---
date: 2026-02-10
description: 學習如何使用 Aspose.Tasks for Java 讀取貨幣屬性並在 MS Project 檔案中設定貨幣值。逐步指南，教您提取貨幣代碼以及調整貨幣格式。
linktitle: How to Read Currency
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 於 Java 讀取貨幣屬性
url: /zh-hant/java/currency-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 讀取 Currency Properties Java with Aspose.Tasks

## 介紹
準備好提升您在 Aspose.Tasks for Java 的專業能力了嗎？在本教學中，您將會了解 **如何從 Microsoft Project 檔案讀取 currency properties java**，以及在需要時 **如何設定 currency** 值。掌握這些屬性可協助您在國際專案中保持財務資料的一致性，避免換算錯誤，並向利害關係人呈現清晰的成本報告。

## 快速回答
- **「read currency」是什麼意思？** 從專案檔案中擷取貨幣代碼、符號與格式。  
- **為什麼要調整貨幣設定？** 以符合專案預算的區域格式或客戶的要求。  
- **需要授權嗎？** 生產環境必須使用有效的 Aspose.Tasks for Java 授權；免費試用版可用於評估。  
- **支援哪些 Project 版本？** 完全支援 .mpp（Microsoft Project 2007‑2024）與 .xml 格式。  
- **需要額外設定嗎？** 只要將 Aspose.Tasks for Java 的 JAR 加入 classpath，並匯入相關類別即可。

## 在 Aspose.Tasks 專案中讀取 Currency Properties Java
在專案管理的動態領域中，擷取貨幣細節對於精確的成本分析至關重要。我們的專屬指南 **[Reading Currency Properties in Aspose.Tasks Projects](./read-properties/)** 會一步步帶您從開啟專案檔案到取得貨幣代碼、符號與格式。完成教學後，您將能夠：

* 取得整個專案使用的貨幣代碼（例如 USD、EUR）。  
* 取得貨幣符號與數字格式設定。  
* 利用這些資訊產生在地化的成本報告或供給財務儀表板使用。

了解如何讀取貨幣可確保您能審核專案預算、比較不同區域的成本，並符合會計準則。

## 如何使用 Aspose.Tasks 以 Java 抽取 Currency Code
如果您只需要 ISO‑4217 識別碼，API 提供了直接的屬性：

* `project.getCurrencyCode()` 會回傳三字母代碼，例如 **USD** 或 **EUR**。  
* 此值可儲存、記錄，或傳遞給外部金融服務進行換算。

以程式方式抽取貨幣代碼在您將專案資料與 ERP 系統整合、且系統要求統一代碼時特別有用。

## 如何使用 Aspose.Tasks 以 Java 調整 Currency Format
不同地區需要不同的數字格式（小數點分隔符、千位分隔符等）。使用以下屬性即可微調顯示方式：

* `project.setCurrencySymbol("€")` – 設定顯示符號。  
* `project.setCurrencyDecimalSeparator(",")` – 定義小數點分隔符。  
* `project.setCurrencyThousandsSeparator(".")` – 定義千位分隔符。  

調整貨幣格式可確保每位利害關係人看到熟悉的數字樣式，減少誤解。

## 如何在 Aspose.Tasks 專案中設定 Currency Properties
當專案進入新市場或客戶要求不同的貨幣格式時，您需要 **以程式方式設定 currency** 值。我們的逐步指南 **[Setting Currency Properties in Aspose.Tasks Projects](./set-properties/)** 說明如何：

* 為整個專案定義新的貨幣代碼與符號。  
* 調整數字格式（小數位數、千位分隔符）以符合在地慣例。  
* 在不遺失任何既有資料的情況下儲存更新後的專案檔案。

掌握設定貨幣的技巧，您即可完全控制排程的財務呈現，輕鬆在 USD、GBP、JPY 或任何支援的貨幣間切換。

## 為什麼要精通 Aspose.Tasks 的 Currency Handling？
* **全球協作：** 不同國家的團隊可以本地格式檢視成本。  
* **精確報告：** 防止四捨五入或換算錯誤影響預算。  
* **合規性：** 符合區域會計標準與客戶規範。  
* **自動化：** 於專案產生過程中以程式方式套用貨幣設定，減少手動編輯。

## 真實案例
* **跨國專案：** 一家建築公司同時管理歐洲與北美的工地，需要同時以 EUR 與 USD 呈現預算。  
* **財務稽核：** 稽核人員需要清楚看到每筆成本的貨幣背景。  
* **動態定價模型：** SaaS 供應商根據客戶所在的本地貨幣調整訂閱費用。

## 常見陷阱與技巧
* **陷阱：** 變更代碼後忘記更新貨幣符號。  
  **技巧：** 變更代碼時同時設定符號，避免顯示不一致。  
* **陷阱：** 依賴執行程式機器的預設區域設定。  
  **技巧：** 在 Aspose.Tasks 程式碼中明確指定所需的貨幣格式，確保跨環境的一致性。  

## Currency Properties 教學
### [Read Currency Properties in Aspose.Tasks Projects](./read-properties/)
學習如何使用 Aspose.Tasks for Java 從 MS Project 檔案抽取貨幣資訊。提供逐步教學。

### [Set Currency Properties in Aspose.Tasks Projects](./set-properties/)
學習如何以 Java 在 Aspose.Tasks 專案中設定貨幣屬性，輕鬆操作 Microsoft Project 檔案。

## 常見問答

**Q: 可以在專案已儲存後變更貨幣嗎？**  
A: 可以。使用 `Project.setCurrencyCode()` 及相關方法，然後再次儲存專案。

**Q: 變更貨幣會影響既有的成本值嗎？**  
A: 數值本身不會改變，僅會更新顯示格式（符號、小數點分隔符）。若需要在不同貨幣間換算，必須自行重新計算成本。

**Q: 可以定義多少種貨幣？**  
A: Aspose.Tasks 支援任何 ISO‑4217 貨幣代碼，實質上沒有上限。

**Q: 若開啟的專案使用不支援的貨幣代碼會怎樣？**  
A: 函式庫會回退至預設貨幣（USD）並記錄警告；您可以手動設定所需的貨幣以覆寫此行為。

**Q: 能否在 Project XML 檔案中讀寫貨幣屬性？**  
A: 當然可以。相同的 API 同時支援 .mpp 與 .xml 格式。

---

**最後更新：** 2026-02-10  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}