---
title: 使用 Aspose.Tasks 進行高效率的 MS 專案任務分組
linktitle: 在 Aspose.Tasks 中將任務分組
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 對 Microsoft Project 任務進行有效分組。
type: docs
weight: 25
url: /zh-hant/net/tasks-project-management/grouping-tasks/
---
## 介紹
在 Microsoft Project 中管理任務有時可能具有挑戰性，尤其是在有效率地組織任務時。 Aspose.Tasks for .NET 透過提供有效的分組任務功能，為此提供了全面的解決方案。在本教程中，我們將探討如何使用 Aspose.Tasks for .NET 將 MS Project 任務分組。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1.  Aspose.Tasks for .NET 函式庫：下載並安裝 Aspose.Tasks for .NET 函式庫[這裡](https://releases.aspose.com/tasks/net/).
2. 開發環境：確保您已設定 .NET 開發環境。
3. C# 基礎：熟悉 C# 程式語言將會很有幫助。

## 導入命名空間
首先，您需要將必要的命名空間匯入到您的 C# 專案中才能使用 Aspose.Tasks 功能：
```csharp
    using Aspose.Tasks;
    using System;
    
```
## 第 1 步：載入 MS 專案文件
首先使用以下程式碼載入 MS Project 檔案：
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## 第 2 步：訪問任務組
接下來，讓我們訪問專案中的任務組：
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
```
## 步驟 3：檢索群組資訊
現在，檢索有關任務組的資訊：
```csharp
Console.WriteLine("Task Group Uid: " + group.Uid);
Console.WriteLine("Task Group Index: " + group.Index);
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Is Task Group Maintain Hierarchy?: " + group.MaintainHierarchy);
Console.WriteLine("Is Task Group Show In Menu?: " + group.ShowInMenu);
Console.WriteLine("Is Task Group Show Summary?: " + group.ShowSummary);
```
## 第 4 步：訪問群組標準
存取為任務群組設定的條件：
```csharp
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
## 第 5 步：檢索標準資訊
檢索有關每個標準的詳細資訊：
```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Task Criterion Field: " + criterion.Field);
    Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
    Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
    Console.WriteLine("Task Criterion Pattern: " + criterion.Pattern);
    if (group == criterion.ParentGroup)
    {
        Console.WriteLine("Parent Group is equal to task Group.");
    }
    Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
    Console.WriteLine("Font Size: " + criterion.Font.Size);
    Console.WriteLine("Font Style: " + criterion.Font.Style);
    Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
}
```
透過執行這些步驟，您可以使用 Aspose.Tasks for .NET 有效地將 MS Project 任務進行分組，從而增強專案資料的組織和管理。

## 結論
總之，Aspose.Tasks for .NET 提供了對 MS Project 任務進行分組的強大功能，從而可以更好地組織和管理專案資料。透過遵循本教學中概述的步驟，您可以在 .NET 應用程式中有效地利用這些功能。
## 常見問題解答
### 我可以根據自訂標準對任務進行分組嗎？
是的，您可以使用 Aspose.Tasks for .NET 根據您的特定要求定義自訂任務分組標準。
### Aspose.Tasks 是否支援不同版本的 MS Project 檔案？
是的，Aspose.Tasks 支援各種版本的 MS Project 文件，確保相容性和無縫整合。
### Aspose.Tasks for .NET 有沒有試用版？
是的，您可以從以下位置取得 Aspose.Tasks for .NET 的免費試用版：[這裡](https://releases.aspose.com/).
### 我可以自訂分組任務的外觀嗎？
當然，Aspose.Tasks 提供了自訂分組任務外觀的選項，包括儲存格顏色、字體和樣式。
### 在哪裡可以找到對 Aspose.Tasks for .NET 的支援？
您可以在 Aspose.Tasks for .NET 中找到支援和協助[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).