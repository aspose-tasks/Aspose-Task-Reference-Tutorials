---
title: 在 Aspose.Tasks 中管理任務
linktitle: 在 Aspose.Tasks 中管理任務
second_title: Aspose.Tasks .NET API
description: 探索使用 Aspose.Tasks for .NET 管理任務的綜合指南。學習新增、顯示分割零件、移動、取得/設定屬性等。
weight: 15
url: /zh-hant/net/task-table-management/managing-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中管理任務

## 介紹
如果您是 .NET 開發人員，希望有效管理專案中的任務，Aspose.Tasks for .NET 提供了一個強大的解決方案。本教學將指導您完成使用 Aspose.Tasks 管理任務的各個方面，並提供逐步說明和程式碼範例。無論您是新增任務、顯示拆分部分、在同一父級下移動任務、獲取/設定任務屬性、迭代任務分配、讀取任務基線或刪除任務，本指南都能滿足您的要求。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. Aspose.Tasks for .NET 函式庫：確保您已安裝 Aspose.Tasks for .NET 函式庫。你可以下載它[這裡](https://releases.aspose.com/tasks/net/).
2. 文檔目錄：設定儲存項目文檔的目錄。
## 導入命名空間
在您的 .NET 專案中，包含使用 Aspose.Tasks 所需的命名空間：
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. 將任務加入項目中
```csharp
//建立一個新項目
var project = new Project();
//新增任務
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
//保存項目
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. 顯示任務的分割部分
```csharp
//加載具有拆分任務的項目
var project = new Project(DataDir + "ViewSplitTasks.mpp");
//訪問任務
var task = project.RootTask.Children.GetById(4);
//顯示分割部分
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. 在同一父級下移動任務
```csharp
try
{
    //載入項目
    var project = new Project(DataDir + "MoveTask.mpp");
    //將 id 5 的任務移到 id 3 的任務前
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    //儲存修改後的項目
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. 取得/設定任務屬性
```csharp
//建立一個新項目
var project = new Project();
//新增任務並設定屬性
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
//收集並顯示任務屬性
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. 迭代任務的分配
```csharp
//載入帶有作業的項目
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
//收集並顯示任務分配
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. 讀取任務的基線
```csharp
//建立一個新項目
var project = new Project();
//新增任務並設定基線
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
//顯示任務基線持續時間
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. 刪除任務
```csharp
//建立一個新項目
var project = new Project();
//新增任務
var task = project.RootTask.Children.Add("Task");
//顯示刪除前後的任務數
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
//刪除任務
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## 結論
使用所提供的範例，在 Aspose.Tasks for .NET 中管理任務是一個無縫過程。無論您是經驗豐富的開發人員還是剛入門，結合這些技術都將增強您的專案管理能力。
## 經常問的問題
### Q：Aspose.Tasks 是否與所有 .NET 框架相容？
答：是的，Aspose.Tasks 支援各種.NET 框架，確保與您的開發環境相容。
### Q：如何取得 Aspose.Tasks 的臨時許可證？
答：您可以從以下地址獲得 30 天的臨時許可證：[這裡](https://purchase.aspose.com/temporary-license/).
### Q：在 Aspose.Tasks 中處理分割任務時有任何限制嗎？
 A：拆分任務是一個很強大的功能，詳細的文檔可以找到[這裡](https://reference.aspose.com/tasks/net/).
### Q：除了範例中顯示的內容之外，我還可以自訂任務屬性嗎？
答：當然！ Aspose.Tasks 為任務屬性提供了廣泛的自訂選項。查看文件以取得更多詳細資訊。
### Q：如何獲得 Aspose.Tasks 的支援？
答：訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以獲得社區支持和討論。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
