---
description: 目标作用范围
---

# GoalRange

## 规范

可以直接使用[预设范围](goalrange.md#mu-biao-fan-wei-yu-she-biao)

也可以通过[Filter](../func/filter.md)函数对[预设范围](goalrange.md#mu-biao-fan-wei-yu-she-biao)进行筛选

示例：

**周围的植物**

```csharp
Filter(Around,(Type,Equal,Plant))
```

{% hint style="info" %}
不是所有预设范围都可以经过Filter，具体见表的CanFilter属性
{% endhint %}

## 目标作用范围预设表

{% hint style="warning" %}
<mark style="background-color:orange;">Global</mark>范围只能匹配[Global全局信息](value/#global-quan-ju-xin-xi)中的value

其他范围只能匹配[CardInfo卡牌信息](value/#cardinfo-ka-pai)中的value
{% endhint %}

NoNameRepeat表示范围内不会有名称重复

例如：LandNoNameRepeat，表示地里名称不重复的物品

### 全局

<table data-full-width="false"><thead><tr><th>Name</th><th>Explanation</th><th>CanFilter</th></tr></thead><tbody><tr><td><mark style="background-color:orange;">Global</mark></td><td>全局数值</td><td>否</td></tr><tr><td>Bag</td><td>袋子中的所有卡牌</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>Land</td><td>地里的所有物品</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>CardCollection</td><td>卡牌集合</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>Discard</td><td>弃牌堆中的所有卡牌</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>LandNotSelf</td><td>地里所有物品（除了自己）</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>Deck</td><td>Bag、Land、Discard的合集</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>LandMushroom</td><td>地里的蘑菇植物</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>LandRaindrop</td><td>地里的雨露植物</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>LandRice</td><td>地里的稻子植物</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>LandRiceField</td><td>地里的稻田植物</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>LandRiceAndRiceField</td><td>地里的稻子与稻田植物</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>LandPlant</td><td>地里的植物</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr></tbody></table>

### 物品

<table data-full-width="false"><thead><tr><th>Name</th><th>Explanation</th><th>CanFilter</th></tr></thead><tbody><tr><td>Self</td><td>自身（在地里/作为卡牌）</td><td>否</td></tr><tr><td>Around</td><td>周围物品（仅在地里有效）</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>Left</td><td>左侧物品（仅在地里有效）</td><td>否</td></tr><tr><td>Right</td><td>右侧物品（仅在地里有效）</td><td>否</td></tr><tr><td>LeftAndRight</td><td>左侧与右侧物品（仅在地里有效）</td><td>否</td></tr><tr><td>Up</td><td>上方物品（仅在地里有效）</td><td>否</td></tr><tr><td>Down</td><td>下方物品（仅在地里有效）</td><td>否</td></tr><tr><td>UpAndDown</td><td>上方与下方物品（仅在地里有效）</td><td>否</td></tr></tbody></table>

### 法术

以下范围仅限Trigger为Play（打出）的时候可使用

<table data-full-width="false"><thead><tr><th>Name</th><th>Explanation</th><th>CanFilter</th></tr></thead><tbody><tr><td>Chosen</td><td>法术指定的物品（如有）</td><td>否</td></tr><tr><td>ChosenAround</td><td>法术指定的物品周围的物品</td><td><mark style="color:red;"><strong>是</strong></mark></td></tr><tr><td>ChosenLeft</td><td>法术指定物品的左侧物品</td><td>否</td></tr><tr><td>ChosenRight</td><td>法术指定物品的右侧物品</td><td>否</td></tr><tr><td>ChosenLeftAndRight</td><td>法术指定物品的左侧与右侧物品</td><td>否</td></tr><tr><td>ChosenUp</td><td>法术指定物品的上方物品</td><td>否</td></tr><tr><td>ChosenDown</td><td>法术指定物品的下方物品</td><td>否</td></tr><tr><td>ChosenUpAndDown</td><td>法术指定物品的上方与下方物品</td><td>否</td></tr></tbody></table>

## 卡牌

<table data-full-width="false"><thead><tr><th>Name</th><th>Explanation</th><th>CanFilter</th></tr></thead><tbody><tr><td>SelfCard</td><td>卡牌自身</td><td>否</td></tr></tbody></table>

## 挂件

<table data-full-width="false"><thead><tr><th>Name</th><th>Explanation</th><th>CanFilter</th></tr></thead><tbody><tr><td>SelfPendant</td><td>挂件自身</td><td>否</td></tr></tbody></table>
