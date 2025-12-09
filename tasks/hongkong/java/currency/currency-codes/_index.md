---
date: 2025-12-09
description: 學習如何使用 Aspose.Tasks for Java 讀取 MS Project 檔案並有效管理貨幣代碼，輕鬆簡化您的項目管理工作。
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 讀取 MS Project 檔案並管理貨幣代碼
url: /zh-hant/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 讀取 MS Project 檔案並管理貨幣代碼

## 介紹
歡迎！在本教學中，您將學會 **如何讀取 MS Project 檔案** 資料，並使用 Aspose.Tasks Java API **管理貨幣代碼**。無論您是要產生報表、合併多幣別專案，或只是需要確保正確的金融符號顯示，本指南都會一步步帶您完成——從環境設定到程式化取得貨幣代碼。完成後，您將能輕鬆讀取 MS Project 檔案並提取所需的貨幣資訊。

## 快速回答
- **API 的功能是什麼？** 它可讀取 MS Project 檔案並公開諸如貨幣代碼等屬性。  
- **使用哪種語言？** Java，透過 Aspose.Tasks for Java 函式庫。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **可以一行程式碼取得代碼嗎？** 可以——`prj.get(Prj.CURRENCY_CODE)` 會回傳貨幣代碼字串。  
- **支援所有 Project 版本嗎？** Aspose.Tasks 支援舊版 (MPP) 與新版 (XML、XER) 格式。

## 什麼是 **read ms project file**？
讀取 MS Project 檔案指的是以程式方式開啟 *.mpp*（或其他支援格式）專案文件，並存取其資料結構——工作、資源、行事曆與財務設定——而不需要手動操作 Microsoft Project 本身。

## 為什麼使用 Aspose.Tasks 來 **read msproject** 檔案？
- **完整格式支援** – 可處理從 Project 98 到最新 Office 版本的檔案。  
- **不需 COM 或 Office 安裝** – 純 Java，適合伺服器端自動化。  
- **功能豐富的 API** – 直接存取 `Prj.CURRENCY_CODE` 等屬性，讓您 **how to retrieve currency** 資訊即時取得。  
- **效能佳** – 輕量化解析，適合大量專案的批次處理。

## 前置條件
在開始撰寫程式碼之前，請確保您已具備以下條件：

### 已安裝 Java Development Kit (JDK)
請確認您的機器上已安裝最新的 JDK。您可以從[此處](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)下載並安裝最新版本。

### Aspose.Tasks for Java 函式庫
下載並設定 Aspose.Tasks for Java 函式庫。詳細文件與最新二進位檔可於[此處](https://reference.aspose.com/tasks/java/)取得。

## 匯入套件
要開始使用，先在 Java 專案中匯入必要的套件：
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 步驟說明

### 步驟 1：設定資料目錄
定義包含 *.mpp* 檔案的資料夾。請依您的環境調整路徑。
```java
String dataDir = "Your Data Directory";
```

### 步驟 2：載入專案檔案
建立 `Project` 實例以載入 MS Project 檔案。此時即 **read msproject** 資料已載入記憶體。
```java
Project prj = new Project(dataDir + "project.mpp");
```

### 步驟 3：取得貨幣代碼
專案載入後，您可以透過單一呼叫 **how to retrieve currency** 資訊。此範例示範 **get currency code java** 的使用方式。
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
輸出將會是三字母 ISO 貨幣代碼（例如 `USD`、`EUR`、`GBP`），即專案設定的使用貨幣。

### 步驟 4：（可選）使用貨幣代碼
您可能想將取得的代碼用於其他地方——例如在自訂報表中格式化成本值，或傳遞給金融 API。以下為簡要說明（不需額外程式碼區塊）：
- 將代碼存入變數。  
- 在組合金額字串時使用該變數。  
- 傳遞給需要貨幣識別碼的下游服務。

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|-------|--------|-----|
| **Null output** | 專案檔未定義貨幣（預設為空）。 | 在 Microsoft Project 中設定貨幣，或於讀取前透過 `prj.set(Prj.CURRENCY_CODE, "USD");` 指定。 |
| **File not found** | `dataDir` 路徑不正確。 | 檢查路徑，並確保檔名完全相符，包含大小寫。 |
| **Unsupported file version** | 非常舊或損毀的 *.mpp* 檔案。 | 使用最新的 Aspose.Tasks 版本，或先在 Microsoft Project 中將檔案轉換為較新格式。 |

## 常見問答

**Q: Aspose.Tasks 能處理複雜的專案結構嗎？**  
A: 可以，API 能讀取並操作多層任務階層、資源池與自訂欄位，毫無問題。

**Q: Aspose.Tasks 相容於不同版本的 MS Project 檔案嗎？**  
A: 絕對相容。它支援 MPP、XML、XER 等多種格式，涵蓋多個 Microsoft Project 版本。

**Q: Aspose.Tasks 提供文件與支援嗎？**  
A: 完整的文件、程式碼範例與專屬支援皆可於 Aspose 官方網站取得。

**Q: 我可以在購買前試用 Aspose.Tasks 嗎？**  
A: 提供免費試用，讓您評估所有功能，包括讀取貨幣代碼。

**Q: 在哪裡可以取得 Aspose.Tasks 的臨時授權？**  
A: 可於[網站](https://purchase.aspose.com/temporary-license/)取得臨時授權，以進行短期評估。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-09  
**測試環境：** Aspose.Tasks for Java (latest version)  
**作者：** Aspose