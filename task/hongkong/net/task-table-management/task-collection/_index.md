---
title: 在 Aspose.Tasks 中管理任務集合
linktitle: 在 Aspose.Tasks 中管理任務集合
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 中高效率的任務集管理。從創作到編輯，輕鬆掌握專案管理。
type: docs
weight: 18
url: /zh-hant/net/task-table-management/task-collection/
---
## 介紹
如果您正在使用 .NET 深入研究專案管理領域，Aspose.Tasks 是您無縫處理任務集的首選解決方案。本教學將引導您完成有效管理任務集合的過程，確保您充分利用這個強大的函式庫。
## 先決條件
在我們深入學習本教程之前，請確保您符合以下先決條件：
- C# 程式語言的基礎知識。
- Visual Studio 安裝在您的電腦上。
- 下載 Aspose.Tasks for .NET 函式庫並在您的專案中引用。
## 導入命名空間
首先，讓我們在 C# 專案中導入必要的命名空間：
```csharp
	using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
這些命名空間提供對有效任務管理所需的基本類別和方法的存取。
現在，讓我們將教程分解為一系列步驟，以確保清晰和簡單。
## 步驟1：建立專案實例
```csharp
var project = new Project();
```
使用實例化一個新項目`Project`班級。
## 第 2 步：檢查任務收集準備情況
```csharp
Console.WriteLine("Is task collection read-only: " + project.RootTask.Children.IsReadOnly);
```
驗證任務集合是否是唯讀的。
## 第 3 步：建立任務
```csharp
var task1 = project.RootTask.Children.Add();
task1.Set(Tsk.Name, "Task 1");
//設定其他任務屬性，例如開始、持續時間和完成
//任務 2 和任務 3 的步驟類似
```
在專案中建立任務並設定其屬性。
## 第 4 步：列印專案任務
```csharp
foreach (var child in project.RootTask.Children)
{
    //列印任務詳細信息
    Console.WriteLine("Task name: " + child.Get(Tsk.Name));
    Console.WriteLine("Task start: " + child.Get(Tsk.Start));
    Console.WriteLine("Task duration: " + child.Get(Tsk.Duration));
    Console.WriteLine("Task finish: " + child.Get(Tsk.Finish));
    Console.WriteLine();
}
```
列印項目中每個任務的詳細資訊。
## 第5步：編輯任務
```csharp
var task1ToEdit = project.RootTask.Children.GetById(1);
task1ToEdit.Set(Tsk.Name, "Task 1 (Edited)");
var taskToEdit2 = project.RootTask.Children.GetByUid(2);
taskToEdit2.Set(Tsk.Name, "Task 2 (Edited)");
```
使用任務 ID 或 UID 編輯任務。
## 第 6 步：新增重複任務
```csharp
var parameters = new RecurringTaskParameters
{
    //設定重複任務參數
};
var recurring = project.RootTask.Children.Add(parameters);
Console.WriteLine("Task name: " + recurring.Get(Tsk.Name));
```
將重複任務新增至項目。
## 第 7 步：將集合轉換為列表
```csharp
List<Task> tasks = project.RootTask.Children.ToList();
foreach (var task in tasks)
{
    task.Delete();
}
```
將任務集合轉換為清單並對每個任務執行操作。
## 結論
透過本逐步指南，在 Aspose.Tasks for .NET 中管理任務集合變得輕而易舉。無論您是建立、編輯還是刪除任務，Aspose.Tasks 都可以讓您無縫地進行專案管理。
## 經常問的問題
### Aspose.Tasks 與 .NET Core 相容嗎？
是的，Aspose.Tasks 支援 .NET Core，讓您在跨平台應用程式中使用它。
### 我可以將專案任務匯出為不同的文件格式嗎？
絕對地！ Aspose.Tasks 提供多種匯出選項，包括 PDF、XLSX 和 MPP。
### 如何處理任務之間的依賴關係？
您可以使用以下命令設定任務依賴關係`TaskLink`由Aspose.Tasks提供的類別。
### 是否有 Aspose.Tasks 支援的社群論壇？
是的，您可以在以下位置找到支持並與社區互動：[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).
### 我可以獲得 Aspose.Tasks 的臨時許可證嗎？
是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).