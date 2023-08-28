---
title: Start-Hexo
date: 2023-08-24 11:08:03
categories: '开发'
tags: 'blog'
---

# A Beginning of Blog Lifestyle
- 搭建自己的博客是一个突然的想法，算是对自己生活的一个记录，以一种古早的方式在未来的互联网海洋里留下自己的一丝痕迹；
- 考虑到增加文章的便捷流程和静态页面的良好性能，目前选择[Hexo](https://hexo.io/zh-cn)作为搭建博客的工具，同时使用Github Page作为博客的托管平台,主题选择的是清新快捷的[Ayer](https://github.com/shen-yu/hexo-theme-ayer)；

# 以下记录部署Hexo过程
## 申请Github Page
现在的GitHub Page申请流程已经十分简便:
1. 新建仓库，命名为`{usrname}.github.io`
2. 在仓库设置中找到GitHub Page，设置主要的Branch(这里的主要问题是古早的git原始分支都是master，但是Github目前的默认分支时main，在部署时本地与Github的分支需要同步，不如提前就在申请Page时设置)
3. 后面还需要配置Github Deployment，但是Hexo可以通过插件自动完成这一步，后面会有操作过程。
## 安装Hexo
1. 安装Node.js
2. 安装Hexo
```bash
npm install -g hexo-cli
```
3. 初始化Hexo
```bash
hexo init <folder>
cd <folder>
npm install
```
4. 本地预览，在此你已经在可以看到一个完备的静态页面
```bash
hexo server
```
## 部署Hexo 至 Github Page
1. 安装hexo-deployer-git插件
```bash
npm install hexo-deployer-git --save
```
2. 修改配置文件
```yml
deploy:
  type: git
  repo: <repository url> # 仓库地址 https://github.com/{usrname}/{usrname}.github.io
  branch: [branch] # 确保这个Branch和Github Page的Branch一致
```
3. 部署，至此已经实现了一个简单的Github博客，接下来就就可以开始写作了 ([Hexo](https://hexo.io/zh-cn)或者自带的hello-word.md有不错的模板)
```bash
hexo deploy
```
