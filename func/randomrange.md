---
description: 从goalRange中随机num张卡牌
---

# RandomRange

## 规范

RandomRange([GoalRange](../common/goalrange.md) originRange : int num)

返回值：[GoalRange](../common/goalrange.md) newRange

示例：

**地里随机一个植物**

```csharp
RandomRange(Filter(Ground'(Type'Is'Plant)) : 1)
```

