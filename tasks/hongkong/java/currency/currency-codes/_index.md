---
date: 2026-09-25
description: 了解如何使用 Aspose.Tasks for Java 從 MS Project 檔案中取得貨幣代碼——快速取得 Java 開發人員所需的貨幣代碼。
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: 在 Aspose.Tasks 中管理貨幣代碼
og_description: 使用 Aspose.Tasks 從 MS Project 檔案中取得 Java 貨幣代碼。本指南示範如何讀取專案、提取 ISO 貨幣識別碼，並在
  Java 應用程式中使用。
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: 從 MS Project 取得 Java 貨幣代碼
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: 使用 Aspose.Tasks 從 MS Project 取得 Java 貨幣代碼
url: /zh-hant/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 從 MS Project 取得貨幣代碼（Java）使用 Aspose.Tasks

## 介紹
在本教學中，您將學習 **如何使用 Aspose.Tasks Java API 從 MS Project 檔案取得貨幣代碼（Java）**。無論您需要產生多幣別財務報表、整合不同地區的專案，或僅僅在下游系統中顯示正確的貨幣符號，以下步驟將帶您從環境設定一路到返回 ISO 貨幣識別碼的單行呼叫。完成本指南後，您將能熟練載入任何支援的 Project 檔案格式，並提取如 `USD`、`EUR` 或 `GBP` 等三字母貨幣代碼。

## 快速解答
- **API 的功能是什麼？** 它會讀取 MS Project 檔案並公開諸如貨幣代碼等屬性。  
- **使用哪種語言？** Java，透過 Aspose.Tasks for Java 函式庫。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **可以用一行程式碼取得代碼嗎？** 可以——`prj.get(Prj.CURRENCY_CODE)` 會立即返回貨幣代碼字串。  
- **相容所有 Project 版本嗎？** Aspose.Tasks 支援超過 20 種輸入格式，包括舊版 MPP、XML 與 XER 檔案。

## 什麼是讀取 MS Project 檔案？
讀取 MS Project 檔案指的是以程式方式開啟 *.mpp*（或其他支援格式，如 XML、XER），並存取其內部資料結構。這些結構包含工作、資源、行事曆、成本表與財務設定。透過解析檔案，您可以在不啟動 Microsoft Project 的情況下擷取資訊，從而實現自動化報表、遷移與整合工作流程。

## 為什麼使用 Aspose.Tasks 讀取 MS Project 檔案？
Aspose.Tasks 提供純 Java 解決方案，免除 COM interop 或本機 Microsoft Project 安裝的需求。它支援超過 20 種檔案格式，能在使用不到 100 MB 記憶體的情況下處理含千項工作的專案，並提供豐富的物件模型。直接存取 `Prj.CURRENCY_CODE` 等常數，讓您即時且可靠地取得貨幣資訊。

## 前置條件
在開始撰寫程式碼之前，請確保您已具備以下條件：

### 已安裝 Java 開發工具包 (JDK)
需要最近的 JDK（11 或更新版）。請從官方 Oracle 網站下載：[here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)。

### Aspose.Tasks for Java 函式庫
取得最新的 Aspose.Tasks for Java 二進位檔，並將其加入專案的 classpath。完整文件與下載連結請參考 [here](https://reference.aspose.com/tasks/java/)。

## 匯入套件
`Project` 類別與 `Prj` 常數位於 `com.aspose.tasks` 命名空間。請在 Java 原始檔的最上方匯入它們：

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 步驟說明

### 步驟 1：設定資料目錄
定義包含 *.mpp* 檔案的資料夾。請依您的環境調整路徑，以便執行階段能正確找到專案檔案。

```java
String dataDir = "Your Data Directory";
```

### 步驟 2：載入專案檔案
`Project` 類別是 Aspose.Tasks 的頂層物件，代表記憶體中的單一 MS Project 檔案。建立實例時會讀取檔案並建構可供查詢的記憶體模型。

```java
Project prj = new Project(dataDir + "project.mpp");
```

### 步驟 3：取得貨幣代碼
`Prj.CURRENCY_CODE` 常數指向儲存 ISO 貨幣識別碼的屬性。呼叫 `prj.get(Prj.CURRENCY_CODE)` 即可在一次操作中返回三字母代碼。

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
輸出將會是三字母 ISO 貨幣代碼（例如 `USD`、`EUR`、`GBP`），即專案設定使用的貨幣。

### 步驟 4：在 Java 中取得貨幣代碼（額外說明）
載入專案後，呼叫 `prj.get(Prj.CURRENCY_CODE)`，並將結果存入 `String`。之後您可以將此值傳遞給任何金融服務、報表引擎或需要貨幣識別碼的 UI 元件。

### 步驟 5：（可選）使用貨幣代碼
典型的下游情境包括：

- **報表產生** – 在成本欄位前加上代碼（`USD 1,200`）。  
- **API 整合** – 將 ISO 代碼傳送至要求貨幣參數的支付閘道。  
- **資料整合** – 依貨幣將多個專案分組，以進行投資組合層級的分析。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **Null 輸出** | 專案檔未定義貨幣（預設為空）。 | 在 Microsoft Project 中設定貨幣，或在讀取前使用 `prj.set(Prj.CURRENCY_CODE, "USD");` 指定。 |
| **找不到檔案** | `dataDir` 路徑不正確。 | 核對路徑，確保檔名完全相符，包含大小寫。 |
| **不支援的檔案版本** | *.mpp* 檔案過舊或已損毀。 | 升級至最新的 Aspose.Tasks 版本，或先在 Microsoft Project 中將檔案轉換為較新格式。 |

## 常見問答

**Q: Aspose.Tasks 能處理複雜的專案結構嗎？**  
A: 能，API 能讀取多層次的工作階層、資源池、自訂欄位與行事曆，沒有限制。

**Q: Aspose.Tasks 相容不同版本的 MS Project 檔案嗎？**  
A: 完全相容。它支援從 Project 98 到最新 Office 版本的 MPP、XML、XER 等格式。

**Q: Aspose.Tasks 提供文件與支援嗎？**  
A: 有完整的 API 參考、程式碼範例，以及 Aspose 官方網站提供的專業技術支援。

**Q: 我可以在購買前試用 Aspose.Tasks 嗎？**  
A: 可以，免費試用版讓您評估所有功能，包括貨幣代碼擷取。

**Q: 哪裡可以取得暫時授權以供評估使用？**  
A: 暫時授權可從 [website](https://purchase.aspose.com/temporary-license/) 取得。

---

**最後更新：** 2026-09-25  
**測試環境：** Aspose.Tasks for Java（最新版本）  
**作者：** Aspose

## 相關教學

- [Project Properties Java – 讀取 Aspose.Tasks 中的中繼資料](/tasks/java/project-properties/)
- [如何使用 Aspose.Tasks for Java 讀取 Microsoft Project 的專案資訊](/tasks/java/project-properties/read-project-info/)
- [在 Aspose.Tasks 中取得 MS Project 大綱代碼](/tasks/java/project-file-operations/retrieve-outline-codes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}