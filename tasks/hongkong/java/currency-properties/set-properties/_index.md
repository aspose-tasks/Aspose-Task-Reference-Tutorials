---
date: 2025-12-04
description: 了解如何在 Aspose.Tasks Java 專案中設定貨幣，包括如何變更貨幣及變更貨幣符號（Java）。輕鬆操作 Microsoft
  Project 檔案。
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 專案中設定貨幣 – Java 指南
url: /zh-hant/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 專案中設定貨幣 – Java 指南

## 介紹
在本教學中，您將學習 **如何設定貨幣** 於 Microsoft Project 檔案，使用 Aspose.Tasks Java API。無論您需要為國際團隊 *變更貨幣*，或在 Java 中調整 *貨幣符號*，以下步驟將以清晰說明與可直接執行的程式碼，引導您完成整個流程。

## 快速解答
- **需要的函式庫是什麼？** Aspose.Tasks for Java。  
- **我可以變更貨幣符號嗎？** 可以 – 使用 `CurrencySymbolPositionType` 與 `Prj.CURRENCY_SYMBOL`。  
- **支援哪些檔案格式？** XML、MPP，以及透過 `SaveFileFormat` 支援的其他多種格式。  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式上線需購買授權。  
- **實作大約需要多久？** 基本設定約需 5‑10 分鐘。

## 專案檔案中的「貨幣」是什麼？
專案的貨幣決定成本數值的顯示方式——代碼（例如 `AUD`）、小數位數、符號（`$`）以及符號的位置。設定這些屬性可確保所有與成本相關的欄位（資源費率、工作項目預算等）皆以正確的貨幣格式呈現給使用者。

## 為何使用 Aspose.Tasks 變更貨幣？
- **不需安裝 Microsoft Project** – 可在任何伺服器上操作檔案。  
- **完整 API 覆蓋** – 所有與貨幣相關的欄位皆可透過 `Prj` 常數存取。  
- **跨平台** – 可在 Windows、Linux、macOS 上執行，支援任何相容 Java 的 IDE。  
- **高效能** – 能快速且可靠地處理大型專案檔案。

## 前置條件
1. **Java Development Kit (JDK)** – 版本 8 或以上。  
2. **Aspose.Tasks for Java** – 從 [Aspose.Tasks 下載頁面](https://releases.aspose.com/tasks/java/) 取得最新 JAR。  
3. **IDE** – Eclipse、IntelliJ IDEA 或您偏好的任何編輯器。  
4. **可寫入的資料夾** – 用於儲存產生的專案檔案。

## 匯入套件
首先，匯入提供專案屬性與檔案處理功能的類別。

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 步驟說明

### 步驟 1：定義資料目錄
指定包含來源檔案的資料夾，以及輸出檔案寫入的目標位置。

```java
String dataDir = "Your Data Directory";
```

### 步驟 2：建立新 Project 實例
建立一個全新的 `Project` 物件。此物件代表記憶體中的 Microsoft Project 檔案。

```java
Project project = new Project();
```

### 步驟 3：設定貨幣屬性
在此步驟中，我們 **設定貨幣** 的相關細節，如代碼、位數、符號以及符號位置。

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **小技巧：** 若需為現有專案 **變更貨幣**，只要先以 `new Project("file.mpp")` 載入檔案，再套用上述設定即可。

### 步驟 4：儲存更新後的專案
將專案寫回磁碟，使用所需的格式。本範例使用 XML 格式，也可選擇 `SaveFileFormat.MPP`。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### 步驟 5：確認成功
印出友善訊息，以確認操作已順利完成且未發生錯誤。

```java
System.out.println("Process completed Successfully");
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **`project.save` 時發生 NullPointerException** | `dataDir` 不是有效路徑或缺乏寫入權限。 | 確保目錄存在且 Java 程序具有寫入權限。 |
| **貨幣符號未顯示** | 符號位置對於您的語系設定不正確。 | 若符號應置於金額前，請使用 `CurrencySymbolPositionType.Before`。 |
| **專案檔無法在 MS Project 中開啟** | 以較舊格式儲存且設定不相容。 | 使用 `SaveFileFormat.MPP` 儲存，以確保與最新 MS Project 完全相容。 |

## 常見問答

**Q: 我可以在單一專案中使用 Aspose.Tasks 設定多種貨幣嗎？**  
A: 可以，Aspose.Tasks 允許在同一專案檔案中透過針對資源或工作項目設定貨幣屬性，來處理多種貨幣。

**Q: Aspose.Tasks 是否相容於不同版本的 Microsoft Project 檔案？**  
A: 完全相容。此函式庫支援從 Project 2000 到最新版本的 MPP 檔案，同時也支援 XML 及其他格式。

**Q: Aspose.Tasks 是否支援自訂貨幣格式？**  
A: 可以，您可以自訂符號、小數位數與位置，以符合任何區域需求。

**Q: 我可以將 Aspose.Tasks 與其他 Java 函式庫或框架整合嗎？**  
A: 當然可以。此 API 為純 Java，能與 Spring、Hibernate、Maven、Gradle 以及其他生態系統無縫整合。

**Q: 我該從哪裡取得 Aspose.Tasks 的進一步支援或協助？**  
A: 前往 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 取得社群協助，或參考官方文件以取得詳細的 API 參考。

## 結論
您現在已了解 **如何設定貨幣**、如何 **變更貨幣** 數值，以及如何以 Aspose.Tasks for Java 以 **Java 方式變更貨幣符號**。這些功能讓您能為全球團隊客製化成本資料、產生符合在地需求的報表，並確保專案檔案在跨地域時保持一致。

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}