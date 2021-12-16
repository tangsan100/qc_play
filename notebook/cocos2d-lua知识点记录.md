#### 节点之间的坐标转换

节点树：
node_main
　　node_parent_1
　　　　node_child
　　node_parent_2
目标：获取 node_child 相对于 node_parent_2 的节点坐标！

```lua
 local worldPos = node_parent_1:convertToWorldSpace(cc.p(node_child:getPosition()));
 local nodePos  =  node_parent_2:convertToNodeSpace(worldPos);
-- nodePos 即为所求的坐标
```

