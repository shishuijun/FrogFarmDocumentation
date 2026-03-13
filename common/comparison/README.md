---
description: 比较
---

# Comparison

## 规范

[GoalRange](../goalrange.md) **judgeGoal,**[Value](../value/) **originValue,**[VarifyWay](varifyway.md) **way,**[Value](../value/) **comparisonValue**

<table data-full-width="false"><thead><tr><th>Name</th><th>Type</th><th>Explanation</th></tr></thead><tbody><tr><td>JudgeGoal</td><td><a href="../goalrange.md">GoalRange</a></td><td>目标/目标范围</td></tr><tr><td>OriginValue</td><td><a href="../value/">Value</a></td><td>原目标值</td></tr><tr><td>VarifyWay</td><td><a href="varifyway.md">VarifyWay</a></td><td>比较方式</td></tr><tr><td>ComparisonValue</td><td><a href="../value/">Value</a></td><td>需要对比的值</td></tr></tbody></table>

{% hint style="warning" %}
Comparison的GoalRange中如果是卡牌目标，只能包含1张卡包，不可为卡牌集合
{% endhint %}

originValue除了Value外，也接受Count函数、Operation函数的结果

## 示例

**当自身收成次数=5时**

```csharp
{Self,HarestTimes,Equal,5} 
```

**当金币数量>10时**

{% code overflow="wrap" %}
```csharp
{Global,Money,Bigger,10} 
```
{% endcode %}

