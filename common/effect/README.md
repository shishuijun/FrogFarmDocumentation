---
description: 效果
---

# Effect

## 规范

一个效果通常由[Trigger](trigger.md)、[If](if.md)以及[Result](result.md)构成

其中[Trigger](trigger.md)表示触发的事件，[If](if.md)表示需要满足的条件，[Result](result.md)表示满足条件后的结果

If和Result的组合体称为**行为Act**，行为由<mark style="color:red;"><></mark>括起，其中可以有0或1个If，但至少有一个Result

#### 详细规则：

1. Trigger必须存在，有且只有1个
2. Trigger后可跟随任意数量的Behaviour

也就是说，效果的构成为：

**Trigger \<If(可选) Result Result ...>  \<If(可选) Result Result ...> ...**

{% hint style="success" %}
一张卡牌可以拥有多个Effect
{% endhint %}

示例：

**回合结束时：若金币>10，则自身生长周期-1并且+5金币**

{% code overflow="wrap" %}
```csharp
RoundEnd <{Global,Money,Bigger,10} [Self,GrowPeriod,-1][Global,Money,5]>
```
{% endcode %}

&#x20;         ↓                                ↓                                                 ↓                                      ↓

&#x20;    **Trigger                            If                                            Result1                             Result2**

***

**回合结束时：+5金币，若金币>10，则自身生长周期-1**

{% code overflow="wrap" %}
```csharp
RoundEnd <[Global,Money,5]> <{Global,Money,Bigger,10} [Self,GrowPeriod,-1]>
```
{% endcode %}

此处将+5金币的result2单独使用<>括起来，表示与“若金币>10”的条件无关，为单独的一个行为

{% hint style="success" %}
Effect中可以加任意空格，程序会在读取时自动忽略所有空格

如 <mark style="color:red;">YearEnd <\[Global,Money,5]></mark> 与 <mark style="color:red;">YearEnd      <\[Global,      Money,     5]></mark> 是等价的
{% endhint %}

## 扩展

如果需要了解如何标注卡牌的“消耗”等效果，请详见[SpecialEntry](../specialentry.md)特殊词条页面

## 多效果

如果希望一张卡牌拥有多个效果（这里按照Trigger划分）

则多个效果之间用#分割

比如布威迪甲龙的

**回合结束时：+8金币，每使用1钻矿石获得金币数量x1.5\[四舍五入]**

{% code overflow="wrap" %}
```csharp
Watch(钻矿石) <[Self,SpecialVal,-1][Self,SpecialVal,x1.5]> 
# 
YearEnd <[Global,Money,GetDataInt(Self'SpecialVal)]>
```
{% endcode %}

