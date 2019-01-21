---
title: fibonacci 斐波那契数列
date: 2018-06-10 09:28:39
tags:
- 算法
- 复习
---

最近复习一些算法和数据结构，看完二叉树后再看递归。发现斐波那契数列跟二叉树是一回事（二叉树就是用递归实现的）。而且也进一步了解了函数的执行过程（其实调试就知道）。

### 测试代码如下

```
let i = 0
function fibonacci(num,name){
	console.log(i,name,num);
	i++;
	if(num === 1 || num ===2 ){
		return 1;
	}
	return fibonacci(num-1,'left') + fibonacci(num-2,'right');
}

let sum = fibonacci(6,'root');
console.log(sum,'sum');
```

### 控制台输出结果
```
 0 "root" 6
 1 "left" 5
 2 "left" 4
 3 "left" 3
 4 "left" 2
 5 "right" 1
 6 "right" 2
 7 "right" 3
 8 "left" 2
 9 "right" 1
 10 "right" 4
 11 "left" 3
 12 "left" 2
 13 "right" 1
 14 "right" 2
 8 "sum"
```
### 二叉树图片（只是结构一样）
{% asset_img fibonacci.jpg %}
