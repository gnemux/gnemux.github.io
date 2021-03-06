---
layout: post
title: A BETTER TRAFFIC DATA VISUALIZATION
type: photo
imagefeature: https://xumeng-me.oss-cn-hangzhou.aliyuncs.com/ticc2_interface.png?x-oss-process=image/resize,p_20
categories: create
description: "更美好才更有效"
comments: false
---

这是为某项目旧版的[交通数据可视化效果](https://xumeng.me/create/traffic-data)

![T-Data-Map](https://xumeng-me.oss-cn-hangzhou.aliyuncs.com/T-Data-Map?x-oss-process=image/resize,p_30)

为了更好的数据可视化效果,我们为一年前的交通数据可视化项目增加了新的界面和新的GIS交互方式. 我们通过如下几个方面的努力,以体现“一张图”和“平滑”概念.我们为系统设计了全新的界面风格,借鉴了《Oblivion》([GMUNK公司的视觉设计](http://gmunk.com/OBLIVION-GFX))

![TICC2-INTERFACE](https://xumeng-me.oss-cn-hangzhou.aliyuncs.com/ticc2_interface.png?x-oss-process=image/resize,p_30)


我们采用了基于[OpenLayers 3](http://openlayers.org) 的GIS-API重做了所有地图呈现与交互效果, 使得在Web端的像“平滑缩放”这样类似Google Earth提供的视觉效果能够得以实现.

<figure>
	<a href="https://xumeng-me.oss-cn-hangzhou.aliyuncs.com/ticc2-dynamic.gif"><img src="https://xumeng-me.oss-cn-hangzhou.aliyuncs.com/ticc2-dynamic.gif"></a>
</figure>


我们采用了新的页面分割方式,使界面的每一块区域的功能更加明确,配合后台代码与数据的模块化,充分使用异步加载使功能切换更加平滑,并进一步降低了维护成本.


<figure class="half">
	<a href="https://xumeng-me.oss-cn-hangzhou.aliyuncs.com/ticc2-nav1.png"><img src="https://xumeng-me.oss-cn-hangzhou.aliyuncs.com/ticc2-nav1.png?x-oss-process=image/resize,p_30"></a>
	<a href="https://xumeng-me.oss-cn-hangzhou.aliyuncs.com/ticc2-nav2.png"><img src="https://xumeng-me.oss-cn-hangzhou.aliyuncs.com/ticc2-nav2.png?x-oss-process=image/resize,p_30"></a>
</figure>



