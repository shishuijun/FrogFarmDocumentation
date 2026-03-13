---
description: 对某个范围统计SpecialVal
---

# CountSpecialVal

## 规范

CountSpecialVal([GoalRange](../common/goalrange.md) originRange'([Value](../common/value/) originValue'[VarifyWay](../common/comparison/varifyway.md) way'[Value](../common/value/) comparisonValue))

返回值：int counter

示例：

**周围的动物巢穴中动物数量**

```csharp
CountSpecialVal(Around'(Type'Is'Nest))
```

## 复合用法

CountSpecialVal([GoalRange](../common/goalrange.md) originRange'([Value](../common/value/) originValue'[VarifyWay](../common/comparison/varifyway.md) way'[Value](../common/value/) comparisonValue'......))

CountSpecialVal的条件中也可以进行组合，使用&表示两个条件需要同时满足，使用|表示两个条件中只需一者满足

{% hint style="warning" %}
&和|暂时不支持同时出现！
{% endhint %}
