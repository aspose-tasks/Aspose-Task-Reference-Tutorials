---
title: Aspose.Tasks 中的計算類型
linktitle: Aspose.Tasks 中的計算類型
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks 庫中的計算類型在 .NET 專案中自訂值計算。
type: docs
weight: 30
url: /zh-hant/net/advanced-features/calculation-type/
---
## 介紹

在本教程中，我們將探索 Aspose.Tasks for .NET 中的計算類型功能。 Aspose.Tasks 是一個功能強大的程式庫，可讓 .NET 開發人員使用 Microsoft Project 文件，而無需在其係統上安裝 Microsoft Project。計算類型可讓我們定義如何計算項目中的任務和摘要任務的值。

## 先決條件

在我們開始之前，請確保您符合以下先決條件：

1. C# 和 .NET 架構的基礎知識。
2. Visual Studio 安裝在您的系統上。
3. 安裝了 .NET 函式庫的 Aspose.Tasks。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).
4. 造訪 Aspose.Tasks for .NET 文件以供參考，可用[這裡](https://reference.aspose.com/tasks/net/).

## 導入命名空間

在深入研究範例之前，請確保導入必要的命名空間：

```csharp
using Aspose.Tasks;
using System;


```

## 第 1 步：建立一個新項目

首先，讓我們建立一個新的專案物件：

```csharp
var project = new Project();
```

## 第 2 步：新增任務

現在，讓我們為專案新增一個任務：

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## 步驟 3：定義擴充屬性的計算類型

我們將建立一個擴展屬性定義，並將計算類型設為公式：

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## 步驟 4：定義總計行的計算類型

接下來，我們將建立另一個擴充屬性定義，其中使用 Average 匯總類型計算摘要任務的值：

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## 結論

在本教程中，我們探討如何在 Aspose.Tasks for .NET 中使用計算類型。透過定義擴展屬性的計算類型，我們可以自訂項目內任務和摘要任務的值計算方式，提供更大的靈活性和控制力。

## 常見問題解答

### Q1：Aspose.Tasks 中的計算類型是什麼？

A1：Aspose.Tasks 中的計算類型決定如何計算項目內的任務和摘要任務的值，提供公式和總和等選項。

### Q2：如何設定擴充屬性的計算類型？

A2：您可以透過對應定義擴充屬性的 CalculationType 屬性來設定擴充屬性的計算類型。

### Q3：我可以為專案中的總計行自訂計算類型嗎？

A3：是的，Aspose.Tasks 可讓您指定總計行的計算類型，使您能夠根據您的要求自訂值計算。

### Q4：是否有不同的 Rollup Type 可用來摘要任務計算？

A4：是的，Aspose.Tasks 提供了 Average、Sum 和 Count 等各種 Rollup Type 來計算摘要任務的值。

### Q5：在哪裡可以找到更多關於 Aspose.Tasks for .NET 的資源？

 A5：您可以瀏覽以下網站上提供的文件和社群支援論壇：[適用於 .NET 的 Aspose.Tasks](https://reference.aspose.com/tasks/net/)以獲得全面的指導和幫助。