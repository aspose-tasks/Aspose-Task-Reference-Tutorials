---
date: 2025-12-04
description: 學習如何使用 Aspose.Tasks for Java 從 MS Project 檔案中讀取貨幣屬性。請跟隨本分步指南，程式化提取貨幣代碼、符號、位數及位置。
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 專案在 Java 中讀取貨幣屬性
url: /zh-hant/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 讀取 Java 貨幣屬性於 Microsoft Project

## 介紹
在本教學中，您將使用 Aspose.Tasks for Java API **讀取 Java 貨幣屬性**，從 Microsoft Project 檔案中取得。Aspose.Tasks 允許您在未安裝 Microsoft Project 的情況下操作 .mpp 檔案，非常適合自動化報告、資料遷移或整合至基於 Java 的企業應用程式。完成本指南後，您將能直接從專案檔案中提取貨幣代碼、符號、小數位數以及符號位置。

## 快速回答
- **「read currency properties java」是什麼意思？** 指的是使用 Java 程式碼從 MS Project 檔案中取得與貨幣相關的中繼資料（代碼、符號、位數、位置）。  
- **需要授權才能試用嗎？** Aspose.Tasks 提供免費試用版；正式環境需購買商業授權。  
- **需要哪個版本的 JDK？** Java 8 或更高版本。  
- **讀取後可以修改貨幣設定嗎？** 可以，Aspose.Tasks 同時支援讀寫貨幣屬性。  
- **是否相容所有 .mpp 版本？** 此 API 支援 Microsoft Project 2003‑2021 所產生的檔案。

## 什麼是讀取貨幣屬性 Java？
在 Java 中讀取貨幣屬性是指存取專案層級的設定，這些設定決定 Microsoft Project 檔案中金額的顯示方式。設定內容包括 ISO 貨幣代碼（例如 **USD**）、符號（**$**）、小數位數，以及符號是放在金額前還是後。

## 為什麼使用 Aspose.Tasks 讀取貨幣屬性 Java？
- **不需安裝 Microsoft Project** – 只要有支援 Java 的平台即可使用此 API。  
- **快速、在程式內即時抽取** – 適合批次處理大量專案檔案。  
- **完整控制** – 可將取得的值與自訂報表結合，或整合至 ERP 系統。  
- **跨版本支援** – 可處理從 Project 2003 到最新 2021 版的 .mpp 檔案。

## 前置條件
在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 已安裝 Java 8 或更新版本，且已在PATH` 中設定。  
2. **Aspose.Tasks for Java JAR** – 從 [here](https://releases.aspose.com/tasks/java/) 下載最新程式庫，並加入專案的 classpath。

## 匯入套件
先匯入操作專案所需的 Aspose.Tasks 命名空間：

```java
import com.aspose.tasks.*;
```

## 步驟 1：設定專案目錄
定義包含欲分析的 `.mpp` 檔案的資料夾。將路徑存於變數可提升程式的可重用性：

```java
String dataDir = "Your Data Directory";
```

*將 `"Your Data Directory"` 替換為 `project.mpp` 所在資料夾的絕對或相對路徑。*

## 步驟 2：建立專案讀取器實例
將 Microsoft Project 檔案載入 `Project` 物件。此物件可讓您存取所有專案屬性，包括貨幣設定：

```java
Project project = new Project(dataDir + "project.mpp");
```

*若檔名不同，請相應更改 `"project.mpp"`。*

## 步驟 3：顯示貨幣屬性
使用 `Prj` 列舉取得每項貨幣屬性，並將結果印出至主控台。API 會回傳可轉換為字串的物件供顯示：

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**您將看到的內容：**  
- **Currency Code** – ISO‑4217 代碼，例如 `USD`、`EUR`、`JPY`。  
- **Currency Digits** – 大多數貨幣為 `2` 位，小數位為 `0` 的例子如日圓。  
- **Currency Symbol** – 報表中顯示的符號（`$`、`€`、`¥`）。  
- **Currency Symbol Position** – `0` 代表**前置**符號，`1` 代表**後置**符號。

## 步驟 4：處理完成
發出訊息表示抽取已成功結束。當程式作為大型批次作業的一部份執行時，此簡短訊息相當有用：

```java
System.out.println("Process completed Successfully");
```

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| **FileNotFoundException** | `dataDir` 路徑不正確或檔名拼寫錯誤。 | 核對目錄字串，並確保 `.mpp` 檔案確實存在於指定位置。 |
| **NullPointerException on `project.get(...)`** | 專案檔未包含貨幣資訊（可能性低）或屬性鍵錯誤。 | 在讀取前使用 `project.contains(Prj.CURRENCY_CODE)` 檢查是否存在。 |
| **LicenseException** | 在生產環境中未使用有效的 Aspose.Tasks 授權。 | 在建立 `Project` 物件前先載入授權檔：`License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## 常見問答

**Q: Aspose.Tasks 是否相容所有版本的 Microsoft Project？**  
A: Aspose.Tasks 支援由 Microsoft Project 2003‑2021 產生的 .mpp 檔案，涵蓋舊版與最新格式。

**Q: 我可以使用 Aspose.Tasks 修改貨幣屬性嗎？**  
A: 可以，您既能讀取也能寫入貨幣設定。範例：`project.set(Prj.CURRENCY_CODE, "EUR");`，之後儲存專案。

**Q: Aspose.Tasks 適合商業使用嗎？**  
A: 當然。它是商業授權的函式庫，您可於 [here](https://purchase.aspose.com/buy) 購買授權。

**Q: Aspose.Tasks 提供免費試用嗎？**  
A: 有，完整功能的試用版可從 [here](https://releases.aspose.com/) 取得。

**Q: 我該向哪裡尋求 Aspose.Tasks 的協助或支援？**  
A: 官方 Aspose.Tasks 論壇是最佳支援管道，請前往 [here](https://forum.aspose.com/c/tasks/15) 參與討論。

## 結論
您現在已學會如何使用 Aspose.Tasks for Java **讀取 Java 貨幣屬性**，從 MS Project 檔案中取得相關資訊。此功能讓您能在不依賴 Microsoft Project 的情況下，將貨幣中繼資料整合至自訂報表、財務分析或整合流程中。歡迎嘗試修改屬性或結合其他專案屬性，打造更豐富的解決方案。

---

**最後更新：** 2025-12-04  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}