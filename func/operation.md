---
description: 数值加减乘除
---

# Operation

仅存在于goalVal的位置，用于对需要变化的数据进一步操作

## 规范

Operation(string input)

返回值：float

**input为：A \[运算符] B \[运算符(可选)] C \[运算符(可选)] D ......**

运算符仅接受+-\*/^五种

此处/并非真正的除法，而是整数的/，例如7/3=2，意味着7有两个3

## 多重运算

Operation可以接受多个运算符和运算数据，但不接受嵌套Operation

多个运算符会无视数学运算规则，按照从左到右依次结算运算的方式



示例：

**周围竹子数量x3**

```csharp
Operation(Count(Around'(Name'Is'竹子))*3)
```

{% hint style="info" %}
可以与GetDataInt或Count嵌套使用
{% endhint %}
