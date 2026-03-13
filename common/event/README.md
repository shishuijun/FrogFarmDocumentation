---
description: 事件
---

# Event

事件在使用的时候，直接按照其对应的使用规范使用即可

## <mark style="color:orange;">Global</mark>

### -RandomForcePlace(string name;int num)

地块上随机放num个name，如果地块上已经有物品，将原物品放回弃牌堆

### -TempSetHealthLimit(int healthlimit;int onlyLimit)

临时设置生命值上限，onlyLimit：只调整上限

### -RecoverTempHealthLimit()

解除临时生命值上限，恢复原先的上限

### -TrySubHealth(int num)

尝试扣血，大于num扣除num，否则扣到1

### -TrySubHealthLimit(int num)

尝试扣血上限，大于num扣除num，否则扣到1

### -AddHealth(int num;int times)

恢复num生命值times次

### -TempSetHealthLimitForRound(int healthlimit;int roundNum;int  onlyLimit)

生命值上限都设置为healthlimit，roundNum回合后自动恢复，onlyLimit：只调整上限

如果多次设置，新的roundNum会覆盖旧的roundNum

### -TempSetHealthLimitForYear(int healthlimit;int yearNum;int  onlyLimit)

生命值上限都设置为healthlimit，yearNum回合后自动恢复，onlyLimit：只调整上限

如果多次设置，新的yearNum会覆盖旧的yearNum

### -Transfer([GoalRange](../goalrange.md) range;string name)

将range的卡牌全部转换为名字为name的卡牌（可以被筛选）

### -TransferRange(GoalRange range;GoalRange goalRange)

将range的卡牌全部转换为goalRange的卡牌（仅限一张）

### -ChickenEvolution()

使地里的鸡\鸡群有概率突变为更高一级的鸡\鸡群

### -TriggerTimeExplode(int num)

触发时间爆炸，如果num为0，则会正常结算时间爆炸惩罚，若为1，则会免除时间爆炸惩罚

### **-ChangeTimeScaleAward(int index;string true/false)**

更改时间刻度条奖励的情况，index表示刻度条奖励的序号，true表示激活，false表示不激活

### -ForbidTimeScaleAwardForYear(int index;int num)

将序号为index的时间刻度条奖励禁用num年

### -ForbidTimeScaleAwardForRound(int index;int num)

将序号为index的时间刻度条奖励禁用num回合

### -MapEventTurn(string eventID;bool needUpdatePic)

打开指定ID为eventID的事件

needUpdatePic：是否要更新事件图片

## <mark style="color:orange;">Buff</mark>

### -ThisYear(Buff buff)

本年内拥有buff效果，下一年开始时消失

### -NextYear(Buff buff : int num)

下一年开始时执行buff，num年后效果消失

### -ThisRound(Buff buff)

本回合内拥有buff效果，下一回合开始时消失

### -NextRound(Buff buff : int num)

下一回合开始时执行buff，num回合后效果消失

Buff分两类：

**（1）Buff(Range range,**[**Value**](../value/) **originValue;**[**VarifyWay**](../comparison/varifyway.md) **way;**[**Value**](../value/) **comparisonValue,Value value,Value GoalValue)**

修改某个数值

**（2）Buff(Global,Event event)**

执行某个事件

示例：

**下一回合开始将袋子里的一张牌放入手牌**

```csharp
NextRound(Global,DrawIgnoreLabel(0):1)
```

**下一回合时间刻度上限+1**

<pre class="language-csharp"><code class="lang-csharp"><strong>NextRound(Global,None,TimeLabelLimit,1:1)
</strong></code></pre>

### -NextDraw(Buff buff: int num)

下num抽，抽到的牌获得buff效果

在结算抽牌事件的时候，会先结算这个效果再结算抽牌的效果（如事件Draw、时间标签结算）

### -NextDrawPredictTimeExplode(Result result)

如果下一抽时间爆炸，则执行result效果（任意result效果）

### -ThisRoundPredictTimeExplode(Result result)

如果本回合时间爆炸，则执行result效果（任意result效果）

