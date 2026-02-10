---
date: 2026-02-10
description: 學習如何使用 Aspose.Tasks for Java 從 MS Project 檔案中擷取貨幣代碼——為 Java 開發者快速取得所需貨幣代碼的簡易方法。
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 從 MS Project 取得貨幣
url: /zh-hant/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspise.Tasks 從 MS Project 取得貨幣

## 簡介
歡迎！在本教學中，您將了解 **how to retrieve currency** 代碼，如何使用 Aspose.Tasks Java API 從 MS Project 檔案中取得。無論您是要產生多貨幣財務報表、整合來自不同地區的專案，或只是需要正確的貨幣符號以供後續處理，本指南將一步步帶領您完成設定環境到以程式方式擷取貨幣代碼的全過程。完成後，您將能熟練讀取 MS Project 檔案，並使用 **get currency code java** 呼叫取得 ISO 貨幣識別碼。

## 快速解答
- **API 的功能是什麼？** 它會讀取 MS Project 檔案並公開諸如貨幣代碼等屬性。  
- **使用哪種語言？** Java，透過 Aspose.Tasks for Java 函式庫。  
- **需要授權嗎？** 免費試用可用於開發；正式上線需購買商業授權。  
- **可以一行程式碼取得代碼嗎？** 可以 — `prj.get(Prj.CURRENCY_CODE)` 會回傳貨幣代碼字串。  
- **是否相容所有 Project 版本？** Aspose.Tasks 支援舊版 (MPP) 與新版 (XML、XER) 格式。

## 什麼是 **read ms project file**？
讀取 MS Project 檔案是指以程式方式開啟 *.mpp*（或其他支援格式）的專案文件，並存取其資料結構——工作、資源、行事曆以及財務設定——而不需手動操作 Microsoft Project 本身。

## 為什麼使用 Aspose.Tasks 來 **read msproject** 檔案？
- **Full format support** – 支援從 Project 98 到最新 Office 版的所有檔案。  
- **No COM or Office installation needed** – 純 Java，適合伺服器端自動化。  
- **Rich API** – 可直接存取如 `Prj.CURRENCY_CODE` 等屬性，讓您即時取得 **how to retrieve currency** 資訊。  
- **Performance** – 輕量級解析，適合大量專案的批次處理。

## 先決條件
在深入程式碼之前，請確保您具備以下條件：

### 已安裝 Java Development Kit (JDK)
請確保您的電腦已安裝最新的 JDK。您可以從 [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載並安裝最新版本的 JDK。

### Aspose.Tasks for Java 函式庫
下載並設定 Aspose.Tasks for Java 函式庫。詳細文件與最新二進位檔可於 [here](https://reference.aspose.com/tasks/java/) 取得。

## 匯入套件
要開始使用，請在您的 Java 專案中匯入必要的套件：
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 逐步指南

### 步驟 1：設定資料目錄
定義包含 *.mpp* 檔案的資料夾。請依您的環境調整路徑。
```java
String dataDir = "Your Data Directory";
```

### 步驟 2：載入專案檔案
透過載入 MS Project 檔案建立 `Project` 實例。此時即會 **read msproject** 資料至記憶體中。
```java
Project prj = new Project(dataDir + "project.mpp");
```

### 步驟 3：取得貨幣代碼
現在專案已載入，您可以 **how to retrieve currency** 資訊，只需一次呼叫即可。此範例示範 **get currency code java** 的使用方式。
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
輸出將會是三字母的 ISO 貨幣代碼（例如 `USD`、`EUR`、`GBP`），即專案設定使用的貨幣代碼。

### 步驟 4：在 Java 中取得貨幣代碼（額外說明）
如果您需要將此值儲存以供日後使用，只需將它指派給變數即可：

*No extra code block is required* – 只要保留 `prj.get(Prj.CURRENCY_CODE)` 回傳的字串，並傳遞給任何金融服務、報表引擎或 UI 元件即可。

### 步驟 5：（可選）使用貨幣代碼
您可能想在其他地方套用取得的代碼，例如在自訂報表中格式化成本值或傳遞給金融 API。典型情境包括：

- **Report generation** – 在成本欄位前加上代碼（例如 `USD 1,200`）。  
- **API integration** – 將 ISO 代碼傳送給需要貨幣識別碼的支付閘道。  
- **Data consolidation** – 依貨幣將多個專案分組，以進行投資組合分析。

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|-------|--------|-----|
| **空值輸出** | 專案檔未定義貨幣（預設為空）。 | 在 Microsoft Project 中設定貨幣，或在讀取前透過 `prj.set(Prj.CURRENCY_CODE, "USD");` 指定。 |
| **找不到檔案** | `dataDir` 路徑不正確。 | 請確認路徑正確，且檔名完全相符（包括大小寫）。 |
| **不支援的檔案版本** | 非常舊或損毀的 *.mpp* 檔案。 | 請使用最新的 Aspose.Tasks 版本，或先在 Microsoft Project 中將檔案轉換為較新格式。 |

## 常見問與答

**Q: Aspose.Tasks 能處理複雜的專案結構嗎？**  
A: 可以，API 能讀取並操作多層次的工作階層、資源池與自訂欄位，毫無問題。

**Q: Aspose.Tasks 是否相容不同版本的 MS Project 檔案？**  
A: 絕對相容。它支援 MPP、XML、XER 等多種格式，涵蓋多個 Microsoft Project 版本。

**Q: Aspose.Tasks 是否提供文件與支援？**  
A: 完備的文件、程式碼範例與專屬支援皆可在 Aspose 官方網站取得。

**Q: 我可以在購買前試用 Aspose.Tasks 嗎？**  
A: 提供免費試用，讓您評估所有功能，包括讀取貨幣代碼。

**Q: 從哪裡可以取得 Aspose.Tasks 的臨時授權？**  
A: 可於 [website](https://purchase.aspose.com/temporary-license/) 取得臨時授權，以供短期評估。

---

**最後更新：** 2026-02-10  
**測試環境：** Aspose.Tasks for Java (latest version)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}