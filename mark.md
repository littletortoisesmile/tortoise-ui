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

## Demo

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Vis Network | Basic usage</title>
    <script type="text/javascript" src="./vis-network.min.js"></script>
    <style type="text/css">
      #mynetwork {
        width: 600px;
        height: 400px;
        border: 1px solid lightgray;
      }
    </style>
  </head>
  <body>
    <p>Create a simple network with some nodes and edges.</p>
    <div id="mynetwork"></div>

    <script type="text/javascript">
      // create an array with nodes
      const nodes = new vis.DataSet([
        { id: 1, label: "Node 1" },
        { id: 2, label: "Node 2" },
        { id: 3, label: "Node 3" },
        { id: 4, label: "Node 4" },
        { id: 5, label: "Node 5" },
      ]);

      // create an array with edges
      const edges = new vis.DataSet([
        { from: 1, to: 3 },
        { from: 1, to: 2 },
        { from: 2, to: 4 },
        { from: 2, to: 5 },
        { from: 3, to: 3 },
      ]);
