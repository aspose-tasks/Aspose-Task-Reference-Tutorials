---
date: 2026-03-24
description: 學習如何在 Aspose.Tasks for .NET 中設定計算，並提供計算彙總值、定義計算公式以及配置滾動彙總的範例。
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中設定計算類型
url: /zh-hant/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中設定計算類型

## 介紹

如果您需要為 Microsoft Project 檔案中的任務與彙總列 **設定計算** 規則，本教學將示範如何使用 Aspose.Tasks for .NET 完成此操作。我們會一步步走過完整的 **計算類型範例**，示範如何 **計算彙總值**，並說明如何 **定義計算公式** 與 **設定彙總彙總** 以用於延伸屬性。完成後，您將能自信地將任務加入專案、設定自訂計算邏輯，並控制彙總行為。

## 快速解答
- **主要目的為何？** 控制在 Project 檔案中任務與彙總值的計算方式。  
- **使用哪個 API 類別？** `ExtendedAttributeDefinition` 搭配 `CalculationType` 與 `SummaryRowsCalculationType`。  
- **可以使用公式嗎？** 可以 – 設定 `CalculationType = CalculationType.Formula` 並提供公式字串。  
- **如何彙總彙總值？** 使用 `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` 並指定 `RollupType`（例如 `Average`）。  
- **需要授權嗎？** 正式環境使用需具備有效的 Aspose.Tasks 授權。

## 什麼是計算類型以及如何設定計算？

`CalculationType` 告訴 Aspose.Tasks 如何計算延伸屬性的值。您可以選擇靜態值、公式，或讓程式庫從子任務彙總值。正確設定計算對於讓專案自動遵循自訂業務規則、避免手動更新至關重要。

## 為何使用計算類型來計算彙總值？

當專案包含彙總任務時，通常需要彙總列顯示聚合資料（例如總成本、平均工期）。透過 `SummaryRowsCalculationType` 與 `RollupType` 設定 **計算彙總值**，Aspose.Tasks 能在您修改個別任務時自動保持這些聚合資料同步。

## 前置條件

在開始之前，請確保您已具備：

1. 具備 C# 及 .NET 框架的基礎知識。  
2. 機器上已安裝 Visual Studio（任一較新版本）。  
3. 已安裝 Aspose.Tasks for .NET 程式庫 – 可從 [here](https://releases.aspose.com/tasks/net/) 下載。  
4. 取得官方 Aspose.Tasks for .NET 文件作為參考，可於 [here](https://reference.aspose.com/tasks/net/) 瀏覽。

## 匯入命名空間

在深入範例之前，請先匯入必要的命名空間：

```csharp
using Aspose.Tasks;
using System;
```

## 步驟 1：建立新 Project

首先，我們建立一個空的 `Project` 物件，以容納任務與自訂屬性。

```csharp
var project = new Project();
```

## 步驟 2：將任務加入 Project

現在我們 **加入任務專案** 資料，建立一個簡單任務，設定開始日期，並給予一天的工期。

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## 步驟 3：為延伸屬性定義計算類型（公式範例）

此處我們建立一個延伸屬性定義，其值由公式計算而得。這示範了一個 **計算類型範例**，並說明如何 **定義計算公式**。

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## 步驟 4：為彙總列定義計算類型（設定彙總）

接著，我們建立另一個延伸屬性定義，告訴 Aspose.Tasks 使用 *Average* 彙總類型來 **設定彙總**。這是 **計算彙總值** 的典型做法，適用於成本、工時或自訂欄位。

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## 常見問題與疑難排解

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| 公式回傳 `null` | 公式中的欄位參照不正確 | 確認方括號內的欄位名稱（例如 `[Start]` 而非 `[stARt]`）。 |
| 彙總列顯示 0 | 未設定 `SummaryRowsCalculationType` 或 `RollupType` 錯誤 | 確保 `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` 並選擇適當的 `RollupType`。 |
| 新增屬性後專案無法載入 | 屬性定義與任務使用不匹配 | 在指派屬性給任何任務之前 **先** 新增屬性定義。 |

## 結論

在本教學中，我們從建立簡單任務到定義公式與彙總兩種計算類型，完整說明了 **如何在 Aspose.Tasks for .NET 中設定計算規則**。掌握這些設定後，您即可精細控制 **計算彙總值**，讓專案分析更豐富，免除手動試算表的繁瑣。

## 常見問答

### Q1：什麼是 Aspose.Tasks 中的計算類型？

A1：Aspose.Tasks 的計算類型決定在專案內任務與彙總任務的值如何計算，提供公式與彙總等選項。

### Q2：如何為延伸屬性設定計算類型？

A2：您可以透過設定延伸屬性的 `CalculationType` 屬性來指定相應的計算類型。

### Q3：我可以自訂專案中彙總列的計算類型嗎？

A3：可以，Aspose.Tasks 允許您為彙總列指定計算類型，依需求調整值的計算方式。

### Q4：彙總任務計算有不同的彙總類型嗎？

A4：有，Aspose.Tasks 提供多種彙總類型，如 Average、Sum、Count 等，用於計算彙總任務的值。

### Q5：在哪裡可以找到更多 Aspose.Tasks for .NET 的資源？

A5：您可以於 [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) 的文件與社群支援論壇中取得完整指引與協助。

---

**Last Updated:** 2026-03-24  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}