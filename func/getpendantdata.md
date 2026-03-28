---
description: 获取挂件数据
---

# GetPendantData

## 规范

GetPendantData(string ID/Name : string goal : string valueName)

返回值：int

仅支持获取类型为int整数的数据

可以通过ID或者名称获取挂件的CountVal或SpecialVal

如果不存在该挂件默认返回0

示例：

**ID为P-Neutral-6的CountVal**

```csharp
GetPendantData(ID : P-Neutral-6 : CountVal)
```

**挂件\[稳定水源]的SpecialVal**

```csharp
GetPendantData(Name : 稳定水源 : SpecialVal)
```