### -NextDrawMust(Comparison condition;int num)

下num抽必定是符合condition的卡，如果没有符合condition的卡，则正常抽卡

### -NextDrawMustPeak(Value peakValue;bool isMax;int num)

下num抽必定是peakValue最大/最小的牌

示例：

**下一次抽取必定为时间标签最小的牌**

<pre class="language-csharp"><code class="lang-csharp"><strong>NextDrawMustPeak(TimeLabel;false;1)
</strong></code></pre>

### -NextSpellPlayTwice()

下一张法术牌生效两次

## <mark style="color:orange;">Bag</mark>

### -BagIn(string name;int num;string result)

将num张名字为name的卡牌放入袋子中，并且对这些卡施加result效果（若没有效果可忽视第三个参数）

示例：BagIn(鸡蛋;1;SelfCard,EffectString,"YearEnd DestroyCard(SelfCard)")

### -BagInByType(string type;int num;string result)

从类型为type的卡牌中随机num张卡牌放入袋子中，并且对这些卡施加result效果（若没有效果可忽视第三个参数）

### -BagInCondition(string condition;int num;string result)

将满足condition的卡牌放入袋子中，并且对这些卡施加result效果（若没有效果可忽视第三个参数）

### -BagInOriginDew(int num)

将num张当前职业的露珠放入袋子

### -BagInCopy(Range goalRange)

将range的原始复制放入袋子中（range中只能有一张牌）

### -BagInDerivativeNoInsect(int num;int needLevel;string result)

将num张等级为level的衍生物（虫除外）放入袋子里，并且对这些卡施加result效果

needLevel只有在大于0时会生效，否则会无视level需求

### -BagBackBagNum(int num)

接下来打出的num张牌会回到袋子里（仅限有打出效果的非消耗牌）

### -DrawIgnoreLabel(int needTimeLabel;int maxValue;int num)

从袋子中时间标签大于needTimeLabel小于maxValue的牌中随机拿num张牌放入手牌，衍生物除外

### -DiscardHandCards(int num)

将手牌中的num张牌弃掉

### -LastDraw()

将袋子的一张牌放入手牌中\[衍生物除外]，本回合无法再抽牌

### **-TransferInsect(int num)**

转换袋子里的num张虫将其变为对应的虫菌，若袋子里没有虫则不会有事情发生

### -DrawMinTimeLabel()

将袋子里时间标签最小的牌放入手牌

### -PutToHandNoDerivative(int num)

将袋子中num张牌放入手牌中\[衍生物除外]

### -PutToHandByCondition(string condition;int num)

将袋子中num张符合condition条件的牌放入手牌中

### **-DestroyCard(GoalRange range)**

将range的卡牌销毁（仅限背包）

### **-BagInRandomBall(int num)**

随机放入蓝/黄/黑/白球中的num个，仅限于扭蛋机灾年使用

## <mark style="color:orange;">Land</mark>

### -ExpandLand()

扩展一个地块

### -AllGrow(**int num**)

全局生长**num**次

### **-RandomGrow(int num)**

随机生长num次

### -LandBackToBag(GoalRange range)

将range的所有卡牌（仅限地里）移回袋子中

### -LandBackToHand(GoalRange range)

将range的所有卡牌（仅限地里）移回手牌中

### **-CreateItemAround(string name;int num)**

在周围生成num个名字为name的物品

### **-CreateItemAroundAppoint(string name;int xoffset;int yoffset)**

在周围的某个方位生成名字为name的物品，若无空地或地块未激活则不生成

xoffset:-1表示左 1表示右

yoffset:-1表示下 1表示上

### -DestroyItem(GoalRange range)

将range的所有卡牌（仅限地里物品）销毁

### -DestroyItemWithNum(GoalRange range;num)

将range的num张卡牌（仅限地里物品）销毁，顺序选取num张

### **-TriggerItem(GoalRange range;**[**Trigger**](../effect/trigger.md) **trigger;int num)**

激活range（仅限地里物品）中所有卡牌的trigger效果num次

