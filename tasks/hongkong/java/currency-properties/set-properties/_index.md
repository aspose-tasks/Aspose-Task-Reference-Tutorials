---
date: 2026-09-09
description: 了解如何在 Aspose.Tasks Java 專案中變更貨幣符號、設定貨幣代碼、調整符號，並為 Microsoft Project 檔案套用自訂格式。
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: 設定 Aspose.Tasks 專案的貨幣屬性
og_description: 如何使用 Java 在 Aspose.Tasks 中變更貨幣符號。探索一步一步的說明、先決條件，以及自訂專案成本格式的技巧。
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: 如何在 Aspose.Tasks 中變更貨幣符號 – Java 指南
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: 如何在 Aspose.Tasks 專案中變更貨幣符號 – Java 指南
url: /zh-hant/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks – Java 指南中更改貨幣符號

## 介紹
在本教學中，您將學習 **如何更改 Microsoft Project 檔案的貨幣符號**，使用 Aspose.Tasks Java API。無論是為海外客戶準備報告、整合多區域的預算，或只是需要符合公司會計標準，調整貨幣符號都能確保每個與成本相關的欄位顯示正確的貨幣符號。本文將逐步說明從設定開發環境到在新檔案或既有檔案中持久化變更的全部步驟。

## 快速回答
- **需要哪個程式庫？** Aspose.Tasks for Java。  
- **我可以更改貨幣符號嗎？** 可以 – 設定 `Prj.CURRENCY_SYMBOL` 並選擇 `CurrencySymbolPositionType`。  
- **支援哪些檔案格式？** XML、MPP，以及透過 `SaveFileFormat` 支援的其他多種格式。  
- **開發時需要授權嗎？** 免費試用可用於測試；正式上線需購買授權。  
- **實作大約需要多久？** 基本設定約 5‑10 分鐘即可完成。

## 如何使用 Java 在 Aspose.Tasks 中更改貨幣符號？
載入目標專案（或建立新專案），設定所需的貨幣屬性，然後儲存檔案。整個操作只需三個 API 呼叫：建立或載入 `Project` 物件、指派貨幣代碼、符號與位置，最後呼叫 `project.save`。此方式適用於全新專案與既有檔案，且不需要安裝 Microsoft Project。

## 為什麼使用 Aspose.Tasks 來更改貨幣？
Aspose.Tasks 提供 **30 多項與貨幣相關的屬性完整 API 支援**，讓您在同一處定義代碼、符號、小數位數與位置。該程式庫在一般伺服器硬體上能在一秒內處理數百頁的 Project 檔案，且可在 Windows、Linux、macOS 上執行，無需額外相依性。

## 前置條件
在開始之前，請確保您已具備：

1. **Java Development Kit (JDK) 8 或以上** – API 至少需要 JDK 8。  
2. **Aspose.Tasks for Java** – 從 [Aspose.Tasks 下載頁面](https://releases.aspose.com/tasks/java/) 取得最新 JAR。  
3. **開發環境 (IDE)** – Eclipse、IntelliJ IDEA，或任何支援 Java 的編輯器。  
4. **可寫入的資料夾** – 用於儲存產生的專案檔案。

## 匯入套件
以下類別讓您可以存取專案屬性、檔案處理與貨幣設定。

`Project` – 代表記憶體中的 Microsoft Project 檔案。  
`Prj` – 包含所有專案層級屬性的常數，包含貨幣相關欄位。  
`CurrencySymbolPositionType` – 列舉貨幣符號可能的放置位置（前置或後置）。

在撰寫任何操作專案的程式碼之前，必須先匯入這些類別。

## 步驟說明

### 步驟 1：定義資料目錄
選擇一個資料夾來存放來源檔案與輸出結果。請確保該目錄已存在且 Java 程序具有寫入權限。

### 步驟 2：建立新專案實例
`Project` 類別是 Aspose.Tasks 的最高層物件，代表記憶體中的單一 Project 檔案。建立它會產生一個空白專案，供後續設定使用。

### 步驟 3：設定貨幣屬性
在此步驟中您會設定貨幣代碼、小數位數、符號本身以及符號的位置。

- **貨幣代碼** – ISO 4217 三字母代碼，例如 `AUD` 或 `USD`。  
- **小數位數** – 大多數貨幣通常為 2 位。  
- **貨幣符號** – 與金額一起顯示的字元或字串，例如 `$` 或 `€`。  
- **符號位置** – `CurrencySymbolPositionType.Before` 會將符號放在數字前；`After` 則放在數字後。

這些設定會影響專案中所有與成本相關的欄位（資源費率、工作項目預算等）。

> **小技巧：** 若要更改既有檔案的貨幣，請先以 `new Project("file.mpp")` 載入檔案，再套用上述設定。

### 步驟 4：儲存更新後的專案
使用所需的格式將專案寫回磁碟。XML 格式易於閱讀，而 `SaveFileFormat.MPP` 則保留與 Microsoft Project 完全相容的結構。

### 步驟 5：確認成功
印出簡短訊息或寫入日誌，以確保操作已順利完成。此步驟在自動化流程中特別有用。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **`NullPointerException` 發生於 `project.save`** | `dataDir` 路徑無效或缺乏寫入權限。 | 確認目錄存在且 Java 程序具有寫入權限。 |
| **貨幣符號未顯示** | 符號位置設定與本地語系不符。 | 若符號應置於金額前，使用 `CurrencySymbolPositionType.Before`。 |
| **專案檔案無法在 MS Project 開啟** | 以不相容的舊版格式儲存。 | 使用 `SaveFileFormat.MPP` 以確保與最新 MS Project 版本相容。 |

## 常見問答

**Q: 可以在同一個專案中設定多種貨幣嗎？**  
A: 可以，您可以在定義專案層級貨幣後，針對個別資源或工作項目修改其成本欄位，以使用不同的貨幣設定。

**Q: Aspose.Tasks 是否相容不同版本的 Microsoft Project 檔案？**  
A: 完全相容。程式庫支援從 Project 2000 到最新版本的 MPP 檔案，亦支援 XML 與其他交換格式。

**Q: 是否支援自訂貨幣格式？**  
A: 支援，您可以自訂符號、 小數位數與位置，以符合任何區域需求，且這些設定會寫入儲存的檔案中。

**Q: 可以將 Aspose.Tasks 與其他 Java 框架整合嗎？**  
A: 當然可以。API 為純 Java，能無縫結合 Spring、Hibernate、Maven、Gradle 等生態系統。

**Q: 哪裡可以取得更多範例或協助？**  
A: 前往 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 取得社群協助，或參考官方文件取得完整 API 參考。

## 結論
現在您已掌握 **如何在 Aspose.Tasks 專案中使用 Java 更改貨幣符號**，包括設定貨幣代碼、調整小數位數以及套用自訂符號。這些功能讓您能產生符合在地化的成本報表，將專案預算與區域會計標準對齊，並確保 Microsoft Project 檔案在全球團隊間保持一致。

---

**最後更新：** 2026-09-09  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## 相關教學

- [java project properties – 使用 Aspose.Tasks for Java 從 MPP 取出貨幣符號](/tasks/java/currency/currency-symbols/)
- [Read Currency Properties Java with Aspose.Tasks Projects](/tasks/java/currency-properties/read-properties/)
- [Manage Currency Codes Java with Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}