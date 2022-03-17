### 节坐标转换成世界坐标

+ convertToWorldSpace：忽略锚点，以左下角为原点

  ```lua
  local worldPos = targetNode:getParent():convertToWorldSpace(cc.p(targetNode:getPosition));
  ```

+ convertToworldSpaceAR: 不忽略锚点，以锚点为原点

  ```lua
  local worldPosAR = targetNode:getParent():convertToWorldSpaceAR(targetNode:getPosition());
  ```

### 世界坐标转换成节点坐标

 + convertToNodeSpace: 忽略锚点，以左下角为原点

   ```lua
   local nodePos = targetNode:getParent():convertToNodeSpace(worldPos);
   ```

+ convertToNodeSpaceAR: 不忽略锚点，以锚点为原点

  ```lua
  local nodePosAR = targetNode:getParent():convertToNodeSpaceAR(worldPosAR);
  ```

### 举例

```lua
--节点树：
node_main
　　node_parent_1
　　　　node_child
　　node_parent_2
--目标：获取 node_child 相对于 node_parent_2 的节点坐标！

-- convertToWorldSpace：忽略锚点，以左下角为原点

 local worldPos = node_parent_1:convertToWorldSpace(cc.p(node_child:getPosition()));
 local nodePos  =  node_parent_2:convertToNodeSpace(worldPos);
-- nodePos 即为所求的坐标
```



#### scrollview 一些用法

```lua
-- 滑动区域的大小重新设置
scrollview:setContentSize(418, 160);
scrollview:setInnerContainerSize(cc.size(410, 160));

-- 最大滚动速度
scrollview:setMaxSpeed(2000);

-- 滚动加速度
scrollview:setBounceBoundaryY(-1100);

-- 回弹距离
scrollview:setAcceleration(60);
```



#### 九宫格设置

```lua
-- 背景拉伸
local contentBg = findChildByName(self.node, "CT/desc_node/content_bg");
setScale9Size(contentBg, scale9rect(48, 48, 62, 62), cc.size(430, 185));
```

