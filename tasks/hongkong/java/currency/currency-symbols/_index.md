---
date: 2025-12-05
description: 學習如何使用 Aspose.Tasks for Java 提取 MPP 檔案中的貨幣符號，並變更 Java 中的貨幣符號。快速取得 Java
  的貨幣符號，以便於專案管理。
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 提取 MPP 貨幣符號
url: /zh-hant/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 提取貨幣符號 mpp

## 簡介
在本教學中，您將 **extract currency symbol mpp** 從 Microsoft Project 檔案中提取，並了解如何使用 Aspose.Tasks 函式庫 **change currency symbol java** 或 **retrieve currency symbol java**。無論您是建立報告工具、將 Project 資料整合至財務系統，或僅需在使用者介面中顯示正確的貨幣符號，掌握這項雖小卻關鍵的任務，都能讓您的 Java 應用程式更健全且使用者友好。

## 快速解答
- **“extract currency symbol mpp” 是什麼意思？** 它表示讀取儲存在 MPP（Microsoft Project）檔案中的貨幣符號。  
- **哪個函式庫負責此操作？** Aspose.Tasks for Java 提供簡易的 API 來完成此工作。  
- **我需要授權嗎？** 免費試用可用於開發；商業授權則需於正式環境使用。  
- **需要多久時間？** 使用以下程式碼，您可在不到一分鐘內取得符號。  
- **我也能更改符號嗎？** 可以 —— 只要使用相同的 `Prj.CURRENCY_SYMBOL` 屬性設定新值即可。

## 什麼是 “extract currency symbol mpp”？
Microsoft Project 將貨幣符號（例如 $, €, £）儲存在專案檔案的標頭中。**extract currency symbol mpp** 操作會讀取該值，以便您可以以程式方式顯示或操作它。

## 為什麼要更改 currency symbol java？
專案常跨越多個地區。能在執行時 **change currency symbol java**，即可讓您在不重新建立整個專案檔的情況下，將報告、發票或儀表板調整為當地市場。

## 先決條件
1. **Java Development Kit (JDK)** – 版本 8 或以上。  
2. **Aspose.Tasks for Java** – 從 [Aspose.Tasks 下載頁面](https://releases.aspose.com/tasks/java/) 下載最新的 JAR。  
3. 有效的 **project.mpp** 檔案，放置於可在程式碼中參考的資料夾內。

## 匯入套件
首先，匯入我們處理 Project 檔案所需的類別。

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 步驟 1：定義資料目錄
告訴應用程式 *.mpp* 檔案所在的位置。

```java
String dataDir = "Your Data Directory";
```

> **小技巧：** 使用 `System.getProperty("user.dir")` 來建立在任何機器上皆可使用的絕對路徑。

## 步驟 2：載入 MS Project 檔案
建立一個代表記憶體中 MPP 檔案的 `Project` 物件。

```java
Project project = new Project(dataDir + "project.mpp");
```

## 步驟 3：取得（並可選擇性更改）貨幣符號
現在，我們透過讀取 `Prj.CURRENCY_SYMBOL` 屬性來 **retrieve currency symbol java**。您也可以透過將新字串指派給相同屬性來 **change currency symbol java**。

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
| `NullPointerException` on `project.get(...)` | 檔案路徑錯誤或找不到檔案 | 檢查 `dataDir` 與檔名；使用 `new File(dataDir).exists()` 進行除錯 |
| 符號異常（例如 `?`） | 專案使用非標準語系建立 | 確保來源 MPP 檔案實際定義了貨幣符號；如上所示可程式化設定 |
| 授權錯誤 | 使用試用版卻未提供有效授權檔案 | 在建立 `Project` 物件前，使用 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` 載入授權 |

## 常見問與答

**Q: 我可以使用 Aspose.Tasks 操作除貨幣符號外的其他專案屬性嗎？**  
A: 可以，Aspose.Tasks 允許您編輯工作、資源、指派、行事曆以及許多其他專案屬性。

**Q: Aspose.Tasks 是否相容於不同版本的 MS Project 檔案？**  
A: 完全相容。它支援從 Project 98 到最新版本的 MPP、MPT 以及 XML 格式。

**Q: Aspose.Tasks 是否提供開發人員的文件與支援？**  
A: 官方網站提供完整的 API 文件、程式碼範例以及專屬支援論壇。

**Q: 我可以在購買前試用 Aspose.Tasks 嗎？**  
A: 可以 —— 完整功能的免費試用版可從 [Aspose 官方網站](https://purchase.aspose.com/buy) 下載。

**Q: 我該如何取得 Aspose.Tasks 的臨時授權？**  
A: 臨時授權可於 [Aspose 臨時授權頁面](https://purchase.aspose.com/temporary-license/) 取得，以供評估使用。

---

**最後更新：** 2025-12-05  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}