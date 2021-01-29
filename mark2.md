
### 1.数组格式

```js
const nodes = [
    {id: 1, label: 'Node 1', color: 'red'},
    {id: 2, label: 'Node 2', color: 'green'},
    {id: 3, label: 'Node 3', color: 'blue'},
]
const edges = [
    {id: 1, from: 1, to: 2},
    {id: 2, from: 2, to: 3},
    {id: 3, from: 3, to: 1},
]
const datas = {
    nodes: nodes,
    edges: edges,
}
```

### 2.DataSet格式

使用示例见前文demo。

### 3.两者之间区别

1、DataSet有**add**、**update**、**remove**、**clear**等方法，可在初始渲染后对数据进行单独增删改操作，可进行双击查询关联node等操作（[示例1](https://visjs.github.io/vis-network/examples/network/data/dynamicData.html)，[示例2](https://visjs.github.io/vis-network/examples/network/data/datasets.html)）；
2、DataSet数据量较大时，存在一定耗时；

### 4.从Gephi导入数据

Network可以直接从gephi导出的json文件中导入数据。[示例](https://ame.cool/pages/f08230/#%E4%BB%8Egephi%E5%AF%BC%E5%85%A5%E6%95%B0%E6%8D%AE)

## options配置项

```js
const options = {
  autoResize: true,
  height: '100%',
  width: '100%'
  locale: 'en',
  locales: locales,
  clickToUse: false,
  configure: {...},    // 详细配置请查看'配置'模块，
  edges: {...},        // 详细配置请查看'边'模块，
  nodes: {...},        // 详细配置请查看'节点'模块，
  groups: {...},       // 详细配置请查看'组'模块，
  layout: {...},       // 详细配置请查看'布局'模块，
  interaction: {...},  // 详细配置请查看'交互'模块，
  manipulation: {...}, // 详细配置请'可视化操作'模块，
  physics: {...},      // 详细配置请查看'物理引擎'模块，
}
```
详细可参考官网可查的[文档](https://visjs.github.io/vis-network/docs/network/)、[中文文档](https://ame.cool/pages/222681/)，就是中文文档比较旧~

### configure

可配置一些vis-network自带的工具项，设置样式、模型等，并能够根据用户设置生成配置项，不过实际使用过程中用到的不多。略~
