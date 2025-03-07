---
title: 在 Aspose.Tasks 中使用基線集合
linktitle: 在 Aspose.Tasks 中使用基線集合
second_title: Aspose.Tasks .NET API
description: 了解如何有效管理 Aspose.Tasks for .NET 中的基準。請按照我們的綜合教程獲取逐步指導。
weight: 20
url: /zh-hant/net/advanced-features/working-with-baseline-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中使用基線集合

## 介紹

Aspose.Tasks for .NET 是一個功能強大的程式庫，可讓開發人員在其 .NET 應用程式中無縫地使用 Microsoft Project 檔案。在其眾多功能中，它為管理專案內的基準提供了強大的支援。基準對於專案管理至關重要，因為它們允許您將原始專案計劃與當前狀態進行比較，從而更好地追蹤和分析專案進度。

## 先決條件

在我們深入研究 Aspose.Tasks 中的基準集合之前，請確保您具備以下先決條件：

1. Visual Studio：在您的系統上安裝 Visual Studio IDE。
2.  Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫：[下載連結](https://releases.aspose.com/tasks/net/).
3. 對 C# 的基本了解：熟悉 C# 程式語言。
4. Microsoft Project 檔案：準備好 Microsoft Project 檔案 (.mpp) 以用於測試目的。

## 導入命名空間

要開始在 Aspose.Tasks 中使用基線集合，您需要匯入以下命名空間：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

現在，讓我們將每個範例分解為多個步驟：

## 第 1 步：載入專案文件

首先，使用 Aspose.Tasks 載入 Microsoft Project 檔案：

```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## 第 2 步：獲取資源

接下來，從專案中檢索所需的資源：

```csharp
var resource = project.Resources.GetByUid(1);
```

## 步驟 3：顯示基線訊息

現在，顯示有關與資源關聯的基線的資訊：

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## 第 4 步：迭代基線

迭代與資源關聯的每個基線並列印相關資訊：

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## 第 5 步：刪除基線

刪除與資源關聯的所有基線：

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## 結論

在本教程中，我們探討如何在 Aspose.Tasks for .NET 中使用基線集合。透過遵循逐步指南，您可以輕鬆管理 .NET 應用程式中的基線，從而實現有效的專案追蹤和分析。

## 常見問題解答

### Q1：Aspose.Tasks 可以處理大型專案檔案嗎？

A1：是的，Aspose.Tasks 經過最佳化，可有效處理大型專案文件，確保流暢的效能。

### Q2：Aspose.Tasks 是否與所有版本的 Microsoft Project 相容？

A2：Aspose.Tasks支援Microsoft Project的各個版本，確保不同環境下的相容性。

### Q3：我可以在 Aspose.Tasks 中自訂基線嗎？

A3：是的，您可以根據您的專案要求使用 Aspose.Tasks for .NET 自訂基線。

### Q4：Aspose.Tasks 是否提供對雲端平台的支援？

A4：是的，Aspose.Tasks 支援與流行的雲端平台集成，提供部署靈活性。

### Q5：Aspose.Tasks 使用者是否有社群論壇來尋求協助和分享知識？

 A5: 是的，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)與社區互動並獲得專家的協助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
