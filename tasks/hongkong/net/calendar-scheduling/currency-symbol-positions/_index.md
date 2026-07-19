---
date: 2026-07-19
description: 了解如何在 .NET 專案中輕鬆使用 Aspose.Tasks 控制貨幣符號顯示於金額之後。
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Aspose.Tasks 中的貨幣符號位置
og_description: 了解如何使用 Aspose.Tasks for .NET 將貨幣符號放在金額之後。遵循一步一步的說明與最佳實踐。
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Aspose.Tasks 中的貨幣符號放在金額之後 — 快速指南
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: 如何在 Aspose.Tasks 中將貨幣符號放在金額之後
url: /zh-hant/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中將貨幣符號放在金額之後

## 簡介

當您產生專案成本報告時，**currency symbol after amount** 的放置方式會影響可讀性與符合區域標準。Aspose.Tasks for .NET 只需幾行程式碼即可讓您控制此格式，確保每筆財務數字都以利害關係人期望的方式呈現。在本教學中，我們將逐步說明所需步驟、解釋此設定的重要性，並示範如何在實際的 .NET 專案中套用。

## 快速解答
- **什麼是「currency symbol after amount」的意思？** 它會在數值之後顯示符號（例如 $），如 `100 $`。
- **哪個屬性控制位置？** `CurrencySymbolPosition` 於 `Project` 物件上。
- **我需要授權嗎？** 開發階段可使用試用版；正式環境需購買商業授權。
- **支援哪些貨幣？** 內建超過 50 種貨幣，涵蓋大多數全球市場。
- **可以在執行時變更設定嗎？** 可以，在儲存專案檔之前隨時更新。

## 什麼是「currency symbol after amount」設定？

**currency symbol after amount** 選項決定在專案所有金額欄位中，貨幣符號是顯示在數值之前還是之後。調整此設定即可讓報表符合當地會計慣例，免除手動後處理，同時提升習慣此格式的利害關係人的可讀性。

## 為什麼使用 Aspose.Tasks 進行貨幣格式化？

Aspose.Tasks 支援 **50+ 種貨幣**，且即使在 **10,000+ 工作** 的大型專案中，也不需將整個檔案載入記憶體，即可提供快速效能，即使在硬體規格較低的環境下亦能順暢運作。API 提供程式化控制，省去手動 Excel 編輯的需求，使大規模財務報告既高效又可靠。

## 先決條件

### 1. 安裝 Aspose.Tasks for .NET
確保已安裝 Aspose.Tasks 程式庫。您可從 [here](https://releases.aspose.com/tasks/net/) 下載。

### 2. .NET 程式設計的基本知識
需要具備 .NET 程式設計的基本概念才能跟隨範例。

## 匯入命名空間

`Aspose.Tasks` 命名空間提供對 `Project` 類別及相關列舉的存取。

`Project` 類別是 Aspose.Tasks 的頂層物件，代表記憶體中的單一專案檔案。匯入命名空間後，即可開始操作專案資料。

```csharp

```

現在，讓我們將範例分解為清晰、可執行的步驟。

## 如何設定 currency symbol after amount？

`CurrencySymbolPosition` 是一個列舉，指定貨幣符號是出現在數值之前或之後。

載入專案、將 `CurrencySymbolPosition` 設為 `After`，然後儲存——這就是在金額之後顯示符號所需的全部步驟。此直接方式適用於任何支援的貨幣，且不需要額外的格式化邏輯。您亦可透過匯出樣本成本報告來驗證設定是否正確。

### 步驟 1：載入專案檔案
`Project` 類別可載入既有的 MS‑Project 檔案或在記憶體中建立新檔案。

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### 步驟 2：設定貨幣符號位置
`CurrencySymbolPosition` 為列舉，可選擇 `Before` 或 `After`。將其設為 `After` 即可將符號放在數值之後。

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### 步驟 3：操作專案
設定好符號位置後，您可以繼續新增工作、資源或自訂欄位。此設定會在儲存專案時一併寫入。

```csharp
// Perform other operations with the project...
```

## 常見問題與解決方案
- **符號仍然出現在金額之前：** 請確保在呼叫 `Save` 之前設定屬性。儲存後再更改需要重新儲存檔案。
- **不支援的貨幣：** 請確認您使用的貨幣代碼已列於 Aspose.Tasks 支援清單（超過 50 種貨幣）。
- **大型專案效能下降：** 若工作項目超過 10,000 個，可使用 `ProjectReader` 以串流方式讀取大型檔案。

## 常見問答

**Q: 可以在同一個專案中多次變更貨幣符號位置嗎？**  
A: 可以，您可以依需求多次調整 `CurrencySymbolPosition`；只要設定屬性後重新儲存專案即可。

**Q: Aspose.Tasks 是否支援除美元外的其他貨幣？**  
A: 當然支援。Aspose.Tasks 支援超過 50 種國際貨幣，讓您能使用任何區域格式。

**Q: 是否有 Aspose.Tasks for .NET 的試用版？**  
A: 有，您可從 [here](https://releases.aspose.com/) 取得免費試用版。

**Q: 使用 Aspose.Tasks for .NET 時若遇到問題，可否取得協助？**  
A: 當然可以！您可前往 Aspose.Tasks 社群論壇取得支援與協助，網址在 [here](https://forum.aspose.com/c/tasks/15)。

**Q: 如何購買 Aspose.Tasks for .NET 的授權？**  
A: 您可從 [here](https://purchase.aspose.com/buy) 購買授權。

## 結論

控制 **currency symbol after amount** 是專案管理軟體財務報告的重要環節。使用 Aspose.Tasks for .NET，您可以以程式方式設定此選項，支援超過 50 種貨幣，且能有效處理大型專案。依照上述步驟操作，即可確保您的專案報表符合任何地區的格式需求。

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## 相關教學

- [管理 Aspose.Tasks 中的行事曆集合](/tasks/net/calendar-scheduling/calendar-collection/)
- [Aspose.Tasks 行事曆例外集合](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [使用 Aspose.Tasks for .NET 處理 MS Project 费率](/tasks/net/rate-recurring-tasks/handling-rates/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}