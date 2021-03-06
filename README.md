## 使用
```
yarn add @hyrule/multitree
```

## 工具方法
### dfsTraverse(treeData, callback, [option])

使用深度优先进行遍历树结构

#### 参数

1. treeData *(Array | Object)*: 需要处理的树形数据
2. callback *(Function)*: 回调函数
3. `[option]` *(Object)*: 配置项

其中 callback 为 (item, structure, data) => {}，item 为该节点当前遍历到的节点的数据，structure 为该节点的在树结构中的结构化信息，data 为原始的树结构数据

```javascript | typescript
import { dfsTraverse } from '@hyrule/multitree'
dfsTraverse(treeData, (item, structure, data) => {
  console.log(item, structure, data)
}, {
    childrenKey: 'children',
    targetChildrenKey: 'children',
    routeKey: 'id'
})
```

### bfsTraverse(treeData, callback, [option])

使用广度优先进行遍历树结构

#### 参数

1. treeData *(Array | Object)*: 需要处理的树形数据
2. callback *(Function)*: 回调函数
3. `[option]` *(Object)*: 配置项

其中 callback 为 (item, structure, data) => {}，item 为该节点当前遍历到的节点的数据，structure 为该节点的在树结构中的结构化信息，data 为原始的树结构数据

```javascript | typescript
import { bfsTraverse } from '@hyrule/multitree'
bfsTraverse(treeData, (item, structure, data) => {
  console.log(item, structure, data)
}, {
    childrenKey: 'children',
    targetChildrenKey: 'children',
    routeKey: 'id'
})
```

## 实例方法

### forEach(callback, [option])

```javascript
import MultiTree from '@hyrule/multitree'
const entity = new MultiTree(treeData)
entity.forEach((item, structure, data) => {
  console.log(item, structure, data)
})
```

### map(callback, [option])

```javascript
import MultiTree from '@hyrule/multitree'
const entity = new MultiTree(treeData)
entity.map((item, structure, data) => {
  return {
    ...item,
    depth: structure.depth,
    degree: structure.depth,
    index: structure.index,
    route: structure.structure,
    siblings: structure.siblings,
    isLeaf: structure.structure,
    parent: structure.structure
  }
})
```

### filter(callback, [option])

```javascript
import MultiTree from '@hyrule/multitree'
const entity = new MultiTree(treeData)
entity.map((item, structure, data) => {
  return structure.isLeaf && structrue.depth === 3
})
```

### pick(callback, [option])

```javascript
import MultiTree from '@hyrule/multitree'
const entity = new MultiTree(treeData)
entity.pick((item, structure, data) => {
  return structure.isLeaf && structrue.depth === 3
})
```

### toArray(relationKey, [traversalType])

```javascript
import MultiTree from '@hyrule/multitree'
const entity = new MultiTree(treeData)
entity.toArray('id')
```

### reduce

### getRouteBetweenTwoNode

### getNodesAndRelations
