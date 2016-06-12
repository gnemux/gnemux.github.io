---
layout: post
title: A BETTER TRAFFIC DATA VISUALIZATION
type: photo
imagefeature: http://7xkj65.com1.z0.glb.clouddn.com/ticc2_interface.png?imageMogr2/thumbnail/!30p
categories: idea
comments: false
---

这是为某项目旧版的[交通数据可视化效果](http://xumeng.me/idea/traffic-data)

![T-Data-Map](http://7xkj65.com1.z0.glb.clouddn.com/T-Data-Map?imageMogr2/thumbnail/!30p)

为了更好的数据可视化效果,我们为一年前的交通数据可视化项目增加了新的界面和新的GIS交互方式. 我们通过如下几个方面的努力,以体现“一张图”和“平滑”概念.我们为系统设计了全新的界面风格,借鉴了《Oblivion》([GMUNK公司的视觉设计](http://gmunk.com/OBLIVION-GFX))

![TICC2-INTERFACE](http://7xkj65.com1.z0.glb.clouddn.com/ticc2_interface.png?imageMogr2/thumbnail/!30p)


我们采用了基于[OpenLayers 3](http://openlayers.org) 的GIS-API重做了所有地图呈现与交互效果, 使得在Web端的像“平滑缩放”这样类似Google Earth提供的视觉效果能够得以实现.

<figure>
	<a href="http://7xkj65.com1.z0.glb.clouddn.com/ticc2-dynamic.gif"><img src="http://7xkj65.com1.z0.glb.clouddn.com/ticc2-dynamic.gif"></a>
</figure>


我们采用了新的页面分割方式,使界面的每一块区域的功能更加明确,配合后台代码与数据的模块化,充分使用异步加载使功能切换更加平滑,并进一步降低了维护成本.


<figure class="half">
	<a href="http://7xkj65.com1.z0.glb.clouddn.com/ticc2-nav1.png"><img src="http://7xkj65.com1.z0.glb.clouddn.com/ticc2-nav1.png?imageMogr2/thumbnail/!30p"></a>
	<a href="http://7xkj65.com1.z0.glb.clouddn.com/ticc2-nav2.png"><img src="http://7xkj65.com1.z0.glb.clouddn.com/ticc2-nav2.png?imageMogr2/thumbnail/!30p"></a>
</figure>



