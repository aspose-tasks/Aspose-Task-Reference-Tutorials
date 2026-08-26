---
date: 2026-03-24
description: 了解如何在 Aspose.Tasks for .NET 中設定計算模式，包括自動、手動以及無計算模式，以管理任務相依性。
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks for .NET 中設定計算模式
url: /zh-hant/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks for .NET 中設定計算模式

## 簡介

Aspose.Tasks for .NET 是一個功能強大的 API，可讓您以程式方式處理 Microsoft Project 檔案。您將會遇到的最重要設定之一是 **calculation mode**（計算模式），它控制任務日期與專案排程的更新方式。在本教學中，您將學習 **如何設定計算** 模式，探索 **automatic calculation mode**（自動計算模式）、**manual calculation mode**（手動計算模式）以及 **none calculation mode**（無計算模式），並了解這些選項如何影響 **管理任務相依性**、**建立專案開始日期** 與 **連結任務完成‑開始** 關係。

## 快速解答
- **什麼是計算模式？** 它決定任務日期是自動、手動，還是根本不重新計算。  
- **為什麼使用手動計算模式？** 讓您完全掌控排程何時重新整理，適用於大量更新的情況。  
- **預設是哪種模式？** 自動計算模式，會在變更後立即更新日期。  
- **我可以在執行時變更模式嗎？** 可以——只需在 `Project` 物件上設定 `CalculationMode` 屬性。  
- **需要授權嗎？** 生產環境必須使用有效的 Aspose.Tasks 授權。

## 什麼是 Aspose.Tasks 中的「設定計算」？

設定計算模式非常簡單，只需將列舉值指派給 `Project.CalculationMode` 屬性。此列舉提供三種選項：`Automatic`、`Manual` 與 `None`。選擇適當的模式取決於您的工作流程——是需要即時更新、批次處理，或是完整的控制權。

## 先決條件

在開始之前，請確保您已具備以下條件：

1. **Visual Studio** – 任意較新的版本（2019、2022 或更新）。  
2. **Aspose.Tasks for .NET** – 從 [here](https://releases.aspose.com/tasks/net/) 下載並安裝程式庫。  
3. **基本的 C# 知識** – 您應該能熟悉建立主控台應用程式以及使用 NuGet 套件。

## 匯入命名空間

在開始使用 Aspose.Tasks for .NET 之前，先匯入必要的命名空間：

```csharp
using Aspose.Tasks;
using System;
```

## 如何設定計算模式

以下提供每種計算模式的逐步範例。程式碼區塊保持原樣；說明文字已為清晰起見作擴充說明。

### 套用自動計算模式

自動模式會在您修改任務或連結時即時重新計算日期。

#### 步驟 1：建立新的 Project 實例

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### 步驟 2：設定專案開始日期並新增任務

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### 步驟 3：連結任務（完成‑開始）

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### 步驟 4：驗證重新計算的日期

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### 套用手動計算模式

手動模式會停用自動更新，讓您在強制重新計算前先批次處理變更。

#### 步驟 1：建立新的 Project 實例

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### 步驟 2：設定專案開始日期並新增任務

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### 步驟 3：驗證任務屬性

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### 步驟 4：連結任務並驗證日期（不會自動重新計算）

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### 套用無計算模式

無計算模式會關閉所有內部計算。當您僅需讀取或匯出資料且不涉及排程變更時，可使用此模式。

#### 步驟 1：建立新的 Project 實例

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### 步驟 2：新增一個任務

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### 步驟 3：驗證任務屬性（不會自動產生 ID）

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## 常見問題與解決方案

| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| 連結任務後日期未更新 | 專案處於 **Manual** 或 **None** 模式 | 將 `project.CalculationMode = CalculationMode.Automatic`，或手動呼叫 `project.Calculate()` |
| 任務 ID 保持為 0 | 使用 **None** 模式會阻止 ID 產生 | 切換至 **Automatic** 或 **Manual** 模式，然後重新計算 |
| 連結失敗，拋出 `ArgumentException` | 在使用 **Manual** 模式且未重新計算時，前置任務的開始日期晚於後置任務 | 確保開始日期正確，或在加入連結後重新計算 |

## 常見問與答

**Q1: 我可以在執行期間動態變更計算模式嗎？**  
A1: 可以，您可以在程式碼的任何位置修改 `CalculationMode` 屬性，若需要即時更新，則呼叫 `project.Calculate()`。

**Q2: Aspose.Tasks 是否支援除 Microsoft Project 之外的其他專案管理檔案格式？**  
A2: Aspose.Tasks 主要針對 Microsoft Project 格式，但亦支援 Primavera P6 XML、Primavera DB 與 Asta Powerproject XML。

**Q3: Aspose.Tasks 是否適用於小型與企業級專案？**  
A3: 當然。此 API 可從簡單的任務清單擴展至複雜的多階段企業排程。

**Q4: 我可以將 Aspose.Tasks 與其他 .NET 函式庫或框架整合嗎？**  
A4: 可以，您可將 Aspose.Tasks 與 ASP.NET、WPF、Xamarin 或任何其他 .NET 技術結合，打造功能豐富的專案管理解決方案。

**Q5: 是否有 Aspose.Tasks 使用者的社群論壇或支援管道？**  
A5: 有，您可前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 取得社群支援與討論。

---

**最後更新：** 2026-03-24  
**測試環境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}