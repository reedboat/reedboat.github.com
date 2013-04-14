---
layout: page
title: "'热点休走'方案设计"
description: "关注最重要的新闻，不让社会热点轻易溜走"
category:产品设计
tags: [产品, 热点]
---

# 不忘新闻设计稿
## 想法
世界上每天都会发生很多的事件，在网络时代，一些事件被广大网民所关注，形成社会热点，产生巨大的能量。
但是网民的精力有限，关注点很容易被转移，每当一个新的热点产生，旧事件很快就被大家遗忘。
很多的事情并未得到解决就这样不了了之，这样不利于问题的解决。
本产品想通过网民的行为，延长部分社会热点的持久性。

##设计思路
1. 通过数据分析或者抓取，获得每日的焦点事件, 新闻按照事件组织。专题? 对于孤立的事件，可以忽略之
1. 网友可以通过微博、QQ、人人等社会化网络账号登陆
1. 网友可以通过点击顶， 来将事件顶上去. 每天对同一事件只能顶一次
1. 对于新闻进行打分排序，时间分和关注分。
## 数据库设计
### Topic
* id
* title
* summary
* keywords
* images:[{pic1, size, label, title},...]
  
### News
* id
* title
* summary
* content
* images
* source

### topic_news
* id
* topic_id
* news_id

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
