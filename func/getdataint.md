---
description: 获取目标数据
---

# GetDataInt

## 规范

GetDataInt([GoalRange](../common/goalrange.md) originRange : string goalValueName)

返回值：int

仅支持获取类型为int整数的数据，float小数不支持

此处的originRange不接受多张卡，必须为Global或一张卡牌

统计HarvestIncome、GrowMultiplier、TimeLabel的时候，结果会连带统计上Temp值

示例：

**金币数量**

```csharp
GetDataInt(Global : Money)
```

**自身的生长值**

```csharp
GetDataInt(Self : Growth)
```
