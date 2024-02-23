---
title: 在 Aspose.Tasks 中處理 MS Project 分割部分
linktitle: 處理 Aspose.Tasks 中的分割部分
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 有效地處理 MS Project 分割部分。增強您的專案管理工作流程。
type: docs
weight: 18
url: /zh-hant/net/rate-recurring-tasks/split-parts/
---

## 介紹
使用 Aspose.Tasks for .NET 時，管理 MS Project 分割部分可能是專案管理的重要面向。在本教程中，我們將探索如何使用逐步指導有效處理分割零件。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. 安裝 Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET[網站](https://releases.aspose.com/tasks/net/).
   
2. 對 C# 的基本了解：熟悉 C# 程式語言將會很有幫助。

## 導入命名空間
在您的 C# 程式碼中，確保導入必要的命名空間：
```csharp
    using Aspose.Tasks;
    using System;
    
```

## 步驟1：建立專案實例
```csharp
var project = new Project();
```
建立一個新實例`Project`班級。
## 第 2 步：設定專案開始和完成日期
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
設定專案的開始和完成日期。
## 第 3 步：新增任務
```csharp
var task = project.RootTask.Children.Add("Task1");
```
新增任務至項目。
## 步驟 4：設定任務屬性
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
設定任務的手動狀態、開始日期和持續時間等屬性。
## 步驟 5：新增資源分配
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
將資源分配加入任務。
## 第 6 步：設定分配屬性
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
設定作業的開始日期、工作和完成日期等屬性。
## 第 7 步：產生時間分段數據
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
根據專案日曆產生任務的時間分段資料。
## 第 8 步：拆分任務
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
在規定的時間內將任務分成多個部分。
## 第 9 步：迭代分割部分
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
迭代任務的各個部分並列印它們的開始和完成日期。

## 結論
在 Aspose.Tasks for .NET 中有效處理 MS Project 分割部分對於專案管理效率至關重要。透過遵循本教學中概述的步驟，您可以無縫管理分割任務並增強專案管理工作流程。
## 常見問題解答
### Q：我可以將 Aspose.Tasks for .NET 與其他 .NET 框架一起使用嗎？
答：是的，Aspose.Tasks for .NET 與各種 .NET 框架相容，包括 .NET Core 和 .NET Standard。
### Q：Aspose.Tasks for .NET 有沒有免費試用版？
答：是的，您可以從以下位置獲得免費試用[這裡](https://releases.aspose.com/).
### Q：Aspose.Tasks for .NET 支援資源管理嗎？
答：是的，Aspose.Tasks for .NET 可讓您有效管理專案資源。
### Q：我可以使用 Aspose.Tasks for .NET 自訂專案行事曆嗎？
答：當然，您可以根據您的專案需求自訂專案日曆。
### Q：在哪裡可以找到對 Aspose.Tasks for .NET 的支援？
答：您可以在以下網站上找到支援和協助：[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).