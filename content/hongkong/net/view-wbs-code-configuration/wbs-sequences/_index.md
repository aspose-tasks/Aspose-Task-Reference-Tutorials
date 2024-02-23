---
title: 使用 Aspose.Tasks for .NET 掌握 WBS 序列
linktitle: 在 Aspose.Tasks 中定義 WBS 序列
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 增強您的專案管理能力 – 無縫定義 WBS 序列並輕鬆提高效率。 #Aspose #Tasks #MS 項目
type: docs
weight: 16
url: /zh-hant/net/view-wbs-code-configuration/wbs-sequences/
---
## 介紹
您是否正在開發專案管理應用程式並需要一個強大的工具來處理工作分解結構 (WBS) 序列？ Aspose.Tasks for .NET 是您的最佳選擇，它是一個功能強大的函式庫，可以簡化專案管理任務。在本教程中，我們將引導您逐步完成定義 WBS 序列的過程。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- [下載並安裝 Aspose.Tasks for .NET](https://releases.aspose.com/tasks/net/)
- C# 程式設計基礎知識
- 為.NET專案設定的開發環境
## 導入命名空間
在您的 C# 程式碼中，請確保包含必要的命名空間以利用 Aspose.Tasks 的功能。在腳本的開頭加入以下內容：
```csharp
    
    using Aspose.Tasks.Saving;
```
## 定義 WBS 序列 - 逐步指南
## 第 1 步：設定項目
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project();
```
## 步驟 2：設定 WBS 代碼定義
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 步驟 3：定義 WBS 代碼掩碼
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
## 步驟 4：將任務加入專案中
```csharp
var tsk = project.RootTask.Children.Add("Task 1");
tsk.Children.Add("Task 2");
```
## 第 5 步：重新計算項目數據
```csharp
project.Recalculate();
```
## 第 6 步：儲存項目
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
恭喜！您已使用 Aspose.Tasks for .NET 在專案中成功定義了 WBS 序列。
## 結論
管理 WBS 序列對於有效的專案管理至關重要，而 Aspose.Tasks for .NET 可以無縫地完成此任務。透過執行這些簡單的步驟，您可以增強專案管理應用程式中的 WBS 功能。
## 經常問的問題
### Aspose.Tasks 與 .NET Core 相容嗎？
是的，Aspose.Tasks 支援 .NET Core，讓您可以建立跨平台應用程式。
### 我可以進一步自訂 WBS 程式碼格式嗎？
絕對地！ Aspose.Tasks 提供了根據您的專案需求定義 WBS 程式碼的靈活性。
### 有試用版嗎？
是的你可以[下載免費試用版](https://releases.aspose.com/)在購買前探索功能。
### 我如何獲得 Aspose.Tasks 的社群支持？
訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)與社區聯繫並尋求協助。
### 可以使用臨時許可證嗎？
是的，您可以獲得[臨時執照](https://purchase.aspose.com/temporary-license/)用於測試目的。