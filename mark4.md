
### cluster集群

集群配置项是提供给集群方法的配置对象。主要设置集群的样式、已经集群聚合的逻辑。[参考](https://ame.cool/pages/193a81/)

```js
clusterByColor() {
    network.setData(data);
    const colors = ["orange", "lime", "DarkViolet"];
    let clusterOptionsByData;
    for (let i = 0; i < colors.length; i++) {
      let color = colors[i];
      clusterOptionsByData = {
        // joinCondition参数设置聚合逻辑
        joinCondition: childOptions => {
          return childOptions.color.background == color; // the color is fully defined in the node.
        },
        // processProperties参数可修改聚合点的属性
        processProperties: (
          clusterOptions,
          childNodes,
          childEdges
        ) => {
          let totalMass = 0;
          for (let i = 0; i < childNodes.length; i++) {
            totalMass += childNodes[i].mass;
          }
          clusterOptions.mass = totalMass;
          return clusterOptions;
        },
        // 初始设置聚合点属性
        clusterNodeProperties: {
          id: "cluster:" + color,
          borderWidth: 3,
          shape: "database",
          color: color,
          label: "color:" + color,
        },
      };
      network.cluster(clusterOptionsByData);
    }
}
```

集群相关方法和事件在后文全局方法和事件中

## methods方法
列举一些平时较为常用的方法，全量方法可参考[中文文档](https://ame.cool/pages/997cc0/#%E5%85%A8%E5%B1%80%E6%96%B9%E6%B3%95)

### destroy() 

从dom上移出network实例，dom仍然存在
```js
const network = vis.network(container, data, options)

network.destroy()
```

### setData({nodes, edges})

覆盖关系图中的所有数据
```js
network.setData({
    nodes: [...],
    edges: [...]
})
or
network.setData({
    nodes: vis.DataSet([...]),
    edges: vis.DataSet([...])
})
```

### on、off、once

事件监听，常规的，略~
