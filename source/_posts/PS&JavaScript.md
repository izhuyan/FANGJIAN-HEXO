---
title: PS&JavaScript教程创建动态3D照片
---
在本教程中，我们将向您展示如何使用JavaScript和[Pixi.js](https://www.pixijs.com/ "Pixi.js") webGL库从图像创建3D照片的幻觉。让我们来看看！

<!-- more -->

# **这个概念**
因此，为了将普通照片变成3D照片，我们需要使用深度图（或者有人会调用置换贴图或高度贴图）就像名称所说的那样，深度贴图是一个图像文件，用于显示每个像素的深度。
# 教程视频
### 哔哩哔哩观看：
##### （由于b站对外嵌视频支持不好建议[点此观看原视频](https://www.bilibili.com/video/av55355837/ "点此观看原视频")）
<iframe width="560" height="315" src="//player.bilibili.com/player.html?aid=55355837&cid=96792753&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

### YouTube观看：
##### （YouTube可以直接观看，欢迎去我的频道点赞转发评论哦！[点此观看原视频](https://www.bilibili.com/video/av55355837/ "点此观看原视频")）
<iframe width="560" height="315" src="https://www.youtube.com/embed/PGepIYuQu7U" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### 代码部分：
让我们首先下载最新版本的[Pixi.js](https://www.pixijs.com/ "Pixi.js")并将其包含在页面中。

```javascript
	<script src = “pixi.min.js” > </ script>

	let app = new PIXI.Application({width: window.innerWidth, height: window.innerHeight});
	document.body.appendChild(app.view);

	let img = new PIXI.Sprite.from("pikachu.jpg");
	img.width = window.innerWidth;
	img.height = window.innerHeight;
	app.stage.addChild(img);

	depthMap = new PIXI.Sprite.from("pikachu-map.jpg");
	app.stage.addChild(depthMap);
        
	displacementFilter = new PIXI.filters.DisplacementFilter(depthMap);
	app.stage.filters = [displacementFilter];

	window.onmousemove = function(e) {
  displacementFilter.scale.x = (window.innerWidth / 2 - e.clientX) /20;
  displacementFilter.scale.y = (window.innerHeight / 2 - e.clientY) /20;
};

```

> 我希望这有助于你并设计灵感。
欣赏这个视频......
在另一个视频中看到你。

> 感谢收看，如果您有任何疑问，请发表评论，或者您对下一个视频教程有一些不错的建议。

> 如果你喜欢这个视频，请按，然后分享。
期望在下一个教程中见到你，You see see one day day de。
