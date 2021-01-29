
### nodes节点

配置节点的样式。也可以在data中配置每个节点的属性，data中的单个节点配置项将覆盖全局配置。[参考](https://ame.cool/pages/43724c)

```js
nodes: {
    shape: "circle",
    widthConstraint: { maximum: 100 },
    scaling: {
      min: 10,
      max: 30,
    },
    font: {
      size: 12,
      face: "Tahoma",
    },
}
```

### edges边

配置边的样式。[参考](https://ame.cool/pages/7e4bf1/)

```js
edges: {
    width: 0.15,
    arrows: {
      to: {
        type: "arrow",
        enabled: true,
      },
    },
    length: 120,
    color: { inherit: "from" },
    smooth: {
      type: "continuous",
    },
}
```

### groups组

定义每个组的样式，除了id、x、y之外，其余和node的配置项相同。
```js
const nodes = [
    {
        id:1, 
        group:'myGroup', // 组名 myGroup
        label:"I'm in a custom group called 'myGroup'!",
    },
]

const options = {
  groups: {
    // 定义 myGroup组的样式
    myGroup: {
        color:{background:'red'}, borderWidth:3
    }
  }
}
```

### layout布局

充当canvas上的摄像机，进行动画、缩放和对焦。

### interaction交互

用于与关系网的所有用户交互。处理鼠标和触摸事件等。

### manipulation可视化操作

配置vis-network自带的添加节点、添加边、编辑节点、编辑边、删除节点、删除边等工具按钮。

### physics物理引擎

处理物理模拟，移动节点和边以清晰地显示它们。
