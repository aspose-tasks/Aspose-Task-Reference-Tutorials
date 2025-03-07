---
title: 在 Aspose.Tasks 中使用樹演算法
linktitle: 在 Aspose.Tasks 中使用樹演算法
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks 的樹演算法有效操作 .NET 專案中的任務層次結構。
weight: 13
url: /zh-hant/net/advanced-concepts/tree-algorithm/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中使用樹演算法

## 介紹

Aspose.Tasks for .NET 提供了強大的功能來處理專案管理任務、資源和時間表。其中一項功能是樹演算法，它允許使用者有效地操作任務層次結構。在本教程中，我們將探索如何利用 Aspose.Tasks for .NET 中的樹演算法來收集專案中的常見工作並更新工作值。

## 先決條件

在我們開始之前，請確保您具備以下先決條件：

1. Visual Studio：確保您的系統上安裝了 Visual Studio。
2.  Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET[這裡](https://releases.aspose.com/tasks/net/).
3. 對 C# 的基本了解：需要熟悉 C# 程式語言才能跟隨範例。

## 導入命名空間

在您的 C# 專案中，匯入必要的命名空間以使用 Aspose.Tasks 功能：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

現在，讓我們將每個範例分解為多個步驟：

## 第 1 步：載入專案文件

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

使用以下命令將項目檔案載入到記憶體中`Project`班級。

## 第 2 步：定義任務層次結構

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

透過新增父任務和子任務來定義任務層次結構。

## 步驟 3：設定任務屬性

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

設定任務的開始日期、持續時間和完成日期等屬性。

## 第四步：新增資源

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

將資源新增至專案並根據需要將其指派給任務。

## 第5步：應用樹演算法

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

初始化`WorkAccumulator`類別並應用樹演算法來收集共同的工作。

## 第 6 步：更新任務工作

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

根據收集的資訊更新任務的工作值。

## 結論

在本教程中，我們學習如何利用 Aspose.Tasks for .NET 中的樹演算法來有效地操作任務層次結構。透過遵循逐步指南，您可以有效地管理專案中的任務和資源。

## 常見問題解答

### Q1：什麼是 Aspose.Tasks for .NET？

A1：Aspose.Tasks for .NET 是一個功能強大的 API，允許開發人員使用 C# 以程式方式操作 Microsoft Project 檔案。

### 問題 2：我可以下載 Aspose.Tasks for .NET 的免費試用版嗎？

 A2：是的，您可以從以下位置下載 Aspose.Tasks for .NET 的免費試用版：[這裡](https://releases.aspose.com/).

### Q3：在哪裡可以找到 Aspose.Tasks for .NET 的文件？

 A3：您可以找到 Aspose.Tasks for .NET 的文檔[這裡](https://reference.aspose.com/tasks/net/).

### Q4：如何獲得 Aspose.Tasks for .NET 支援？

 A4：有關 Aspose.Tasks for .NET 的支持，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).

### Q5：是否有可用於測試目的的臨時許可證？

 A5：是的，您可以從以下位置取得用於測試目的的臨時許可證：[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
