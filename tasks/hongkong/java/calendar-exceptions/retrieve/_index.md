---
date: 2025-11-29
description: 學習如何使用 Aspose.Tasks for Java 從 MS Project 取得行事曆例外。此 Aspose.Tasks Java
  教程提供逐步程式碼範例。
linktitle: Retrieve Calendar Exceptions with Aspose.Tasks – asp tasks java tutorial
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 取得行事曆例外 – ASP Tasks Java 教學
url: /zh-hant/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 以 Aspose.Tasks 取得行事曆例外 – asp tasks java 教程

## 介紹
在本 **asp tasks java 教程** 中，您將學習如何使用 Aspose.Tasks for Java 從 Microsoft Project 檔案中取得行事曆例外。行事曆例外代表非工作期間，例如假期或自訂工作時間規則，能以程式方式讀取它們對於資源平衡、報表以及自訂排程邏輯都相當重要。我們將一步一步說明完整流程，讓您能自信地將此功能整合到自己的 Java 應用程式中。

## 快速回答
- **本教程涵蓋什麼內容？** 使用 Aspose.Tasks for Java 從 MPP 檔案取得行事曆例外。  
- **實作需要多長時間？** 基本設定約需 10‑15 分鐘。  
- **先備條件？** JDK、Aspose.Tasks for Java 以及 IDE（IntelliJ IDEA 或 Eclipse）。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **支援哪些 Project 版本？** 所有主要的 MS Project 格式（MPP、MPT、XML）。

## 什麼是 asp tasks java 教程？
**asp tasks java 教程** 說明如何在 Java 專案中使用 Aspose.Tasks API。它提供具體的程式碼片段、最佳實踐說明與實務案例，讓開發者在不安裝 Microsoft Project 的情況下操作 Project 檔案。

## 為什麼要取得行事曆例外？
了解行事曆例外可讓您：
- 產生符合假期與自訂工作排程的精確專案時間表。  
- 建立能突顯非工作日的自訂報表工具。  
- 將 Project 行事曆與外部系統（如 ERP、HR）同步。

## 先備條件
在開始之前，請確保您已具備以下條件：

1. **Java Development Kit (JDK)** – 請安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 [此處](https://releases.aspose.com/tasks/java/) 下載並安裝。  
3. **整合開發環境 (IDE)** – 您可使用任意喜好的 IDE，例如 IntelliJ IDEA 或 Eclipse。

## 匯入套件
首先，您需要匯入使用 Aspose.Tasks 所必需的套件：

```java
import com.aspose.tasks.*;
```

## 步驟 1：設定資料目錄
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

> **小技巧：** 使用絕對路徑或相對於專案 resources 資料夾的路徑，可避免 `FileNotFoundException`。

## 步驟 2：載入 MS Project 檔案
```java
Project project = new Project(dataDir + "project.mpp");
```

此行程式碼會根據指定路徑建立一個新的 `Project` 物件，並載入 MS Project 檔案。

## 步驟 3：取得行事曆例外
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

此段程式會遍歷專案中的每個行事曆，然後遍歷該行事曆內的每個例外，並印出例外的開始與結束日期。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **沒有輸出結果** | 專案檔案未包含任何行事曆例外。 | 確認在 MS Project 中已為行事曆定義例外（例如假期）。 |
| **`NullPointerException`** | `dataDir` 路徑不正確或找不到檔案。 | 再次檢查目錄路徑，並確保 `project.mpp` 存在。 |
| **時區不符** | 日期以 UTC 顯示。 | 如有需要，可使用 `calExc.getFromDate().toLocalDateTime()` 轉換為本地時間。 |

## 常見問答
### Aspose.Tasks 能處理不同版本的 MS Project 檔案嗎？
是的，Aspose.Tasks 支援多種版本的 MS Project 檔案，包括 MPP、MPT 與 XML 格式。

### Aspose.Tasks 有提供免費試用嗎？
有，您可從 [此處](https://releases.aspose.com/) 下載 Aspose.Tasks 的免費試用版。

### 哪裡可以找到 Aspose.Tasks for Java 的文件說明？
請參考文件說明 [此處](https://reference.aspose.com/tasks/java/)。

### 如何取得 Aspose.Tasks 的技術支援？
您可在社群論壇取得支援，網址在 [此處](https://forum.aspose.com/c/tasks/15)。

### 是否提供臨時授權給 Aspose.Tasks？
有，您可從 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**其他問答**

**問：** *取得例外後，我可以修改行事曆例外嗎？*  
**答：** 當然可以。使用 `CalendarException.setFromDate()` 與 `setToDate()` 調整日期，然後以 `project.save(...)` 儲存專案。

**問：** *Aspose.Tasks 會保留行事曆上的自訂欄位嗎？*  
**答：** 會的，載入與儲存專案時，所有自訂欄位與延伸屬性皆會被保留。

## 結論
在本 **asp tasks java 教程** 中，我們學會了如何使用 Aspose.Tasks for Java 從 MS Project 取得行事曆例外。只要依照上述簡易步驟，即可將此功能無縫整合至您的 Java 應用程式，提供更豐富的排程功能與更精確的專案分析。

---

**最後更新：** 2025-11-29  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}