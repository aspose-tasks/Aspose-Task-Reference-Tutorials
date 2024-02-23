---
title: 處理 Aspose.Tasks 中的任務鏈接
linktitle: 處理 Aspose.Tasks 中的任務鏈接
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 在高效能管理專案任務連結的強大功能。請遵循我們的逐步指南來增強您的專案管理體驗。
type: docs
weight: 19
url: /zh-hant/net/task-table-management/task-link-collection/
---
## 介紹
歡迎閱讀有關在 Aspose.Tasks for .NET 中處理任務連結的逐步指南！任務連結在專案管理中發揮著至關重要的作用，它允許您在任務之間建立關係並創建依賴關係。在本教程中，我們將引導您完成使用 Aspose.Tasks 處理任務連結集合的過程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1.  Aspose.Tasks for .NET 函式庫：下載並安裝 Aspose.Tasks 函式庫。你可以找到圖書館[這裡](https://releases.aspose.com/tasks/net/).
2. 範例專案文件：準備一個範例專案文件（例如“SampleProject.mpp”）以遵循範例。
現在，讓我們開始吧！
## 導入命名空間
在您的 .NET 專案中，請確保匯入使用 Aspose.Tasks 所需的命名空間：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 第 1 步：載入項目並存取任務
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
//載入項目
var project = new Project(DataDir + "SampleProject.mpp");
//透過ID存取任務
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## 第 2 步：建立任務鏈接
將任務連結在一起以建立依賴關係：
```csharp
//使用 FinishToStart 依賴項連結任務
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## 第 3 步：列印任務鏈接
列印項目的任務連結：
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
//遍歷任務連結
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## 步驟 4：編輯任務鏈接
透過索引存取編輯任務連結：
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## 步驟 5：刪除任務鏈接
從項目中刪除所有任務連結：
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## 結論
恭喜！您已經成功學習如何處理 Aspose.Tasks for .NET 中的任務連結。這個綜合指南涵蓋了載入項目、建立任務連結、列印連結、編輯連結和刪除任務連結。
請隨意探索 Aspose.Tasks 提供的更多功能和功能，以增強您的專案管理體驗。
## 常見問題解答
### Aspose.Tasks 與所有版本的 .NET 相容嗎？
是的，Aspose.Tasks 旨在與所有版本的 .NET 無縫協作。
### 我可以使用 Aspose.Tasks 建立自訂任務連結類型嗎？
目前，Aspose.Tasks 支援標準任務連結類型，自訂連結類型不可用。
### 如何對 Aspose.Tasks 中的任務套用約束？
您可以使用下列方法套用約束`ConstraintType`的財產`Task`Aspose.Tasks 中的類別。
### Aspose.Tasks 可以處理的專案檔案的大小有限制嗎？
Aspose.Tasks 可以有效地處理大型專案文件，同時對效能的影響最小。
### 是否有 Aspose.Tasks 支援的社群論壇？
是的，您可以在以下位置找到支持並與社區互動[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).