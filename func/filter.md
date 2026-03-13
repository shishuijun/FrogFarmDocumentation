---
description: 筛选GoalRange
---

# Filter

## 规范

Filter([GoalRange](../common/goalrange.md) originRange ' ([Value](../common/value/) originValue ' [VarifyWay](../common/comparison/varifyway.md) way ' [Value](../common/value/) comparisonValue))

返回值：[GoalRange](../common/goalrange.md) newRange

{% hint style="warning" %}
Filter函数中的Value必须是CardInfo相关的Value，不可为Global分类的Value
{% endhint %}

{% hint style="warning" %}
仅可作用于[GoalRange](../common/goalrange.md)不是所有GoalRange都可以使用该函数，只有拥有卡牌的集合才可以进行筛选，如Bag、Around，具体见[预设范围](../common/goalrange.md#mu-biao-zuo-yong-fan-wei-yu-she-biao)表
{% endhint %}

示例：

**周围的植物**

```csharp
Filter(Around'(Type'Is'Plant))
```

## 复合用法

Filter([GoalRange](../common/goalrange.md) originRange'([Value](../common/value/) originValue'[VarifyWay](../common/comparison/varifyway.md) way'[Value](../common/value/) comparisonValue'......))

Filter的条件中也可以进行组合，使用&表示两个条件需要同时满足，使用|表示两个条件中只需一者满足

{% hint style="warning" %}
&和|暂时不支持同时出现！
{% endhint %}

示例：

**周围生长值=1的植物**

```csharp
Filter(Around'(Type'Is'Plant & Growth'Bigger'1))
```

**周围的植物或动物**

```csharp
Filter(Around'(Type'Is'Plant | Type'Is'Animal))
```

