---
date: 2026-04-30
description: 學習如何使用 Aspose.Tasks for .NET 設定基準線並有效操作專案基準線。
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Aspose.Tasks 中的不同基準線類型
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中設定基準 – 不同的基準類型
url: /zh-hant/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的不同基準類型

## 介紹

在專案管理中，正確的 **設定基準線** 方式可能決定專案是保持在正軌上，還是失控。Aspose.Tasks for .NET 為您提供完整功能的 API，能建立、更新與比較基準線，讓您 **追蹤專案進度** 與原始計畫對照。在本教學中，您將學習如何設定基準線、使用多種基準類型，並利用資料分析專案的 **基準與實際排程**。

## 快速解答
- **什麼是基準線？** 在專案的特定時間點所拍攝的排程、成本與工作資料快照。  
- **Aspose.Tasks 能儲存多少個基準線？** 每個專案最多可有 11 個不同的基準線。  
- **為什麼要設定基準線？** 用於將實際表現與原始計畫比較，並找出差異。  
- **試用是否需要授權？** 提供免費試用；正式使用需購買授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## Aspose.Tasks 中的「如何設定基準線」是什麼？
設定基準線即是對 `Project` 物件呼叫 `SetBaseline` 方法。此 API 允許您從多個 `BaselineType` 值 (Baseline、Baseline1 … Baseline10) 中選擇，以便在專案演進過程中保留歷史快照。

## 為什麼要管理專案基準線？
- **衡量差異：** 快速查看工作是否提前或延遲。  
- **成本控制：** 比較基準成本與實際支出。  
- **利害關係人報告：** 將基準資料匯出為 PDF、XLSX 或其他格式，以便清晰溝通。  
- **情境規劃：** 儲存多個基準線以評估「假設」排程。

## 前置條件

### 1. 熟悉 C# 與 .NET Framework
需要具備 C# 類別、方法與物件導向概念的基本了解。

### 2. 安裝 Aspose.Tasks for .NET
確保已將此函式庫加入您的專案。您可以從 [Aspose.Tasks 官方網站](https://releases.aspose.com/tasks/net/) 下載，或透過 NuGet 安裝。

### 3. 整合開發環境 (IDE)
建議使用 Visual Studio（或其他相容的 IDE）來編寫、編譯與偵錯 C# 程式碼。

## 匯入命名空間

在我們的 C# 專案中開始使用 Aspose.Tasks 前，需要匯入必要的命名空間以存取所需的類別與方法。請依照以下步驟：

```csharp

```

現在我們已完成前置條件設定與必要命名空間的匯入，讓我們深入探討使用 Aspose.Tasks for .NET 設定不同類型的基準線。為了清晰易懂，我們會將每個範例拆解成多個步驟。

## 如何在 Aspose.Tasks 中設定基準線

### 步驟 1：載入專案檔案
首先，我們需要載入欲設定基準線的專案檔案。此步驟包括初始化 `Project` 物件並載入專案檔案。以下是實作方式：

```csharp
var project = new Project("Project2.mpp");
```

### 步驟 2：設定基準線
專案載入後，即可進行基準線設定。基準線提供專案初始排程的快照，作為專案進行過程中比較的參考點。使用 `SetBaseline` 方法來設定基準線。例如，若要為整個專案設定基準線，請使用 `BaselineType.Baseline` 列舉：

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### 步驟 3：使用專案基準線
設定基準線後，您可以使用各種專案基準欄位來精確分析與追蹤專案進度。此步驟涉及存取基準資料，如開始日期、結束日期、工期與成本。您可利用 Aspose.Tasks 提供的豐富功能，依需求操作基準資料。

## 常見問題與解決方案
- **基準線未套用：** 呼叫 `SetBaseline` 後請確保儲存專案檔案。若需保留變更，使用 `project.Save("output.mpp");`。  
- **多個基準線衝突：** 設定超過一個基準線時，請指定正確的 `BaselineType`（例如 `Baseline1`、`Baseline2`）。  
- **版本不匹配：** 確認 Aspose.Tasks DLL 版本與目標 .NET 執行環境相符。

## 常見問答

**Q: 我可以在單一專案中使用 Aspose.Tasks for .NET 設定多個基準線嗎？**  
A: 可以，Aspose.Tasks 允許為專案設定最多 11 個基準線，提供完整的追蹤功能。

**Q: Aspose.Tasks 是否相容於不同的專案檔案格式？**  
A: 當然！Aspose.Tasks 支援多種專案檔案格式，如 MPP、XML 與 MPX，確保在不同平台間的相容性。

**Q: 我該如何在專案中可視化基準資料？**  
A: 您可使用 Aspose.Tasks 將專案資料匯出為常見檔案格式，如 PDF 或 XLSX，方便視覺化與分享基準資訊。

**Q: Aspose.Tasks 是否提供與專案管理工具整合的支援？**  
A: Aspose.Tasks 提供豐富的文件與支援論壇，協助開發者將其功能無縫整合至流行的專案管理工具與平台。

**Q: 我可以在購買前先試用 Aspose.Tasks 嗎？**  
A: 可以，您可於官方網站取得免費試用，親自體驗其功能。

---

**Last Updated:** 2026-04-30  
**Tested With:** Aspose.Tasks for .NET (latest stable release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}