---
title: Aspose.Tasks 中任務基線的集合
linktitle: Aspose.Tasks 中任務基線的集合
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 輕鬆探索任務基線。高效率的專案管理變得簡單。現在下載！ #Aspose.Tasks #MS 項目
weight: 17
url: /zh-hant/net/task-table-management/task-baseline-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中任務基線的集合

## 介紹
歡迎來到 Aspose.Tasks for .NET 的世界，這是一個功能強大的程式庫，可促進專案任務的無縫操作和管理。在本教程中，我們將深入研究任務基線的迷人領域——專案規劃和追蹤的一個重要方面。在本指南結束時，您將掌握使用任務基線集合的藝術，從而增強您的專案管理能力。
## 先決條件
在我們開始這趟旅程之前，請確保您具備以下先決條件：
-  Aspose.Tasks for .NET Library：從以下位置下載並安裝該程式庫：[發布頁面](https://releases.aspose.com/tasks/net/).
- 開發環境：設定您首選的 .NET 開發環境。
- 對 C# 的基本了解：熟悉 C# 程式語言是有益的。
現在我們已經準備就緒，讓我們進入 Aspose.Tasks for .NET 的激動人心的世界。
## 導入命名空間
在您的 C# 專案中，首先匯入必要的命名空間：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. 設定項目和任務
首先建立一個新專案並在其中新增一個任務：
```csharp
var project = new Project();
var task = project.RootTask.Children.Add("Task");
```
## 2. 建立專案基線
現在，讓我們為該任務建立專案基線：
```csharp
project.SetBaseline(BaselineType.Baseline);
```
## 3. 列印任務基線
列印有關任務基線的資訊：
```csharp
Console.WriteLine("Count of task baselines: " + task.Baselines.Count);
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration: {0}", baseline.Duration);
    Console.WriteLine("Baseline start: {0}", baseline.Start);
    Console.WriteLine("Baseline finish: {0}", baseline.Finish);
}
```
## 4. 清除所有基線
如果需要，您可以清除與任務關聯的所有基準：
```csharp
List<TaskBaseline> baselines = task.Baselines.ToList();
for (var i = 0; i < baselines.Count; i++)
{
    task.Baselines.Remove(baselines[i]);
}
```
恭喜！您已成功完成使用 Aspose.Tasks for .NET 處理任務基準的程序。
## 結論
總之，使用 Aspose.Tasks for .NET 掌握任務基準為高效專案管理開啟了多種可能性。本指南為您提供了有效利用此功能的知識和技能。
## 經常問的問題
### Q：我可以為單一任務建立多個基線嗎？
答：是的，Aspose.Tasks for .NET 可讓您設定和管理任務的多個基準。
### Q：在使用任務基線時如何處理異常？
答：您可以使用try-catch區塊來優雅地處理異常並確保程式碼順利執行。
### Q：專案中可以包含的任務數量是否有限制？
答：Aspose.Tasks for .NET 對任務數量沒有嚴格限制，為不同的專案規模提供了彈性。
### Q：我可以自訂列印基線資訊的格式嗎？
答：當然！列印基線詳細資訊時，您可以完全控制格式，從而可以根據您的特定要求進行自訂。
### Q：如果我遇到問題或有其他疑問，可以在哪裡尋求協助？
答：訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以獲得專門的支持和社區援助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
