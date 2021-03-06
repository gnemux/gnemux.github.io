---
layout: post
title: ABOUT FULL-TEXT SEARCH
type: photo
imagefeature: https://xumeng-me.oss-cn-hangzhou.aliyuncs.com/full-text-search.jpg?x-oss-process=image/resize,p_100
categories: think
description: "关于全文检索"
comments: true
---

所谓全文检索(Full-Text Search)

就是对文件或者其他任何包含着一堆数据信息的对象，提供对其包含所有内容进行全文的搜索功能：比如我有一堆word、excel、txt文件在系统里，我怎样输入一个词(像Alfred 的 in 命令)，程序能帮我找到所有包含了这个词的文件。

#### 主要困难
做这件事情的困难点就是我们面对的是一堆非结构化的数据(比如一个文件)，而搜索是需要面对结构化的数据的(比如同一张表或者同一结构的json)。

#### 解决思路
所以解决这个问题的思路就是，通过一个“索引(Indexing)”过程，读取所有非结构化数据，把里面关键的信息保存在同一个索引结构里。用户查询的时候是面对这张结构化的索引表，命中了以后返回对应的那个文件即可。

#### 解决方案
为了实现这一点，我们需要以下几个工具

+ 可以把非结构化数据(文件)索引成结构化数据的工具
+ 能支持大量数据高性能索引的工具
+ 自然语言处理工具(分词工具) [这个很重要，尤其对中文来说]

----

##### 对于这1点：可以把非结构化数据(文件)索引成结构化数据的工具
• 可以把非结构化数据(文件)索引成结构化数据的工具，最有名的，也是目前效率最高的，就是 [lucene](https://lucene.apache.org/) 这个工具，它已经托管在ASF(Apache软件基金会)开源了


##### 对于第2点: 能支持大量数据高性能索引的工具
• 能支持大量数据高性能索引的工具
目前比较流行的就是 [Elastic Search](https://github.com/elastic/elasticsearch) 它底层就是基于lucene的，但是是分布式的，可扩展的，提供了非常高的索引和查询性能

##### 这里要补充一点
对于如何把Office文件(如Word\Excel)等文件里面的数据提取出来进行索引，也已经有很多现成的方法。用得比较多的方法也都是基于Apache上的一个 [tika](http://tika.apache.org/index.html) 的项目，可以通过这个工具读取所有tika支持的文件格式，Office的都是支持的

更方便的是，有人已经基于tika做了针对elasticsearch的工具 [fscrawler](https://github.com/dadoonet/fscrawler) 用它可以直接把目录里的office数据加载到ES中来，简直不要太方便

##### 对于第3点: 自然语言处理工具(分词工具)
• 自然语言处理工具(分词工具) 
这个很重要，尤其对中文，当我们把所有数据存放到ES中时，因为我们搜索的时候不能像英文那样输入一个单词去查，一般会输入至少是一个词，比如(网上找到一个邪恶的例子)

```
“工信处女干事每月经过下属科室都要亲口交代24口交换机等技术性器件的安装工作”
```

这句话，它要知道分成

```
“工信处/ 女/ 干事/ 每月/ 经过/ 下属/ 科室/ 都/ 要/ 亲口/ 交代/ 24/ 口/ 交换机/ 等/ 技术性/ 器件/ 的/ 安装/ 工作”。
```

这种处理过程我们叫中文分词，它属于自然语言处理NLP(Natural Language Processing)，目前也有很多开源的应用。在Github上都有一个 [NLPChina](https://github.com/NLPchina) 的中国自然语言处理开源组织，里面有很多分词工具项目。

所以，原则上，我们是可以很方便搭建起一套“全文检索”应用的:

+ 用集群发布配置好一套ES
+ 使用FSClawer定时把目标目录下的文件进行索引到ES
+ 选择一个分词系统对数据进行分词，通过ES返回结果完成高效全文检索

> 感谢所有那些开放合作的人们，让创造变得如此简单



