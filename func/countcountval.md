---
description: 对某个范围统计CountVal
---

# CountCountVal

## 规范

CountCountVal([GoalRange](../common/goalrange.md) originRange'([Value](../common/value/) originValue'[VarifyWay](../common/comparison/varifyway.md) way'[Value](../common/value/) comparisonValue))

返回值：int counter

示例：

周围巢穴的countVal之和

```csharp
CountCountVal(Around'(Type'Is'Nest))
```

## 复合用法

CountCountVal([GoalRange](../common/goalrange.md) originRange'([Value](../common/value/) originValue'[VarifyWay](../common/comparison/varifyway.md) way'[Value](../common/value/) comparisonValue'......))

CountCountVal的条件中也可以进行组合，使用&表示两个条件需要同时满足，使用|表示两个条件中只需一者满足

{% hint style="warning" %}
&和|暂时不支持同时出现！
{% endhint %}
