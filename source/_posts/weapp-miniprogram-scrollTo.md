---
title: 微信小程序scrollTo
date: 2019-03-12 20:27:16
tags:
- 微信小程序
- JavaScript
---

需求： 在“subat视频”微信小程序首页实现播放完一个视频后继续播放下一个视频并自动scroll到当前播放的视频。
实现思路： 播放下一个视频当然不是问题，获取当前视频index并找出下一个视频，播放就可以了。
问题：问题就是上面提到的需求。
解决方案： 在视频列表给每个视频设个id，然后通过官方提供的[`SelectorQuery wx.createSelectorQuery()`](https://developers.weixin.qq.com/miniprogram/dev/api/wx.createSelectorQuery.html)和[`wx.pageScrollTo(Object object)`](https://developers.weixin.qq.com/miniprogram/dev/api/wx.pageScrollTo.html)来实现。
具体实现函数如下：

``` JavaScript
scrollToVideo(videoId){
	if(videoId){
		const query = wx.createSelectorQuery();
		query.select('#video-'+videoId).boundingClientRect();
		query.selectViewport().scrollOffset();
		console.log(query,'query');
		query.exec((res)=> {
			console.log(res,'res');
			// res[0].top  // #the-id节点的上边界坐标
			// res[1].scrollTop // 显示区域的竖直滚动位置
			wx.pageScrollTo({
				scrollTop: res[1].scrollTop+res[0].height,
				duration: 300
			})
		})
	}
}

```
