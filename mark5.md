
### cluster(options)

手动进行集群操作
```js
clusterOptionsByData = {
    joinCondition: function (childOptions) {
      return childOptions.color.background === color; // the color is fully defined in the node.
    },
    processProperties: function (
      clusterOptions,
      childNodes,
      childEdges
    ) {
      var totalMass = 0;
      for (var i = 0; i < childNodes.length; i++) {
        totalMass += childNodes[i].mass;
      }
      clusterOptions.mass = totalMass;
      return clusterOptions;
    },
    clusterNodeProperties: {
      id: "cluster:" + color,
      borderWidth: 3,
      shape: "database",
      color: color,
      label: "color:" + color,
    },
};
network.cluster(clusterOptionsByData);
```

### clusterByConnection(nodeId,[options])

将指定的节点、与其连接的节点组成一个集群
```js
network.clusterByConnection(1);
```

### clusterByHubsize([hubsize],[options])

设置当节点连接的边超过一定数量（hubsize）后聚合
```js
var clusterOptionsByData = {
  processProperties: function (clusterOptions, childNodes) {
    clusterOptions.label = "[" + childNodes.length + "]";
    return clusterOptions;
  },
  clusterNodeProperties: {
    borderWidth: 3,
    shape: "box",
    font: { size: 30 },
  },
};
network.clusterByHubsize(undefined, clusterOptionsByData);
```

### clusterOutliers([options])

将所有具有1个边的节点与它们各自的连接节点组成一个集群，就是将最边缘的叶子节点和它连接的节点聚合
```js
network.clusterOutliers();
```
