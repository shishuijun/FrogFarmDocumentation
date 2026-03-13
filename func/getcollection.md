---
description: 筛选卡组
---

# GetCollection

## 规范

GetCollection([Value](../common/value/) originValue ' [VarifyWay](../common/comparison/varifyway.md) way ' [Value](../common/value/) comparisonValue)

返回值：[GoalRange](../common/goalrange.md) newRangeGetCollection

{% hint style="warning" %}
GetCollection函数中的Value必须是CardInfo相关的Value，不可为Global分类的Value
{% endhint %}

筛选当前职业和中立卡组中符合条件的range（只读）

示例：

卡组中的建筑

```csharp
GetCollection(Type'Is'Building)
```

## 复合用法

GetCollection([Value](../common/value/) originValue'[VarifyWay](../common/comparison/varifyway.md) way'[Value](../common/value/) comparisonValue'......)

GetCollection的条件中也可以进行组合，使用&表示两个条件需要同时满足，使用|表示两个条件中只需一者满足

{% hint style="warning" %}
&和|暂时不支持同时出现！
{% endhint %}

示例：

**卡组中的2级建筑**

```csharp
GetCollection(Type'Is'Building & Level'Equal'2)
```

