---
title: 掌握 Aspose.Tasks 中的專案時程視圖
linktitle: 在 Aspose.Tasks 中自訂時間軸視圖
second_title: Aspose.Tasks .NET API
description: 掌握 Aspose.Tasks for .NET 自訂時間軸視圖。透過根據您的專案需求量身定制的具有視覺吸引力的時間表來增強您的專案管理。
type: docs
weight: 13
url: /zh-hant/net/text-view-configuration/timeline-views/
---
## 介紹
創建具有視覺吸引力和資訊豐富的時間軸視圖對於有效的專案管理至關重要。 Aspose.Tasks for .NET 為自訂時間軸視圖提供了強大的解決方案，可讓您根據專案的特定需求自訂任務的顯示。在本逐步指南中，我們將探索如何使用 Aspose.Tasks 輕鬆建立和自訂時間軸視圖。
## 先決條件
在我們深入學習本教學之前，請確保您具備以下條件：
- C# 和 .NET 程式設計的基礎知識。
- 安裝了 .NET 函式庫的 Aspose.Tasks。如果沒有，請下載[這裡](https://releases.aspose.com/tasks/net/).
- 整合開發環境 (IDE)，例如 Visual Studio。
## 導入命名空間
確保在 C# 程式碼中導入必要的命名空間：
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## 第 1 步：初始化專案和時間軸視圖
首先初始化一個新專案和時間軸視圖：
```csharp
var project = new Project();
var view = new TimelineView();
```
## 第 2 步：設定時間軸視圖屬性
透過設定各種屬性來自訂時間軸視圖：
```csharp
view.DateFormat = DateFormat.DateDddDd;
view.DisplayOverlapped = true;
view.ShowPanZoom = true;
view.ShowTimescale = true;
view.ShowToday = true;
view.TextLinesCount = 2;
```
## 步驟3：顯示時間軸查看詳細信息
檢索有關時間軸視圖的資訊：
```csharp
Console.WriteLine("Show Dates: " + view.ShowDates);
```
## 第 4 步：將視圖新增至專案中
將自訂時間軸視圖新增至專案：
```csharp
project.Views.Add(view);
```
## 步驟5：將測試資料加入項目中
使用範例任務填充項目：
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Set(Tsk.Start, new DateTime(2020, 4, 29, 8, 0, 0));
task1.Set(Tsk.Duration, task1.ParentProject.GetDuration(24, TimeUnitType.Hour));
var task2 = project.RootTask.Children.Add("Task 2");
task2.Set(Tsk.Start, new DateTime(2020, 4, 29, 8, 0, 0));
task2.Set(Tsk.Duration, task1.ParentProject.GetDuration(40, TimeUnitType.Hour));
```
## 第 6 步：將項目另存為 PDF
將具有自訂時間軸視圖的項目另存為 PDF 檔案：
```csharp
project.Save("Your Document Directory/SetTimeScaleCount_out.pdf", SaveFileFormat.Pdf);
```
## 結論
恭喜！您已使用 Aspose.Tasks for .NET 成功自訂了時間軸視圖。這個功能強大的庫簡化了創建具有視覺吸引力的專案時間表的過程，從而增強了您的專案管理能力。
## 常見問題解答
### Aspose.Tasks 與其他 .NET 框架相容嗎？
是的，Aspose.Tasks 支援各種 .NET 框架，確保與您的開發環境相容。
### 我可以自訂時間軸視圖中各個任務的外觀嗎？
絕對地！ Aspose.Tasks 提供了自訂時間軸視圖中每個任務的外觀的靈活性。
### 在哪裡可以找到 Aspose.Tasks 的其他資源和支援？
參觀[Aspose.Tasks 文檔](https://reference.aspose.com/tasks/net/)取得綜合指南和[支援論壇](https://forum.aspose.com/c/tasks/15)尋求幫助。
### Aspose.Tasks 是否有免費試用版？
是的，您可以探索免費試用[這裡](https://releases.aspose.com/).
### 如何取得 Aspose.Tasks 的臨時許可證？
獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).