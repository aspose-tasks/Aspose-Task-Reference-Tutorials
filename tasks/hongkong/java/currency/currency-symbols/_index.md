---
date: 2026-09-20
description: 了解如何使用 Aspose.Tasks for Java 提取 mpp 貨幣符號並更新專案屬性。只需幾行程式碼即可變更與取得該符號。
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: 使用 Aspose.Tasks for Java 提取 mpp 貨幣符號
og_description: 了解如何使用 Aspose.Tasks for Java 提取 mpp 貨幣符號並更新專案屬性。快速、可靠，已備妥投入生產環境。
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: 如何使用 Aspose.Tasks for Java 提取 mpp 貨幣符號
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: 如何使用 Aspose.Tasks for Java 提取 mpp 貨幣符號
url: /zh-hant/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 從 MPP 提取貨幣符號

## 介紹
在本教學中，您將學習如何使用 **java project properties**——具體而言，如何 **extract currency symbol mpp** 從 Microsoft Project (MPP) 檔案，以及如何使用 Aspose.Tasks 函式庫 **change currency symbol java** 或 **retrieve currency symbol java**。無論您是構建財務報告工具、將 Project 資料整合至 ERP 系統，或僅需在 UI 中顯示正確的貨幣符號，掌握這項小而重要的任務都能讓您的 Java 應用程式更健全且使用者友好。

## 快速解答
- **什麼是「extract currency symbol mpp」？** 這表示讀取儲存在 MPP（Microsoft Project）檔案中的貨幣符號。  
- **哪個函式庫負責此操作？** Aspose.Tasks for Java 提供簡易的 API 來完成此工作。  
- **我需要授權嗎？** 免費試用可用於開發；正式上線需購買商業授權。  
- **需要多長時間？** 使用以下程式碼即可在一分鐘內取得符號。  
- **我也可以變更符號嗎？** 可以——使用相同的 `Prj.CURRENCY_SYMBOL` 屬性即可設定新值。

## 什麼是「extract currency symbol mpp」？
從 MPP 檔案中提取貨幣符號是指讀取 Microsoft Project 在檔案標頭中儲存的單一字元字串，用以表示專案的貨幣單位。此操作讓您在自己的應用程式中顯示正確的符號（例如 $, €, £），而不必硬編碼值。

## 為何在 Java 專案屬性中更新貨幣符號？
更新貨幣符號可讓您即時在報告、發票和儀表板上進行在地化。跨多個區域執行專案的企業可以一次切換符號，免除必須複製整個專案檔的需求。Aspose.Tasks 能在記憶體中修改此屬性並重新儲存檔案，支援包含多達 2,000 個工作項的專案，且不會產生明顯的效能影響。

## 前置條件
在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 版本 8 或以上。  
2. **Aspose.Tasks for Java** – 從 [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/) 下載最新的 JAR。  
3. 一個有效的 **project.mpp** 檔案，放置於您程式碼可參考的資料夾中。

## 匯入套件
首先，匯入我們處理 Project 檔案所需的類別。

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 步驟 1：定義資料目錄
告訴應用程式您的 *.mpp* 檔案所在的位置。

```java
String dataDir = "Your Data Directory";
```

> **專業提示:** 使用 `System.getProperty("user.dir")` 來建立在任何機器上皆可使用的絕對路徑。

## 步驟 2：載入 MS Project 檔案
`Project` 是 Aspose.Tasks 的頂層物件，代表記憶體中的單一 Microsoft Project 檔案。建立此物件會載入檔案結構，且不需要安裝 Microsoft Project。

```java
Project project = new Project(dataDir + "project.mpp");
```

## 步驟 3：取得（並可選擇變更）貨幣符號
`Prj.CURRENCY_SYMBOL` 是儲存貨幣符號的屬性鍵。讀取它會返回目前的符號；指派新字串則會更新專案的貨幣定義。

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

`System.out.println` 呼叫會將符號（例如 `$`）印到主控台，以確認提取成功。

## 常見問題與解決方法
| 症狀 | 可能原因 | 解決方案 |
|---------|--------------|----------|
| `project.get(...)` 上的 `NullPointerException` | 檔案路徑錯誤或找不到檔案 | 驗證 `dataDir` 與檔名；使用 `new File(dataDir).exists()` 進行除錯 |
| 出現非預期的符號（例如 `?`） | 專案使用非標準語系建立 | 確保來源 MPP 檔案實際定義了貨幣符號；您可以如上所示以程式方式設定 |
| 授權錯誤 | 使用試用版但未提供有效的授權檔案 | 在建立 `Project` 物件前，使用 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` 載入授權 |

## 常見問答

**Q: 我可以使用 Aspose.Tasks 操作除貨幣符號之外的其他專案屬性嗎？**  
**A:** 可以，Aspose.Tasks 讓您編輯工作項、資源、指派、行事曆以及更多專案屬性。

**Q: Aspose.Tasks 是否相容於不同版本的 MS Project 檔案？**  
**A:** 完全相容。它支援從 Project 98 到最新版本的 MPP、MPT 與 XML 格式。

**Q: Aspose.Tasks 是否提供開發者文件與支援？**  
**A:** 完整的 API 文件、程式碼範例以及專屬支援論壇皆可在 Aspose.Tasks 官方網站取得。

**Q: 我可以在購買前試用 Aspose.Tasks 嗎？**  
**A:** 可以——可從 [Aspose website](https://purchase.aspose.com/buy) 下載功能完整的免費試用版。

**Q: 我要如何取得 Aspose.Tasks 的臨時授權？**  
**A:** 臨時授權可於 [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) 取得，用於評估目的。

**最後更新：** 2026-09-20  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose

## 相關教學

- [Java 專案屬性 – 使用 Aspose.Tasks 讀取中繼資料](/tasks/java/project-properties/)
- [如何使用 Aspose.Tasks 從 MS Project 取得貨幣](/tasks/java/currency/currency-codes/)
- [使用 Aspose.Tasks for Java 設定 MS Project 的專案開始日期](/tasks/java/project-properties/write-project-info/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}