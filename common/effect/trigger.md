---
description: 游戏触发事件
---

# Trigger

## 卡牌Trigger表格

<table data-full-width="false"><thead><tr><th>Trigger</th><th>Explanation</th><th width="154">TypeOnly<select><option value="5veJFo3X9AfQ" label="Item" color="blue"></option><option value="WtCqF2uFE6nD" label="Spell" color="blue"></option><option value="Q0Fzej7kD5ph" label="Item-Plant" color="blue"></option><option value="PAF0EPzDQM6H" label="Card" color="blue"></option></select></th><th>When<select multiple><option value="Hbh9mNFKr1EN" label="Hand" color="blue"></option><option value="xyn7vGXN13m9" label="Land" color="blue"></option><option value="0etFOTZtph6T" label="All" color="blue"></option><option value="gQ1XflnrZi3d" label="Bag" color="blue"></option></select></th><th data-hidden><select></select></th></tr></thead><tbody><tr><td>Draw</td><td>抽出</td><td><span data-option="PAF0EPzDQM6H">Card</span></td><td><span data-option="Hbh9mNFKr1EN">Hand</span></td><td></td></tr><tr><td>Play</td><td>打出</td><td><span data-option="WtCqF2uFE6nD">Spell</span></td><td><span data-option="Hbh9mNFKr1EN">Hand</span></td><td></td></tr><tr><td>Consume</td><td>消耗</td><td><span data-option="WtCqF2uFE6nD">Spell</span></td><td><span data-option="Hbh9mNFKr1EN">Hand</span></td><td></td></tr><tr><td>RoundEnd</td><td>回合结束</td><td><span data-option="PAF0EPzDQM6H">Card</span></td><td><span data-option="0etFOTZtph6T">All</span></td><td></td></tr><tr><td>RoundBegin</td><td>回合开始</td><td><span data-option="PAF0EPzDQM6H">Card</span></td><td><span data-option="0etFOTZtph6T">All</span></td><td></td></tr><tr><td>TimeExplode</td><td>时间爆炸</td><td><span data-option="PAF0EPzDQM6H">Card</span></td><td><span data-option="0etFOTZtph6T">All</span></td><td></td></tr><tr><td>TimeSafe</td><td>时间安全</td><td><span data-option="PAF0EPzDQM6H">Card</span></td><td><span data-option="0etFOTZtph6T">All</span></td><td></td></tr><tr><td>Place</td><td>放置</td><td><span data-option="5veJFo3X9AfQ">Item</span></td><td><span data-option="xyn7vGXN13m9">Land</span></td><td></td></tr><tr><td>Destroy</td><td>销毁</td><td><span data-option="5veJFo3X9AfQ">Item</span></td><td><span data-option="xyn7vGXN13m9">Land</span></td><td></td></tr><tr><td>Grow</td><td>生长</td><td><span data-option="Q0Fzej7kD5ph">Item-Plant</span></td><td><span data-option="xyn7vGXN13m9">Land</span></td><td></td></tr><tr><td>Harvest</td><td>收成</td><td><span data-option="Q0Fzej7kD5ph">Item-Plant</span></td><td><span data-option="xyn7vGXN13m9">Land</span></td><td></td></tr><tr><td>Buff</td><td>光环效果（放下时开始生效，拿起则失效）</td><td><span data-option="5veJFo3X9AfQ">Item</span></td><td><span data-option="xyn7vGXN13m9">Land</span></td><td></td></tr><tr><td>YearBegin</td><td>年开始</td><td><span data-option="PAF0EPzDQM6H">Card</span></td><td><span data-option="gQ1XflnrZi3d">Bag, </span><span data-option="xyn7vGXN13m9">Land</span></td><td></td></tr><tr><td>YearEnd</td><td>年结束</td><td><span data-option="PAF0EPzDQM6H">Card</span></td><td><span data-option="gQ1XflnrZi3d">Bag, </span><span data-option="xyn7vGXN13m9">Land</span></td><td></td></tr><tr><td>Add</td><td>放入背包（仅背包卡牌生效）</td><td><span data-option="PAF0EPzDQM6H">Card</span></td><td><span data-option="gQ1XflnrZi3d">Bag</span></td><td></td></tr><tr><td>AfterPlay</td><td>打出后</td><td><span data-option="PAF0EPzDQM6H">Card</span></td><td><span data-option="Hbh9mNFKr1EN">Hand</span></td><td></td></tr><tr><td>Sell</td><td>出售</td><td><span data-option="PAF0EPzDQM6H">Card</span></td><td><span data-option="Hbh9mNFKr1EN">Hand, </span><span data-option="xyn7vGXN13m9">Land</span></td><td></td></tr></tbody></table>

**TypeOnly**表示仅这个事件是某一类卡牌特有的

**When**表示这个事件只有在手牌或者在地里才会触发，All表示手牌或地里都可以

**例如：**

Place是物品特有的事件，并且只有在地里才会触发

