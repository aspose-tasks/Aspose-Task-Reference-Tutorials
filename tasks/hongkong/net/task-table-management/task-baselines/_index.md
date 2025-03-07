---
title: 掌握 Aspose.Tasks for .NET 中的任務基線
linktitle: 在 Aspose.Tasks 中處理任務基線
second_title: Aspose.Tasks .NET API
description: 透過這個綜合教程，了解如何在 Aspose.Tasks for .NET 中處理任務基準。立即增強您的專案管理技能！
weight: 16
url: /zh-hant/net/task-table-management/task-baselines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 掌握 Aspose.Tasks for .NET 中的任務基線

## 介紹
在動態的專案管理世界中，保持組織性和資訊靈通至關重要。 Aspose.Tasks for .NET 提供了處理任務基準的強大解決方案，讓您能夠有效地存取有價值的基準資訊。本逐步指南將引導您完成整個過程，確保您清晰地掌握每個概念。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- 環境設定：確保您的開發環境中安裝了 Aspose.Tasks for .NET。如果沒有，您可以從以下位置下載[Aspose.Tasks 文檔](https://reference.aspose.com/tasks/net/).
- C# 基礎知識：熟悉 C# 程式語言基礎知識，因為本教學假設您有基本的了解。
- 整合開發環境 (IDE)：使用首選 IDE（例如 Visual Studio）來無縫地進行操作。
## 導入命名空間
首先，將必要的命名空間匯入到您的專案中。這可確保您可以存取 Aspose.Tasks 功能：
```csharp
    using Aspose.Tasks;
    using System;
```
現在，讓我們將提供的範例分解為多個步驟，以指導您在 Aspose.Tasks 中處理任務基準。
## 第 1 步：建立項目
```csharp
var project = new Project();
```
首先使用以下命令初始化一個新項目`Project`班級。
## 第 2 步：建立任務並設定基線
```csharp
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
```
將任務新增至專案並使用以下命令設定其基線`SetBaseline`方法。
## 步驟 3：顯示任務基線訊息
```csharp
var baseline = task.Baselines.ToList()[0];
Console.WriteLine("Baseline Start: {0}", baseline.Start);
Console.WriteLine("Baseline duration: {0}", baseline.Duration);
Console.WriteLine("Baseline duration format: {0}", baseline.Duration.TimeUnit);
Console.WriteLine("Is it estimated duration?: {0}", baseline.EstimatedDuration);
Console.WriteLine("Baseline Finish: {0}", baseline.Finish);
```
檢索並顯示有關任務基線的關鍵信息，例如開始時間、持續時間和完成時間。
## 第 4 步：其他基線詳細信息
```csharp
Console.WriteLine("Interim: {0}", baseline.Interim);
Console.WriteLine("Fixed Cost: {0}", baseline.FixedCost);
```
探索其他詳細信息，包括基線是否為臨時基線以及與其相關的固定成本。
## 第 5 步：列印時間分段數據
```csharp
Console.WriteLine("Number of timephased items: " + baseline.TimephasedData.Count);
foreach (var data in baseline.TimephasedData)
{
    Console.WriteLine(" Uid: " + data.Uid);
    Console.WriteLine(" Start: " + data.Start);
    Console.WriteLine(" Finish: " + data.Finish);
}
```
了解與任務基線相關的時間分段數據，提供各種專案時間表的見解。
## 結論
恭喜！您已經成功學習如何在 Aspose.Tasks for .NET 中處理任務基準。這些知識將增強您的專案管理能力，確保準確的追蹤和規劃。
## 經常問的問題
### Q：我可以將 Aspose.Tasks 與其他 .NET 框架一起使用嗎？
答：Aspose.Tasks 與多個.NET 框架相容，為您的開發環境提供靈活性。
### Q：是否有 Aspose.Tasks 支援的社群論壇？
答：是的，您可以在以下位置找到支持並與社區互動：[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).
### Q：如何取得 Aspose.Tasks 的臨時許可證？
答：訪問[這裡](https://purchase.aspose.com/temporary-license/)取得 Aspose.Tasks 的臨時許可證。
### Q：是否有任何超出任務基線的教學可用？
答：探索[文件](https://reference.aspose.com/tasks/net/)有關 Aspose.Tasks 功能的各種教學。
### Q：哪裡可以購買 Aspose.Tasks for .NET？
 A：您可以輕鬆購買Aspose.Tasks[這裡](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
