---
title: Aspose.Tasks .NET 中的逐步 WBS 程式碼配置
linktitle: 在 Aspose.Tasks 中配置 WBS 代碼掩碼
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks 探索 .NET 專案中的逐步 WBS 程式碼遮罩配置。輕鬆提升專案管理能力。
type: docs
weight: 14
url: /zh-hant/net/view-wbs-code-configuration/wbs-code-masks/
---
## 介紹
Aspose.Tasks for .NET 是一個功能強大的程式庫，可讓開發人員有效地操作 .NET 應用程式中的專案管理資料。在本教程中，我們將探索使用 Aspose.Tasks 配置工作分解結構 (WBS) 程式碼遮罩的過程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
-  Aspose.Tasks for .NET Library：從以下位址下載並安裝此程式庫[Aspose.Tasks for .NET 文檔](https://reference.aspose.com/tasks/net/).
- 開發環境：確保您設定了有效的 .NET 開發環境。
- 文件目錄：選擇系統上的一個目錄來儲存專案文件。
## 導入命名空間
在您的 .NET 專案中，包含使用 Aspose.Tasks 所需的命名空間：
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## 步驟1：建立專案實例
首先建立一個新的專案實例：
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## 步驟 2：定義 WBS 代碼定義
為您的專案設定 WBS 代碼定義：
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 步驟 3：新增 WBS 代碼掩碼
定義 WBS 程式碼遮罩並將其新增至專案：
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## 第 4 步：建立任務
將任務加入項目：
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## 第 5 步：重新計算
重新計算專案以確保正確應用 WBS 程式碼：
```csharp
project.Recalculate();
```
## 步驟 6：顯示 WBS 遮罩訊息
將有關 WBS 遮罩的資訊輸出到控制台：
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## 第 7 步：儲存項目
使用新增的 WBS 程式碼儲存項目：
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
恭喜！您已在 Aspose.Tasks 專案中成功配置了 WBS 程式碼遮罩。
## 結論
在本教程中，我們探索了使用 Aspose.Tasks for .NET 配置 WBS 程式碼遮罩的逐步過程。這個功能強大的程式庫為開發人員提供了一種無縫的方式來增強其 .NET 應用程式中的專案管理功能。

## 常見問題解答
### 我可以免費使用 Aspose.Tasks 嗎？
 Aspose.Tasks 提供免費試用版，您可以下載[這裡](https://releases.aspose.com/).
### 我可以在哪裡找到額外的支援？
訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以獲得社區支持。
### 我怎麼才能獲得臨時許可證？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 有詳細的文件嗎？
是的，有完整的文檔可供使用[這裡](https://reference.aspose.com/tasks/net/).
### 在哪裡可以購買 Aspose.Tasks？
購買 Aspose.Tasks[這裡](https://purchase.aspose.com/buy).