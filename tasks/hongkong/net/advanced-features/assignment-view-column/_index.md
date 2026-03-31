---
date: 2026-03-19
description: 了解如何在使用 Aspose.Tasks for .NET 將專案匯出為 XML 時，新增多個自訂欄位並設定自訂欄寬。
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 在 Aspose.Tasks 的指派檢視中新增多個自訂欄位
url: /zh-hant/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中為指派檢視新增多個自訂欄位

## 簡介

在本教學中，您將學會 **如何在 Aspose.Tasks for .NET 的指派檢視中新增多個自訂欄位**。自訂欄位讓您能在匯出報表中直接呈現額外資料——例如備註、成本或自訂旗標。完成本指南後，您將能設定自訂欄位寬度、將專案匯出為 XML，並依照專案管理需求調整檢視。

## 快速解答
- **我可以達成什麼？** 在自訂欄位中顯示任何指派資料，並控制其外觀。  
- **支援哪種格式？** 使用 `Spreadsheet2003SaveOptions` 將專案匯出為 XML（或其他格式）。  
- **需要授權嗎？** 需要，有效的 Aspose.Tasks 授權在正式環境中是必須的。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **可以新增多少欄位？** 無限制，只要建立額外的 `AssignmentViewColumn` 實例即可。

## 什麼是多個自訂欄位？
多個自訂欄位是使用者自行定義的欄位，會與預設的指派欄位一起出現在專案儲存或匯出時。它們讓您彈性呈現 `ResourceAssignment` 物件的任何屬性，例如自訂備註、成本代碼或計算值。

## 為何要在指派檢視中新增多個自訂欄位？
- **增強報告功能：** 包含內建欄位未涵蓋的專案特定資訊。  
- **提升決策品質：** 利害關係人可直接看到所需資料，免於深入原始檔案。  
- **一致的格式化：** 控制欄寬與文字轉換，確保輸出清晰易讀。  

## 先決條件

在開始之前，請確保您已具備：

1. 基本的 C# 程式語言知識。  
2. 已安裝 Aspose.Tasks for .NET 套件。如未安裝，可於 **[此處](https://releases.aspose.com/tasks/net/)** 下載。  
3. 如 Visual Studio 等整合開發環境 (IDE)。  

## 步驟說明

### 步驟 1：匯入命名空間
首先，匯入提供專案與視覺化所需類別的命名空間。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### 步驟 2：載入專案
建立 `Project` 實例並載入既有的 MPP 檔案。

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### 步驟 3：建立 Spreadsheet 儲存選項
實例化 `Spreadsheet2003SaveOptions` —— 這個物件讓我們在匯出前自訂指派檢視。

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### 步驟 4：定義自訂欄位
為每筆想要顯示的資料建立 `AssignmentViewColumn`。以下範例加入寬度為 200 點的 **Notes** 欄位。

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**提示：** 若要新增 *多個* 自訂欄位，只需以不同的欄位名稱與委派邏輯重複此步驟，然後將每個實例加入 `options.AssignmentView.Columns`。

### 步驟 5：將自訂欄位加入選項
將欄位（或多個欄位）加入指派檢視的 `Columns` 集合。

```csharp
options.AssignmentView.Columns.Add(column);
```

### 步驟 6：遍歷指派（可選除錯）
您可以遍歷指派以驗證自訂欄位文字是否正確產生。

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

### 步驟 7：以自訂欄位儲存專案
最後，儲存專案。範例儲存為 XML，但您也可以選擇任何支援的格式。

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## 如何使用自訂欄位將專案匯出為 XML？
當您以已設定好的 `Spreadsheet2003SaveOptions` 呼叫 `project.Save` 時，Aspose.Tasks 會將專案資料（包括所有 **多個自訂欄位**）寫入指定的 XML 檔案。這讓您能輕鬆將豐富的專案資訊分享給其他系統或利害關係人。

## 設定自訂欄位寬度以提升可讀性
`AssignmentViewColumn` 建構式的第二個參數控制欄位寬度（以點為單位）。請依預期文字長度調整此數值。例如，寬度 **300** 適合較長的備註，而 **100** 足以容納短旗標。

## 常見問題與解決方案
- **欄位文字顯示空白：** 確認 delegate 回傳字串，且底層指派屬性（例如 `Asn.NotesText`）已填寫。  
- **匯出檔案中未顯示欄位：** 在呼叫 `Save` 前，確認 `options.AssignmentView.Columns` 已包含自訂欄位。  
- **欄寬似乎被忽略：** 某些匯出格式有自己的版面規則；XML 會遵守欄寬設定，但 PDF/HTML 可能需要額外樣式。

## 常見問與答

### Q1：我可以在指派檢視中新增多個自訂欄位嗎？
**A：** 可以，只需建立額外的 `AssignmentViewColumn` 物件，並將每個物件加入 `options.AssignmentView.Columns`。

### Q2：是否有預先定義的轉換器可用於常見的指派欄位？
**A：** 有，Aspose.Tasks 提供內建的轉換器，讓您無需自行撰寫委派即可輕鬆取得多數標準欄位資料。

### Q3：我可以自訂自訂欄位的外觀，例如文字格式或樣式嗎？
**A：** 當然可以。除了設定寬度外，您還能透過欄位的樣式選項調整字型、對齊方式及其他視覺屬性。

### Q4：是否可以從指派檢視中移除預設欄位？
**A：** 可以，透過從 `Columns` 集合中移除預設欄位，或將其寬度設為零來排除。

### Q5：Aspose.Tasks 是否支援將專案匯出至除試算表外的其他格式，同時保留自訂欄位？
**A：** 支援，Aspose.Tasks 可匯出為 PDF、HTML、XML 等多種格式，且會保留自訂欄位的定義。

---

**最後更新：** 2026-03-19  
**測試環境：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}