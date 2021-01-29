
### isCluster(nodeId)

判断id=nodeId的节点是否为集群
```js
network.on("selectNode", function (params) {
    if (params.nodes.length == 1) {
      if (network.isCluster(params.nodes[0]) == true) {
        network.openCluster(params.nodes[0]);
      }
    }
});
```

### openCluster(nodeId[, options])

打开集群。nodeId为集群id；options可选，目前只支持一个选项releaseFunction，该函数可用于在集群打开后手动定位节点（用的不多）
```js
// 同isCluster
```

### stabilize([iterations])

稳定布局。iterations参数可选，指定迭代次数。数据量小时，可以快速稳定布局，满足部分业务需求。数据量较大时，慎用！比较耗时，卡顿感和明显。
```js
network.stabilize();
network.stabilize(20);
```

### fit([options])

缩放所有节点以适应canvas
```js
network.fit()
```
