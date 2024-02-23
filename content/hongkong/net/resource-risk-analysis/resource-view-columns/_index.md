---
title: 自訂 Aspose.Tasks 中的 MS Project 資源視圖列
linktitle: 在 Aspose.Tasks 中自訂資源視圖列
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 有效地自訂 MS Project 資源視圖列。建立自訂視圖以實現更好的專案管理。
type: docs
weight: 17
url: /zh-hant/net/resource-risk-analysis/resource-view-columns/
---
## 介紹
Aspose.Tasks for .NET 是一個功能強大的 API，可讓開發人員以程式設計方式處理 Microsoft Project 檔案。專案管理中的常見任務是自訂視圖以顯示特定資訊。在本教程中，我們將探索如何使用 Aspose.Tasks for .NET 自訂 MS Project 資源視圖列。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1.  Aspose.Tasks for .NET Library：您可以從以下位置下載它[這裡](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 檔案：準備一個範例 MS Project 檔案以進行測試。
3. 開發環境：採用.NET架構建置的開發環境。
## 導入命名空間
首先，讓我們將必要的命名空間匯入到我們的專案中：
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## 第 1 步：載入專案文件
使用 Aspose.Tasks API 載入 MS Project 檔案：
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## 第 2 步：取得資源並定義選項
接下來，取得要自訂其視圖列的資源並定義 PDF 儲存選項：
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## 第 3 步：定義自訂列
現在，為資源視圖定義自訂列。您可以指定各種字段，甚至使用委託進行自訂計算：
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## 第 4 步：迭代列
迭代定義的列並顯示它們的屬性：
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## 第 5 步：儲存自訂視圖
最後，設定自訂視圖並將其儲存為 PDF 文件：
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
透過執行這些步驟，您可以使用 Aspose.Tasks for .NET 有效率地自訂 MS Project 資源視圖列。
## 結論
自訂 MS Project 資源視圖列對於顯示根據專案需求自訂的相關資訊至關重要。透過 Aspose.Tasks for .NET，此任務變得簡單且高效，讓您可以輕鬆建立自訂視圖。
## 常見問題解答
### 除了資源之外，我可以自訂其他元素的視圖嗎？
是的，Aspose.Tasks 還允許自訂任務、指派和其他項目元素。
### Aspose.Tasks 是否支援以 PDF 以外的格式儲存視圖？
是的，您可以以各種格式儲存視圖，例如 XLSX、HTML 和映像。
### 是否可以將格式套用於自訂視圖？
當然，Aspose.Tasks 提供了廣泛的格式化選項來增強自訂視圖的外觀。
### 我可以根據更改的項目資料動態更新自訂視圖嗎？
是的，只要基礎專案資料發生變化，您就可以更新並重新產生自訂視圖。
### Aspose.Tasks支援跨平台開發嗎？
Aspose.Tasks for .NET 主要針對 .NET 平台，但也有 Java 和其他平台的版本。