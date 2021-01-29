@[TOC](使用vis-network进行图数据库可视化（一）)

## 什么是vis-network

[vis-network](https://github.com/visjs/vis-network)是[vis.js](https://github.com/visjs)可视化库中的一个组件。主要用于网络可视化需求，支持自定义形状、样式、颜色、大小、图像等。**vis-network**可以在任务现代浏览器上流畅展示多达上千个nodes（节点）和edges（边），也支持cluster（集群），使用**canvas**渲染。作为图数据库可视化工具使用，效果很好。

> 注意：nodes、edges上千之后，已经出现卡顿现象，亲测还是小数据量下可视化效果较为理想

## 安装

1.npm安装
```bash
npm install vis-network
```

2.umd引入
```html
<script type="text/javascript" src="../../../standalone/umd/vis-network.min.js"></script>
```
