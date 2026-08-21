---
date: 2026-03-19
description: 學習如何將資源新增至專案，使用 Aspose.Tasks 的樹狀演算法計算任務持續時間，並在 .NET 中將資源指派給任務。
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 在 Aspose.Tasks 中使用樹狀演算法將資源新增至專案
url: /zh-hant/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 的樹狀演算法將資源新增至專案

## 簡介

在本教學中，您將透過 Aspose.Tasks for .NET 提供的強大樹狀演算法，了解 **如何將資源新增至專案**。我們將逐步說明如何建立工作階層、計算工作持續時間，以及將資源指派給工作——全部以清晰的步驟說明，您可以直接複製到自己的解決方案中。

## 快速答覆
- **樹狀演算法的功能是什麼？** 它會遍歷工作階層，以高效方式彙總工作值。  
- **本指南主要說明哪項操作？** 將資源新增至專案並更新工作總計。  
- **是否需要授權？** 生產環境使用需取得臨時或正式授權。  
- **可以在 .NET Core 中使用嗎？** 可以，Aspose.Tasks 支援 .NET Framework 與 .NET Core。  
- **實作需要多長時間？** 基本專案檔約需 10‑15 分鐘。

## 什麼是 Aspose.Tasks 中的「將資源新增至專案」？

將資源新增至專案即是建立 `Resource` 物件、定義其類型（例如 work），並透過 `ResourceAssignments` 將其連結至一或多個工作。這讓排程器能計算工作量、成本與整體專案持續時間。

## 為什麼在資源工作計算上使用樹狀演算法？

樹狀演算法只遍歷一次工作樹，將葉子工作之工作量累加至其彙總工作。此方法較逐一遍歷每個工作更有效率，尤其在階層深且規模大的專案中。它亦能確保彙總工作值與子工作保持同步。

## 先決條件

1. **Visual Studio** – 任一近期版本（2019、2022 或更新）。  
2. **Aspose.Tasks for .NET** – 從 [here](https://releases.aspose.com/tasks/net/) 下載。  
3. **基本的 C# 知識** – 您應熟悉類別、物件與簡單的 LINQ。

## 匯入命名空間

在 C# 專案中，匯入必要的命名空間以使用 Aspose.Tasks 功能：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

現在，讓我們將每個範例分解為多個步驟：

## 步驟 1：載入專案檔案

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

使用 `Project` 類別將專案檔載入記憶體。

## 步驟 2：定義工作階層

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

透過新增父工作與子工作來定義工作階層。

## 步驟 3：設定工作屬性（包含 **計算工作持續時間**）

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

此處我們透過將工作時數轉換為 `Duration` 物件，進而 **計算工作持續時間**，並推算完成日期。

## 步驟 4：新增資源（**將資源指派給工作**）

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

此程式碼片段 **將資源新增至專案**，並 **指派資源給工作**，讓排程器知道誰負責該工作。

## 步驟 5：套用樹狀演算法

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

初始化 `WorkAccumulator` 類別，並套用樹狀演算法以彙總整個階層的共通工作量。

## 步驟 6：更新工作工作量

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

根據彙總資訊更新各工作之工作量值。

## 常見問題與技巧

- **缺少行事曆設定：** 若完成日期異常，請在呼叫 `GetFinishDateByStartAndWork` 前確認專案行事曆已正確設定。  
- **資源類型不符：** 對於以工作量為基礎的資源，務必將 `Rsc.Type` 設為 `ResourceType.Work`；否則工作累加可能為零。  
- **專業提示：** 更新工作後，呼叫 `project.Save("UpdatedProject.mpp")` 以儲存變更。

## 結論

透過上述步驟，您現在已了解如何使用 Aspose.Tasks 的樹狀演算法 **將資源新增至專案**、**計算工作持續時間**，以及 **將資源指派給工作**。此方法簡化階層管理，並以最少程式碼確保彙總工作值的準確性。

## 常見問答

### Q1：什麼是 Aspose.Tasks for .NET？

A1：Aspose.Tasks for .NET 是一套強大的 API，讓開發者能以 C# 程式方式操作 Microsoft Project 檔案。

### Q2：我可以下載 Aspose.Tasks for .NET 的免費試用版嗎？

A2：可以，您可從 [here](https://releases.aspose.com/) 下載 Aspose.Tasks for .NET 的免費試用版。

### Q3：在哪裡可以找到 Aspose.Tasks for .NET 的文件？

A3：您可在 [here](https://reference.aspose.com/tasks/net/) 找到 Aspose.Tasks for .NET 的文件。

### Q4：如何取得 Aspose.Tasks for .NET 的支援？

A4：若需 Aspose.Tasks for .NET 的支援，可前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

### Q5：是否提供測試用的臨時授權？

A5：可以，您可從 [here](https://purchase.aspose.com/temporary-license/) 取得測試用的臨時授權。

## 常見問題

**Q：我可以將此方法套用於現有的大型專案檔嗎？**  
A：當然可以。樹狀演算法適用於任何 `Project` 實例，無論大小。

**Q：此演算法也會更新成本值嗎？**  
A：範例僅聚焦於工作量，但您可透過累加 `Tsk.Cost` 以類似方式擴充至成本。

**Q：支援哪些 .NET 版本？**  
A：Aspose.Tasks 支援 .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5 以上，以及 .NET 6 以上。

**Q：如何處理每個工作有多個資源的情況？**  
A：使用 `project.ResourceAssignments.Add(task, resource)` 為每個資源新增；累加器會自動將它們的工作量相加。

---

**最後更新：** 2026-03-19  
**測試環境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}