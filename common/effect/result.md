---
description: 结果
---

# Result

## 规范

由 数值变更 或者 事件触发 组成

以<mark style="color:red;">中括号\[]</mark>括起，每一条Result仅有一条数值变更/事件触发，<mark style="color:red;">无复合</mark>Result

### · 数值变更

数值变更指的是[GoalRange](../goalrange.md)中[Value](../value/)的变化

-如果是int（数值），通常表示的是在原值上变化的值

&#x20; 如果是要为int赋值，需要在数字前面加上=表示

&#x20; 如果是要为int乘积，需要在数字前面加上\*表示（生命值无法进行乘积）

-如果是string（字符串），通常表示的是将新的字符串赋给指定的值

&#x20; 如果是加在后面，需要在字符串前面加上+表示

&#x20; 如果是删除部分字符串，需要在字符串前面加上-表示

&#x20; 如果是添加[Entry](../specialentry.md)词条，需要在字符串前面加上E表示

&#x20; 如果是为字符串赋值，需要在字符串前面加上=表示

示例：

**金币设置为10**

{% code overflow="wrap" %}
```csharp
[Chosen,Money,*5]
```
{% endcode %}

**金币+5**

{% code overflow="wrap" %}
```csharp
[Global,Money,5]
```
{% endcode %}

**自身生长周期-1**

```csharp
[Self,GrowPeriod,-1]
```

**选中的植物生长值+1**

{% code overflow="wrap" %}
```csharp
[Chosen,Growth,1]
```
{% endcode %}

### · 事件触发

事件触发指的是触发某一[Event](../event/)事件

示例：

**将两个粑粑放入袋子中**

{% code overflow="wrap" %}
```csharp
[BagIn(粑粑;2)]
```
{% endcode %}
