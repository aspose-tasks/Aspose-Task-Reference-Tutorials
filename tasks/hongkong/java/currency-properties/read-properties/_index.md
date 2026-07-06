---
date: 2026-02-07
description: 學習如何使用 Aspose.Tasks for Java 從 MS Project 檔案中讀取貨幣屬性（Java）並提取貨幣符號（Java）。跟隨本步驟指南，程式化提取貨幣代碼、符號、小數位數及位置。
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 專案在 Java 中讀取貨幣屬性
url: /zh-hant/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 專案閱讀 Java 貨幣屬性

## 介紹
在本教學中，您將 **read currency properties java** 從 Microsoft Project 檔案中讀取，使用 Aspose.Tasks for Java API。Aspose.Tasks 讓您在未安裝 Microsoft Project 的情況下操作 .mpp 檔案，非常適合自動化報表、資料遷移或整合至基於 Java 的企業應用程式。完成本指南後，您將能直接從專案檔案中擷取貨幣代碼、符號、小數位數以及符號位置。

## 快速解答
- **What does “read currency properties java” mean?** 它指的是使用 Java 程式碼從 MS Project 檔案中取得與貨幣相關的中繼資料（代碼、符號、位數、位置）。  
- **Do I need a license to try this?** 可使用 Aspose.Tasks 的免費試用版；商業使用需購買授權。  
- **Which JDK version is required?** Java 8 或更新版本。  
- **Can I modify the currency settings after reading them?** 可以，Aspose.Tasks 同時支援讀寫貨幣屬性。  
- **Is this compatible with all .mpp versions?** 此 API 支援 Microsoft Project 2003‑2021 所建立的檔案。

## 什麼是 read currency properties java？
在 Java 中讀取貨幣屬性即是存取專案層級的設定，這些設定決定在 Microsoft Project 檔案中金額如何顯示。設定內容包括 ISO 貨幣代碼（例如 **USD**）、符號（**$**）、小數位數，以及符號是放在金額前還是後。

## 為什麼要使用 Aspose.Tasks 讀取 read currency properties java？
- **No Microsoft Project installation needed** – 此 API 可在任何支援 Java 的平台上執行。  
- **Fast, in‑process extraction** – 非常適合批次處理大量專案檔案。  
- **Full control** – 您可以將取得的值與自訂報表結合，或整合至 ERP 系統。  
- **Cross‑version support** – 支援從 Project 2003 到最新 2021 版的 .mpp 檔案。

## 前置條件
在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 已安裝 Java 8 或更新版本，並在 `PATH` 中設定。  
2. **Aspose.Tasks for Java JAR** – 從 [here](https://releases.aspose.com/tasks/java/) 下載最新程式庫，並加入專案的 classpath。  

## 匯入套件
先匯入操作專案所需的 Aspose.Tasks 命名空間：

```java
import com.aspose.tasks.*;
```

## 步驟 1：設定專案目錄
定義包含欲分析的 `.mpp` 檔案的資料夾。將路徑存於變數中可提升程式碼的可重用性：

```java
String dataDir = "Your Data Directory";
```

*將 `"Your Data Directory"` 替換為 `project.mpp` 所在資料夾的絕對或相對路徑。*

## 步驟 2：建立 Project 讀取器實例
將 Microsoft Project 檔案載入 `Project` 物件。此物件可讓您存取所有專案屬性，包括貨幣設定：

```java
Project project = new Project(dataDir + "project.mpp");
```

*如果檔案名稱不同，請相應更改 `"project.mpp"`。*

## 步驟 3：顯示貨幣屬性
使用 `Prj` 列舉取得每個貨幣屬性，並將結果印出至主控台。API 會回傳可轉換為字串的物件供顯示：

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**您將看到的內容：**  
- **Currency Code** – ISO‑4217 代碼，例如 `USD`、`EUR`、`JPY`。  
- **Currency Digits** – 大多數貨幣為 `2` 位，小數點後 0 位則為日圓。  
- **Currency Symbol** – 報表中顯示的字元（`$`、`€`、`¥`）。  
- **Currency Symbol Position** – `0` 代表 **before** 金額，`1` 代表 **after**。

## 如何提取 currency symbol java？
如果您只關心符號本身，可聚焦於 `Prj.CURRENCY_SYMBOL` 屬性。相同的 `project.get(...)` 呼叫會回傳符號，您可以將其儲存、記錄或傳遞給其他服務進一步處理。此方式特別適合在金融儀表板或在地化 UI 元件中 **extract currency symbol java**。

## 步驟 4：處理完成
發出訊息表示抽取已成功完成。此簡短訊息在程式作為大型批次作業的一部份執行時相當有用：

```java
System.out.println("Process completed Successfully");
```

## 常見問題與解決方案
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir` 路徑不正確或檔名拼寫錯誤。 | 核對目錄字串，並確保 `.mpp` 檔案確實存在於指定位置。 |
| **NullPointerException on `project.get(...)`** | 專案檔未包含貨幣資訊（較少見）或屬性鍵錯誤。 | 在讀取前使用 `project.contains(Prj.CURRENCY_CODE)` 檢查是否存在。 |
| **LicenseException** | 在生產環境中未使用有效的 Aspose.Tasks 授權。 | 在建立 `Project` 物件前，先載入授權檔：`License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## 常見問答

**Q: Aspose.Tasks 是否相容所有版本的 Microsoft Project？**  
A: Aspose.Tasks 支援由 Microsoft Project 2003‑2021 產生的 .mpp 檔案，涵蓋舊版與最新格式。

**Q: 我可以使用 Aspose.Tasks 修改貨幣屬性嗎？**  
A: 可以，您既能讀取也能寫入貨幣設定。使用 `project.set(Prj.CURRENCY_CODE, "EUR");` 後再儲存專案。

**Q: Aspose.Tasks 適合商業使用嗎？**  
A: 當然。它是商業授權的函式庫，您可於 [here](https://purchase.aspose.com/buy) 購買授權。

**Q: Aspose.Tasks 提供免費試用嗎？**  
A: 有，完整功能的試用版可從 [here](https://releases.aspose.com/) 取得。

**Q: 我該向哪裡尋求 Aspose.Tasks 的協助或支援？**  
A: 官方 Aspose.Tasks 論壇是最佳支援管道，請前往 [here](https://forum.aspose.com/c/tasks/15) 。

## 其他常見問答（AI 優化）

**Q: 如何在 Java 中程式化只提取貨幣符號？**  
A: 呼叫 `project.get(Prj.CURRENCY_SYMBOL)`，並將結果轉型為 `String`。即可取得專案檔中使用的精確符號。

**Q: 能否從受密碼保護的 .mpp 檔案讀取貨幣屬性？**  
A: 能。使用接受密碼參數的 `Project` 建構子載入檔案，然後如前所示讀取屬性。

**Q: 大量處理專案檔時的效能如何？**  
A: Aspose.Tasks 於同一進程內執行，通常在數毫秒內讀取標準 .mpp 檔案。若進行批次作業，建議盡可能重複使用同一個 `Project` 實例。

## 結論
您現在已學會如何 **read currency properties java** 與 **extract currency symbol java**，從 MS Project 檔案中使用 Aspose.Tasks for Java 取得貨幣資訊。此功能讓您能在不依賴 Microsoft Project 的情況下，將貨幣中繼資料整合至自訂報表、財務分析或整合管道。歡迎自行嘗試修改屬性，或將此資料與其他專案屬性結合，打造更豐富的解決方案。

---

**最後更新：** 2026-02-07  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}