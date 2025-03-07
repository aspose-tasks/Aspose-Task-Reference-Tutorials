---
title: Aspose.Tasks 中風險項的統計
linktitle: Aspose.Tasks 中風險項的統計
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 釋放 MS Project 檔案中風險分析的強大功能。輕鬆獲得洞察、減少不確定性並推動專案成功。
weight: 21
url: /zh-hant/net/resource-risk-analysis/risk-item-statistics/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中風險項的統計

## 介紹
您是否希望使用 Aspose.Tasks for .NET 來增強您的專案管理能力？透過我們有關獲取 MS Project 檔案中風險項目統計資訊的逐步教程，深入了解風險分析領域。透過利用 Aspose.Tasks 的強大功能，您可以獲得對專案不確定性的寶貴見解，並做出明智的決策以有效降低風險。
## 先決條件
在我們開始這趟旅程之前，請確保您具備以下先決條件：
1.  Aspose.Tasks for .NET Library：從以下位置下載並安裝該程式庫：[.NET 文件的 Aspose.Tasks](https://reference.aspose.com/tasks/net/)。該庫為您提供了強大的工具，用於以程式設計方式操作 MS Project 檔案。
2. .NET 開發環境：設定您的 .NET 開發環境，包括 Visual Studio 或您選擇的任何其他 IDE，以促進 Aspose.Tasks 無縫整合到您的專案中。

## 導入命名空間
將必要的命名空間合併到您的專案中以利用 Aspose.Tasks 的功能：
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## 第 1 步：定義資料目錄
```csharp
String DataDir = "Your Document Directory";
```
確保更換`"Your Document Directory"`以及 MS Project 檔案所在的文檔目錄的路徑。
## 步驟 2：配置風險分析設置
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
調整`IterationsCount`根據您的專案需求參數來控制風險分析的精確度。
## 第 3 步：載入 MS 專案文件
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
將所需的 MS Project 檔案載入到`project`為進一步分析的對象。
## 第 4 步：定義任務並初始化風險模式
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
指定風險分析任務，並使用適當的參數（例如分佈類型、樂觀和悲觀持續時間以及置信水準）來配置風險模式。
## 第五步：分析專案風險
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
使用定義的設定和專案資料啟動風險分析流程。
## 第 6 步：檢索並顯示統計數據
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
檢索並顯示與 MS Project 文件中的風險項目相關的各種統計指標，包括預期值、標準差、百分位數、最小值和最大值。

## 結論
總之，使用 Aspose.Tasks for .NET 掌握 MS Project 檔案中的風險分析為專案經理和利害關係人開啟了新的可能性領域。透過遵循我們的綜合教程，您可以自信地應對不確定性，確保專案成功。
## 常見問題解答
### 我可以將 Aspose.Tasks 與其他 .NET 程式庫整合以實現擴充功能嗎？
絕對地！ Aspose.Tasks 與各種 .NET 函式庫無縫集成，讓您可以根據專案需求擴充其功能。
### Aspose.Tasks for .NET 有沒有試用版？
是的，您可以透過造訪來探索 Aspose.Tasks 的功能[免費試用](https://releases.aspose.com/)可在我們的網站上找到。
### Aspose.Tasks 的更新和增強功能多久會發布一次？
我們努力透過定期發布更新和增強功能來不斷改進 Aspose.Tasks，確保您始終能夠存取最新的功能和最佳化。
### 我可以獲得 Aspose.Tasks 的技術支援嗎？
當然！我們的專業支援團隊隨時可以在[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)協助您解決在實施過程中可能遇到的任何疑問或挑戰。
### 你們為短期專案提供臨時許可證嗎？
是的，如果您需要 Aspose.Tasks 進行短期項目，您可以利用我們的便利[臨時執照](https://purchase.aspose.com/temporary-license/)無需任何長期承諾即可滿足您的授權需求的選項。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
