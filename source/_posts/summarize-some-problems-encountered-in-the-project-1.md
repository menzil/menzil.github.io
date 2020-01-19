---
layout: publish
title: 总结有些在项目中遇到的问题（1）
date: 2020-01-19 12:27:34
tags:
- javascript
- electron
- react
- react-hooks
---


最近在用react-hook、electron技术站做个电脑端应用，本篇记录一下项目中遇到的一些大小问题借解决办法。


### 1. create-react-app 无 eject 配置代理请求
	安装 http-proxy-middleware，`npm install http-proxy-middleware --save-dev`
	添加 src/setupProxy.js 文件, 不需要另外引入到项目
	```
	const proxy = require('http-proxy-middleware');
	module.exports = function(app) {
	  app.use(proxy('/api', { target: 'http://localhost:5000/' }));
	};
```

### 2. 点击子元素是防止父容器点击事件的执行
`e.stopPropagation();`
