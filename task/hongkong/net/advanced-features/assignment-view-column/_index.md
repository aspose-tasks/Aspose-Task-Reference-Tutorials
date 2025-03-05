---
title: Aspose.Tasks 中的自訂分配視圖列
linktitle: Aspose.Tasks 中的自訂分配視圖列
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中新增自訂分配視圖列以增強專案管理功能。
type: docs
weight: 16
url: /zh-hant/net/advanced-features/assignment-view-column/
---
## 介紹

在本教程中，我們將探索如何使用 Aspose.Tasks for .NET 為作業視圖新增自訂列。自訂列提供了靈活性，並允許您顯示與專案管理需求相關的附加資訊。

## 先決條件

在我們開始之前，請確保您具備以下條件：

1. C# 程式語言的基礎知識。
2. 安裝了 .NET 函式庫的 Aspose.Tasks。如果沒有的話可以下載[這裡](https://releases.aspose.com/tasks/net/).
3. 整合開發環境 (IDE)，例如 Visual Studio。

## 導入命名空間

首先，讓我們匯入必要的命名空間來存取建立自訂分配視圖列所需的類別和方法：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 第 1 步：載入項目

首先，使用以下命令載入您的專案文件`Project`班級：

```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## 第 2 步：建立電子表格儲存選項

接下來，建立一個實例`Spreadsheet2003SaveOptions`這允許我們自訂分配視圖列：

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## 第 3 步：定義自訂列

現在，透過建立一個實例來定義您的自訂列`AssignmentViewColumn`。此類別需要列名、寬度和委託函數來將賦值資料轉換為列文字：

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## 第 4 步：將自訂列新增至選項

將自訂列新增至已儲存選項的指派視圖列集合中：

```csharp
options.AssignmentView.Columns.Add(column);
```

## 第 5 步：迭代分配

迭代專案中的每個資源分配並顯示自訂列文字：

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## 第 6 步：使用自訂列儲存項目

最後，使用自訂分配視圖列儲存項目：

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## 結論

在本教程中，我們學習如何使用 Aspose.Tasks for .NET 新增自訂分配視圖列。自訂列可以靈活地顯示根據您的專案要求定制的附加信息，從而增強專案管理能力。

## 常見問題解答

### Q1：我可以在作業視圖中新增多個自訂列嗎？

 A1：是的，您可以透過建立額外的實例來新增多個自訂列`AssignmentViewColumn`並將它們添加到`Columns`收藏。

### Q2：是否有可用於常見分配欄位的預先定義轉換器？

A2：是的，Aspose.Tasks 為常見分配欄位提供了預先定義的轉換器，使提取自訂列的資料變得更加容易。

### 問題 3：我可以自訂自訂列的外觀，例如格式化文字或應用程式樣式嗎？

A3：是的，您可以透過修改寬度、字體和對齊方式等屬性來自訂自訂列的外觀。

### 問題 4：是否可以從分配視圖中刪除預設列？

 A4：是的，您可以透過將預設列從清單中排除來刪除它們`Columns`集合或將其寬度設為零。

### Q5：除了具有自訂列的電子表格之外，Aspose.Tasks 是否支援將項目匯出為其他格式？

A5：是的，Aspose.Tasks 支援將項目匯出為各種格式，例如 PDF、HTML 和 XML，從而提供多種項目報告選項。