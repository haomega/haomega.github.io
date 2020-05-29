---
title: "Hugo and GithubPages 博客搭建"
date: 2020-05-11T11:08:27+08:00
draft: false
---

## Hugo
Go语言实现的博客生成器
> The world's fastest framework for building websites.

在使用Hugo之前，我使用过hexo，Hugo和其相比，速度是快了不少。当然速度并不是那么重要。

## Github Pages

提供了类似静态文件服务的功能，你不必去购买服务器和域名了。

## 搭建步骤

1. 安装Hugo，[下载地址](https://github.com/gohugoio/hugo/releases),请下载对应系统版本；
2. 配置Hugo环境变量，终端中执行`hugo version` 出现版本详情，表示环境变量配置成功；
3. 博客初始化、安装主题、创建post，请查看[官网](https://gohugo.io/getting-started/quick-start/)
4. 配置GithubPages
	* 在Gihub上创建 username.github.io的仓库；
	* 执行`hugo -D` 将会在/public生成静态博客的内容；
	* 我们将/public内容添加remote到第一步的远程仓库，并推送到master；
	* 在仓库的配置页面打开GithubPages；
5. 博客源文件的备份当然，我们也会考虑到，你使用Hugo生成博客的目录可能会丢失，
所以，对当前目录做个备份吧，不仅能备份配置，也能备份生成文章的md源文件。
我的做法是将根目录推送到username.github.io仓库的hugo-source分支，与master分支互不影响。