### -TransferCopy(GoalRange range;GoalRange goal)

将range的物品变为goal的原始复制（goal里只有一个物品）

range和goal都仅限于land

### -UpgradeRice(GoalRange range)

升级range里所有的稻子，稻子会升级为改良稻子，改良稻子会升级为高产稻子

### -CheckChicken()

检查地里是否有养鸡场有空位可以收养鸡，有的话则收养

## <mark style="color:orange;">Hand</mark>

### -UseCard()

打出自身（在手牌里才生效）

### -HandIn(string name;int num)

直接往手牌中生成num张名字为name的手牌

### -HandInCatogaryWithResult(string catogary;int num;SelfCard,string value,string goal)

直接往手牌中随机生成num张有value变化goal的类型为Type的卡牌

### -HandCardsReturnBag(string condition;int num)

把符合condition的num张手牌放入背包

如果num是-1，则代表无上限

### -DrawTwoDiscardOne()

抽取两张牌（衍生物除外），弃掉一张

## <mark style="color:orange;">Discard</mark>

### \[废弃]-DiscardBack(int num;int goal)

从弃牌堆选择num张牌回到goal

goal为0代表背包，1代表手牌

### -DiscardBackBagCondition(string condition;int num;string result;bool ignoreSelf)

从弃牌堆随机num张符合condition的卡牌，添加result效果后回到袋子（是否忽视自身）

### -DiscardBackHandCondition(string condition;int num;string result;bool ignoreSelf)

从弃牌堆随机num张符合condition的卡牌，添加result效果后回到手牌（是否忽视自身）

### -DiscardDestroy(string condition;int num)

将弃牌堆中符合condition的num张卡牌全部删除

如果num是-1，则代表无上限

### -ReDrawAll()

将所有手牌放入弃牌堆里，将弃牌堆里相同数量的牌放入手牌中（自身除外）

## <mark style="color:orange;">Pendant</mark>

### -DestroyPendant(int resetGain)

销毁挂件自身（必须由挂件调用触发）

resetGain：销毁后是否可以再次获得 1为可以，0为不可以

### -AddPendant(string name)

添加名称为Name的挂件（如果已获得此挂件，则无事发生）

### -ChangePendantByID(string id;string ValName;int value)

修改ID为id的挂件数值，valName为CountVal或者SpecialVal

### -ChangePendantByName(string name;string ValName;int value)

修改名称为name的挂件数值，valName为CountVal或者SpecialVal

## <mark style="color:orange;">Special</mark>

### -Buff(Range range,[Value](../value/) originValue;[VarifyWay](../comparison/varifyway.md) way;[Value](../value/) comparisonValue,Value value,Value GoalValue) <a href="#buffevent" id="buffevent"></a>

类似Filter，也接受复合条件，使用该事件时，Trigger必须为Buff

如果没有条件，则填写None

此处range可以是CardCollection，但此时，第二项condition必须是filter筛选卡组的

目前Buff函数只接受加减法变化，暂不支持乘除

GoalValue支持列表见[子级页面](buff-goalvalue.md)

示例：

**粑粑提供的生长值+1**

```csharp
Buff(Global,Filter(CardCollection'(Name'Is'粑粑)),EffectPar1,1)
```

**周围植物收成收益+2**

```csharp
Buff(Around,Type;Is;Plant,HarvestIncome,2)
```

### **-OpenOrePackage(int goal;int num)**

goal   0：手牌   1：背包

打开一个矿石包获得num个矿石

### -Probability(float P1%Result result1%float P2%Result result2%......)

有P1%的概率触发result1，有P2%的概率触发result2，一个probability函数中，所有概率值加起来最大为100

若概率总和不足100，有可能出现什么事件都不触发的情况

### -OpenPack(string Card/Pendant,string Big/Small,int guaranteeLevel)

打开卡牌/挂件包，第二个参数表示大包/小包，第三个参数表示有几级保底

### -OpenOneOfFourteen()

打开一个14选1的卡牌包

### -OpenBingoOrScratch(string type;int num)

打开num张bingo或者刮刮乐

