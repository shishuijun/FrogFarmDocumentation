---
description: 条件判断
---

# If

只有在条件符合的时候，才会执行[Result](result.md)中的效果

以<mark style="color:red;">大括号{}</mark>括起，通常由[Comparison](../comparison/)组成（0-n个）

### 基础示例

当自身收成次数=5时

```csharp
{Self,HarestTimes,Equal,5} 
```

当金币数量>10时

{% code overflow="wrap" %}
```csharp
{Global,Money,Bigger,10} 
```
{% endcode %}

### 复合条件

使用&表示两个条件需要同时满足，使用|表示两个条件中只需一者满足

{% hint style="warning" %}
&和|暂时不支持同时出现！
{% endhint %}

示例：

**当金币数量>10 且 当自身收成次数=5时**

```csharp
{Global,Money,Bigger,10 && Self,HarestTimes,Equal,5} 
```

**当自身生长值>1 或 自身为建筑**

```csharp
{Self,Growth,Bigger,1 || Self,Type,Equal,Building} 
```

{% hint style="success" %}
大括号{}可以加任意空格，程序会在读取时自动忽略所有空格

如<mark style="color:red;">{Global,Money,Bigger,10}</mark> 与<mark style="color:red;">{Global,        Money, Bigger, 10}</mark> 是等价的
{% endhint %}
