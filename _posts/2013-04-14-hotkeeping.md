---
layout: page
title: 顶事件
category: work
tags: [产品设计, 新闻]
---

想法
----
世界上每天都会发生很多的事件，在网络时代，一些事件被广大网民所关注，形成社会热点，产生巨大的能量。
但是网民的精力有限，关注点很容易被转移，每当一个新的热点产生，旧事件很快就被大家遗忘。
很多的事情并未得到解决就这样不了了之，这样不利于问题的解决。
本产品想通过网民的行为，延长部分社会热点的持久性。

设计思路
-------
1. 通过数据分析或者抓取，获得每日的焦点事件, 新闻按照事件组织。专题? 对于孤立的事件，可以忽略之
2. 网友可以通过微博、QQ、人人等社会化网络账号登陆
3. 网友可以通过点击顶， 来将事件顶上去. 每天对同一事件只能顶一次
4. 对于新闻进行打分排序，时间分和关注分。
  
数据库设计
---------
### Topic
* id
* title
* summary
* keywords
* images:[{pic1, size, label, title},...]
* created_at
  
### News
* id
* title
* summary
* content
* images
* source
* published_at
* created_at

### topic_news
* id
* topic_id
* news_id
* type

### user
* id
* username
* screenname

### user_bind
* id
* site
* site_uid
* uid
* token
* expire

### user_vote
* id
* user_id
* topic_id
* time

### user_favorite
* id
* user_id
* topic_id

实现步骤
-----
1. 技术选型:django mysql
1. 话题和新闻. 实现新闻按话题组织. 按时间排列
1. 新闻和话题管理后台
1. 新闻和话题视图
1. 增加用户和用户绑定. 先实现新浪微博
1. 增加用户投票, 按投票排列
