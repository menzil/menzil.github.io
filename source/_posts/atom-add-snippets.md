---
title: Atom add snippets for weapp view tag
date: 2019-02-11 17:11:27
tags:
- 小程序
- atom
---

这里应该得用`'.source.wxml'`，但是我这样写一直不起作用，只能用*来设置全局了。

``` CoffeeScript
'*':
  'Snippet Name':
    'prefix': 'view'
    'body': '<view class="${1:}"></view>'
```
