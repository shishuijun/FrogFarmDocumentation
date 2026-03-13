---
description: Buff支持的GoalValue列表
---

# Buff-GoalValue

## 1. 常数

例如：

周围植物收成金币+2

```csharp
Buff(Around,Type;Is;Plant,HarvestIncome,2)
```

## 2. Global数值

* Money
* TimeLabelLimit
* TempTimeLabelLimit
* Health
* HealthLimit

例如：

周围植物收成金币+当前临时时间

```csharp
Buff(Around,Type;Is;Plant,HarvestIncome,GetDataInt(Global:TempTimeLabelLimit))
```

## 3. 物品数值

* TimeLabel
* Growth
* GrowPeriod
* HarvestIncome
* TempHarvestIncome
* TempTimeLabel
* SpecialVal
* CountVal
* LabelVal
* HarvestCounter
* EffectPar{x}

例如：

周围植物收成金币+本物品特殊值

```csharp
Buff(Around,Type;Is;Plant,HarvestIncome,GetDataInt(Self:SpecialVal))
```
