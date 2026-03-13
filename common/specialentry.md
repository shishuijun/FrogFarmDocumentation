---
description: 特殊词条
---

# SpecialEntry

对于卡牌/挂件而言，除效果外，还有一些特殊词条，在Effect栏里使用<mark style="color:red;">小括号()</mark>括出

示例：

**使1个植物生长+2(消耗)**

{% code overflow="wrap" %}
```csharp
Play <[Chosen,Growth,2]> (Consume)
```
{% endcode %}

特殊词条必须来自于下列列表

## 特殊词条列表

<table data-full-width="false"><thead><tr><th>Name</th><th>Explanation</th><th>CardTypeOnly<select><option value="hPzgDyNTm4N0" label="Spell" color="blue"></option><option value="mGZPs3DgoeES" label="Item" color="blue"></option><option value="b0moXTErurxK" label="Card" color="blue"></option><option value="hXRdGg6RDtCx" label="Pendant" color="blue"></option></select></th></tr></thead><tbody><tr><td>Consume</td><td>消耗，打出后消失</td><td><span data-option="hPzgDyNTm4N0">Spell</span></td></tr><tr><td>CannotDestroy</td><td>不可销毁</td><td><span data-option="mGZPs3DgoeES">Item</span></td></tr><tr><td>BackBag</td><td>回袋，打出后回到袋子</td><td><span data-option="hPzgDyNTm4N0">Spell</span></td></tr><tr><td>CannotSell</td><td>不可出售</td><td><span data-option="b0moXTErurxK">Card</span></td></tr><tr><td>CannotMove</td><td>不可移动</td><td><span data-option="mGZPs3DgoeES">Item</span></td></tr><tr><td>DoubleHarvest</td><td>双倍收成</td><td><span data-option="mGZPs3DgoeES">Item</span></td></tr><tr><td>Repeat</td><td>可重复获得（仅限挂件）</td><td><span data-option="hXRdGg6RDtCx">Pendant</span></td></tr><tr><td>Foresee</td><td>预知，每回合抽牌时必定优先抽出（0费植物默认预知）</td><td><span data-option="hPzgDyNTm4N0">Spell</span></td></tr></tbody></table>

