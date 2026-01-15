---
date: 2026-01-15
description: 學習如何將資源新增至專案、更新資源資料，並使用 Aspose.Tasks for Java 將專案儲存為 MPP。
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 為專案新增資源
url: /zh-hant/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 向專案新增資源

## 簡介
在本實作教學中，您將學會 **如何以程式方式將資源新增至專案**，使用 Aspose.Tasks Java API。我們將示範如何載入既有的 MS Project XML 檔案、插入新資源、更新其屬性，最後 **將專案另存為 MPP**。完成後，您將擁有一套可直接套用於任何基於 Java 的報表或自動化工具的可重複使用模式。

## 快速解答
- **「將資源新增至專案」是什麼意思？** 它會在 Microsoft Project 檔案的資源表中建立一筆新條目（人員、設備、材料）。  
- **哪個程式庫負責此功能？** Aspose.Tasks for Java – 無需安裝 Microsoft Project。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線則需購買商業授權。  
- **可以將 XML 轉成 MPP 嗎？** 可以 – 載入 XML 後使用 `project.save(...)` **將專案另存為 MPP**。  
- **需要哪個 Java 版本？** Java 6 或更新版本（建議使用 Java 8 以上）。

## 什麼是「將資源新增至專案」？
將資源新增至專案即是在 MS Project 檔案的 **Resources** 表格中插入一列。此列會儲存名稱、成本費率、群組以及任務日後可參照的自訂欄位等資訊。

## 為什麼使用 Aspose.Tasks for Java？
- **無需 Microsoft Project 依賴** – 可在任何作業系統或 CI 伺服器上執行。  
- **完整保真度** – 在不同格式之間轉換時保留所有原生 Project 功能。  
- **功能豐富的 API** – 讓您讀寫、操作任務、資源、行事曆等。

## 前置條件
在開始之前，請確保您已具備以下項目：

1. 已安裝 Java Development Kit (JDK) 8 或更新版本。  
2. Aspose.Tasks for Java 程式庫 – 可從 [此處](https://releases.aspose.com/tasks/java/) 下載。  
3. 具備基本的 Java 語法與 Maven/Gradle 專案設定知識。

## 匯入套件
在 Java 原始檔中加入必要的 Aspose.Tasks 類別：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## 步驟 1：設定資料目錄
定義來源 XML 與最終產生的 MPP 檔案所在的路徑：

```java
String dataDir = "Your Data Directory";
```

## 步驟 2：指定輸入與輸出檔案
指向欲 **將 XML 轉成 MPP** 的 XML 檔案，以及將包含新資源的目標 MPP 檔案：

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## 步驟 3：載入專案
從 XML 檔案建立 `Project` 物件：

```java
Project project = new Project(file);
```

## 步驟 4：新增資源並設定屬性
此處即 **將資源新增至專案**，並設定其費率與群組：

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*小技巧：* 您可以在迴圈中重複呼叫 `add`，一次執行 **更新多筆資源**。

## 步驟 5：儲存專案
最後，**將專案另存為 MPP** 以寫入變更：

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## 結論
您已學會 **如何以 Aspose.Tasks for Java 向專案新增資源**、更新其屬性，並 **將專案另存為 MPP**。此方法非常適合自動化報表管線、大量資源匯入，或任何需要在未安裝桌面版 Microsoft Project 的情況下操作 MS Project 檔案的情境。

## 常見問題

**Q1: 可以在同一個專案中使用 Aspose.Tasks for Java 更新多筆資源嗎？**  
A: 可以，遍歷 `project.getResources()` 或重複呼叫 `add`，依需求設定每筆資源的欄位。

**Q2: Aspose.Tasks 支援除 MS Project 之外的其他檔案格式嗎？**  
A: 當然支援 – 包括 XML、MPP、MPX、Primavera 等多種格式。

**Q3: Aspose.Tasks 與不同版本的 Java 相嗎？**  
A: 此程式庫相容於 Java 6 及以上版本；建議使用 Java 8 以上以獲得最佳效能。

**Q4: 我可以使用 Aspose.Tasks 執行其他 MS Project 檔案的操作嗎？**  
A: 可以，您能讀寫任務、行事曆、指派、客製欄位，甚至產生報表。

**Q5: 在哪裡可以取得 Aspose.Tasks 的進一步協助或支援？**  
A: 請造訪 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 取得社群協助與官方支援。

---

**最後更新：** 2026-01-15  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}