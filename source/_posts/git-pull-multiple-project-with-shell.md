---
title: git-pull-multiple-project-with-shell
date: 2019-02-05 15:21:09
tags:
- shell
- 复习
---

``` shell
#!/bin/bash

for dir in $(ls)
do
	if [ -d $dir ]
	then
		# echo $dir
		cd $dir && echo $dir
		if [ -d ".git" ] && $dir != 'frontend'
		then
			git pull origin master
		else
			echo "文件夹还没有git(或者忽略git pull),请注意把代码保存的远程仓库哦！"
		fi
		cd ..
	fi
	echo '----------------------------------------'
done


```
