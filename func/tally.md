---
description: 对某个范围统计某个值
---

# Tally

## 规范

Tally([GoalRange](../common/goalrange.md) originRange'([Value](../common/value/) originValue'[VarifyWay](../common/comparison/varifyway.md) way'[Value](../common/value/) comparisonValue))

返回值：int counter

示例：

**周围的植物数量**

```csharp
Tally(Around'(Type'Is'Plant))
```

**袋子里时间标签为1的数量**

```csharp
Tally(Bag'(TimeLabel'Equal'1))
```

## 复合用法

Tally([GoalRange](../common/goalrange.md) originRange'([Value](../common/value/) originValue'[VarifyWay](../common/comparison/varifyway.md) way'[Value](../common/value/) comparisonValue'......))

Tally的条件中也可以进行组合，使用&表示两个条件需要同时满足，使用|表示两个条件中只需一者满足

{% hint style="warning" %}
&和|暂时不支持同时出现！
{% endhint %}

示例：

**周围生长值=1的植物的数量**

<pre class="language-csharp"><code class="lang-csharp"><strong>Tally(Around'(Type'Equal'Plant &#x26; Growth'Bigger'1))
</strong></code></pre>

**袋子里的植物或动物数量**

```csharp
Tally(Bag'(Type'Equal'Plant | Type'Equal'Animal))
```
