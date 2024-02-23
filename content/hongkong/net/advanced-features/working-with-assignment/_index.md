---
title: 在 Aspose.Tasks 中使用分配
linktitle: 在 Aspose.Tasks 中使用分配
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks 管理 .NET 中的專案分配。探索資源調度的不同輪廓。
type: docs
weight: 13
url: /zh-hant/net/advanced-features/working-with-assignment/
---
## 介紹

在本教程中，我們將探討如何在 Aspose.Tasks for .NET 中處理作業。分配在專案管理中至關重要，因為它們為任務分配資源，有助於安排和追蹤進度。我們將重點放在使用 Aspose.Tasks 產生具有各種輪廓的資源分配時間分段資料。

## 先決條件

在我們開始之前，請確保您符合以下先決條件：

1. 安裝 Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫：[下載連結](https://releases.aspose.com/tasks/net/).
2. 對 C# 和 .NET Framework 的基本了解：需要熟悉 C# 程式語言和 .NET 框架概念才能遵循。

## 導入命名空間

確保將必要的命名空間匯入到您的 C# 專案中：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## 第 1 步：建立專案和任務

讓我們先建立一個新項目並在其中新增一個任務。設定任務的開始日期、持續時間和完成日期：

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## 步驟 2：新增資源並指派給任務

接下來，將資源新增至專案並將其指派給先前建立的任務：

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## 步驟 3：產生具有不同輪廓的時間分段數據

現在，讓我們為資源分配產生具有不同輪廓的時間分段資料：

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## 第 4 步：更改輪廓並產生數據

我們可以更改等值線類型並相應地產生時間分段資料。這裡有些例子：

```csharp
//改變輪廓
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
//生成時間分段資料並列印
//對其他輪廓類型重複此步驟
```

## 結論

在本教程中，我們學習如何在 Aspose.Tasks for .NET 中處理作業。我們探索了產生具有各種輪廓的資源分配時間分段資料。這些知識在專案管理場景中非常有用。

## 常見問題解答

### Q1：我可以使用 Aspose.Tasks 在我的 .NET 應用程式中安排任務嗎？

A1：是的，Aspose.Tasks 為 .NET 應用程式中的任務排程和管理提供了全面的 API。

### Q2：Aspose.Tasks 有免費試用版嗎？

 A2：是的，您可以免費試用[這裡](https://releases.aspose.com/).

### Q3：Aspose.Tasks 中的任務或資源數量有限制嗎？

A3：Aspose.Tasks 不會對您可以在專案中管理的任務或資源的數量施加任何限制。

### Q4：我可以在Aspose.Tasks中自訂資源分配的輪廓嗎？

A4: 是的，如本教學所示範的，您可以根據您的專案要求設定各種輪廓，如海龜、鐘形、峰值等。

### Q5：在哪裡可以找到 Aspose.Tasks 相關查詢的支援？

 A5：您可以在[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)專家和社區成員積極參與討論。