**特殊的两个事件：**

TimeExplode事件会在时间值超出时间刻度上限时触发

TimeSafe事件会在回合结束的时候判定，如果本回合没有触发时间爆炸，则会触发TimeSafe事件

{% hint style="info" %}
游戏会自动在抽牌时结算时间标签，无需加在效果里
{% endhint %}

{% hint style="info" %}
Buff不接受If，Result也必须使用Event里的[Buff](../event/#buffevent)事件
{% endhint %}

## 遗物Trigger表格

<table data-full-width="false"><thead><tr><th>Trigger</th><th>Explanation</th><th width="154">TypeOnly<select><option value="MKiOoUwINqSO" label="Relics" color="blue"></option></select></th><th>When<select><option value="0etFOTZtph6T" label="All" color="blue"></option></select></th><th data-hidden><select></select></th></tr></thead><tbody><tr><td>Gain</td><td>获得</td><td><span data-option="MKiOoUwINqSO">Relics</span></td><td><span data-option="0etFOTZtph6T">All</span></td><td></td></tr><tr><td>RoundBegin</td><td>回合开始</td><td><span data-option="MKiOoUwINqSO">Relics</span></td><td><span data-option="0etFOTZtph6T">All</span></td><td></td></tr><tr><td>RoundEnd</td><td>回合结束</td><td><span data-option="MKiOoUwINqSO">Relics</span></td><td><span data-option="0etFOTZtph6T">All</span></td><td></td></tr><tr><td>TimeExplode</td><td>时间爆炸</td><td><span data-option="MKiOoUwINqSO">Relics</span></td><td><span data-option="0etFOTZtph6T">All</span></td><td></td></tr><tr><td>TimeSafe</td><td>时间安全</td><td><span data-option="MKiOoUwINqSO">Relics</span></td><td><span data-option="0etFOTZtph6T">All</span></td><td></td></tr><tr><td>YearBegin</td><td>年开始</td><td><span data-option="MKiOoUwINqSO">Relics</span></td><td><span data-option="0etFOTZtph6T">All</span></td><td></td></tr><tr><td>YearEnd</td><td>年结束</td><td><span data-option="MKiOoUwINqSO">Relics</span></td><td><span data-option="0etFOTZtph6T">All</span></td><td></td></tr><tr><td>Dying</td><td>濒死（没有GlobalMultiplier）</td><td><span data-option="MKiOoUwINqSO">Relics</span></td><td><span data-option="0etFOTZtph6T">All</span></td><td></td></tr></tbody></table>

## 特殊Trigger

### Watch

watch代表需要计算某张卡牌的打出次数/某个普通Trigger的触发次数，统计的数值将存放在[SpecialVal](../value/#cardinfo-ka-pai)里

Watch后跟随的效果会在统计的数值**发生变化**的时候触发

使用规范：

Watch(WatchType,value)

WatchType目前支持：

（1）Trigger    _**这个仅支持挂件使用，并且不可在EffectString中重复出现**_

统计自身某个事件的次数

（2）Condition

统计符合Condition条件的卡牌打出/放置的次数

如：**Watch(Condition,Type;Is;Plant)**

（3）Global

统计Global变量为[value](../value/#global-quan-ju-xin-xi)的增加/减少情况

监听变量的时候，效果不能是对这个变量的同类操作，比如 监听生命值减少，效果中不可以再出现生命值减少

特殊：

监听超额回复

_**Watch(GlobalNum,OnExcessiveHealPlus)**_

例如：

_**Watch(GlobalTimes,TempTimeLabelLimitPlus)**_&#x20;

统计临时时间刻度的增加次数

_**Watch(GlobalNum,TempTimeLabelLimitPlus)**_&#x20;

统计临时时间刻度的增加情况

（4）Around,Harvest

统计周围植物收成的次数

（5）ConditionDestroy

统计符合Condition条件的地里物品的销毁次数

如：Watch(ConditionDestroy,Type;Is;Plant)

#### Harvest

（1）Harvest,Type:Value  /AroundHarvest

统计类型为Value的植物收成次数

（2）Harvest,Name:Value  /AroundHarvest

统计名字为Value的植物收成次数

（3）Harvest,None

统计全局植物收成次数

（4）Havrest,NameContain:Value  /AroundHarvest

统计名字中包含Value的植物的收成次数

#### BagIn

（1）BagIn,Name:Value

统计名字为Value的卡牌放入背包的次数

（2）BagIn,NameContain:Value

统计名字为Value的卡牌放入背包的次数

（3）BagIn,Type:Value

统计类型为Value的卡牌放入背包的次数

（4）BagIn,Catogary:Value

统计种类为Catogary的卡牌放入背包的次数

（5）BagIn,None

统计将卡包放入背包的次数



**DrawCondition**

（1）DrawCondition,Condition

统计符合Condition条件的卡牌抽出次数



**GlobalEvent**

（1）GlobalEvent,AllGrow

统计全局生长的次数
