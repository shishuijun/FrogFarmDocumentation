---
description: 判断挂件是否存在
---

# IsPendantExist

## 规范

int IsPendantExist(string range : string value)

返回值：int exist

**若存在返回1，不存在返回0**

{% hint style="warning" %}
range为ID/Name，分别表示按ID搜索/按名字搜索
{% endhint %}

{% hint style="warning" %}
value为要搜索的值，如要搜索的挂件ID/名字
{% endhint %}

示例：

**判断ID为P-StrongGrow-1的挂件是否存在**

```csharp
IsPendantExist(ID:Neutral-1)
```

**判断名字为丰收之力的挂件是否存在**

```csharp
IsPendantExist(Name:丰收之力)
```

