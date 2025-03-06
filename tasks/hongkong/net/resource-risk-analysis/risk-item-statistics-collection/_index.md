---
title: 在 Aspose.Tasks 中收集 MS 專案風險項統計資訊
linktitle: Aspose.Tasks中風險項目統計資料的收集
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 從 MS Project 檔案收集風險項目統計資料。增強您的專案管理能力。
weight: 22
url: /zh-hant/net/resource-risk-analysis/risk-item-statistics-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中收集 MS 專案風險項統計資訊

## 介紹
在本教學中，我們將探討如何使用 Aspose.Tasks for .NET 從 MS Project 檔案收集風險項目統計資料。該庫提供了強大的功能來分析專案數據，包括風險評估和統計分析。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. Aspose.Tasks for .NET：下載並安裝 Aspose.Tasks 函式庫。您可以從[下載頁面](https://releases.aspose.com/tasks/net/).
2. 開發環境：為.NET 程式設計設定開發環境。

## 導入命名空間
在開始編碼之前，請確保在專案中匯入必要的命名空間：
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## 第 1 步：載入專案文件
首先，您需要將 MS Project 檔案載入到您的應用程式中。以下是實現這一目標的方法：
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## 第 2 步：定義風險分析設置
初始化風險分析設置，包括迭代次數，如下圖：
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## 第 3 步：初始化風險模式
設定分析的風險模式，指定分佈類型、樂觀和悲觀百分比以及置信水準：
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## 第 4 步：進行風險分析
實例化`RiskAnalyzer`對項目進行分類和分析：
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## 第 5 步：檢索統計數據
從分析結果中檢索風險項統計信息，例如提前完成：
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## 第 6 步：列印統計數據
迭代統計資訊並列印詳細資訊：
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //列印其他相關統計資料...
}
```

## 結論
在本教程中，我們學習如何利用 Aspose.Tasks for .NET 從 MS Project 檔案收集風險項目統計資料。透過執行這些步驟，您可以有效地分析專案數據並評估潛在風險，有助於更好的決策和專案管理。

## 常見問題解答
### Q：Aspose.Tasks 可以處理大型 MS Project 檔案嗎？
答：是的，Aspose.Tasks 能夠有效處理大型 MS Project 文件，提供可靠的效能和可擴充性。
### Q：Aspose.Tasks 是否支援 .mpp 以外的其他專案檔案格式？
答：是的，Aspose.Tasks 支援各種專案檔案格式，包括 XML 和 MPT。
### Q：Aspose.Tasks 適合企業級專案管理應用嗎？
答：當然，Aspose.Tasks 旨在滿足企業級專案管理應用程式的需求，提供強大的功能和豐富的文件。
### Q：我可以在 Aspose.Tasks 中自訂風險分析設定嗎？
答：是的，Aspose.Tasks 可以靈活地配置風險分析設置，以滿足您的特定專案要求和情境。
### Q：Aspose.Tasks 用戶可以獲得技術支援嗎？
答：是的，Aspose.Tasks 用戶可以透過 Aspose 獲得技術支持[論壇](https://forum.aspose.com/c/tasks/15)，他們可以提出問題、報告問題並與社區互動。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
