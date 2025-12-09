---
date: 2025-12-07
description: 學習如何在使用 Aspose.Tasks for Java 操作 Microsoft Project 檔案時，**建立測試專案**及**新增自訂欄位**。
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 建立測試專案並在 Aspose.Tasks for Java 中使用公式
url: /zh-hant/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立測試專案並在 Aspose.Tasks for Java 中使用公式

## 介紹
在本教學中，你將 **建立測試專案** 檔案、加入自訂欄位，並使用 Aspose.Tasks for Java 套件來處理 MS Project 公式。Aspose.Tasks 讓以程式方式 **操作 Microsoft Project** 資料變得相當簡單——無論是產生排程、計算日期或自動化報表。完成本指南後，你將擁有一個可執行的範例，示範如何定義延伸屬性、為工作設定截止日期，並將專案儲存為 MPP 檔案。

## 快速答覆
- **本教學涵蓋什麼內容？** 建立測試專案加入自訂欄位、定義延伸屬性，以及使用公式設定工作截止日期。  
- **需要哪個套件？** Aspose.Tasks for Java（最新版本）。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買授權。  
- **可以使用哪種 IDE？** 任何支援 JDK 8+ 的 Java IDE（IntelliJ IDEA、Eclipse、VS Code 等）。  
- **實作大約需要多久？** 約 10‑15 分鐘即可複製程式碼並執行。

## 什麼是 Aspose.Tasks 中的「測試專案」？
**測試專案** 是以程式方式建立的輕量級 Microsoft Project 檔案，用來示範或驗證功能。它只包含最少的工作、資源與自訂欄位，讓你在不影響真實專案資料的情況下進行操作。

## 為什麼使用 Aspose.Tasks 操作 Microsoft Project？
- **完整 API 覆蓋** – 可存取每個 Project、Task、Resource 屬性。  
- **不需安裝 Office** – 可在伺服器、CI 流程與 Docker 容器中執行。  
- **跨平台** – 同一段 Java 程式碼可在 Windows、Linux、macOS 上執行。  
- **強大的公式引擎** – 直接在專案檔內計算日期、工期與自訂欄位。

## 前置需求
在開始之前，請確保已具備以下項目：

- **Java Development Kit (JDK) 8+** – 可從 Oracle 官方網站或 AdoptOpenJDK 下載。  
- **Aspose.Tasks for Java** – 從 [Aspose.Tasks for Java 下載頁面](https://releases.aspose.com/tasks/java/) 取得最新 JAR，並加入專案的 classpath 或 Maven/Gradle 依賴中。

## 匯入套件
首先，匯入我們將會使用的類別：

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## 步驟說明

### 步驟 1：建立帶有自訂欄位的測試專案
我們先 **建立測試專案**，並加入稍後會存放公式結果的自訂欄位。

```java
Project project = CreateTestProjectWithCustomField();
```

> *小技巧：* `CreateTestProjectWithCustomField()` 是一個輔助方法，用來建立最小排程並註冊可供公式使用的延伸屬性。

### 步驟 2：定義延伸屬性（加入自訂欄位）
接著，我們 **定義延伸屬性**——也就是自訂欄位，並為它設定易讀的別名。這裡就是加入 **自訂欄位** 邏輯的地方。

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **別名** 讓欄位在 Project 中顯示為可讀名稱。  
- **公式** 計算工作 *Finish* 日期與 *Deadline* 之間的天數。

### 步驟 3：為工作設定截止日期（加入截止日期工作並設定工作截止日期）
現在，我們透過設定特定工作之 *Deadline* 屬性來 **加入截止日期工作** 資料。

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` 例項定義了精確的截止時間。  
- `set(Tsk.DEADLINE, …)` **設定工作截止日期** 給選定的工作。

### 步驟 4：儲存專案（操作 Microsoft Project 檔案）
最後，我們 **操作 Microsoft Project**，將變更寫入 MPP 檔案。

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

你可以在 Microsoft Project 中開啟 `SaveFile.mpp`，查看自訂欄位、公式結果與截止日期在排程中的呈現。

## 常見問題與解決方案
| 問題 | 解決方案 |
|------|----------|
| **公式未計算** | 確認屬性的 `Formula` 文字使用正確的欄位名稱（例如 `[Deadline]`、`[Finish]`）。 |
| **找不到工作** | 檢查範例中使用的工作 ID（`1`）是否存在；可使用 `project.getRootTask().getChildren().size()` 進行除錯。 |
| **授權例外** | 在呼叫任何 API 方法前先套用有效的 Aspose.Tasks 授權 (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`)。 |

## 常見問答

**Q: 我可以在其他程式語言中使用 Aspose.Tasks 嗎？**  
A: 可以，Aspose.Tasks 提供 .NET、Java 以及其他平台的 API，讓你能以自己熟悉的語言 **操作 Microsoft Project** 檔案。

**Q: Aspose.Tasks 有免費試用版嗎？**  
A: 有的。可從 [Aspose.Tasks 下載頁面](https://releases.aspose.com/) 取得功能完整的試用版。

**Q: 我在哪裡可以找到 Aspose.Tasks 的詳細文件？**  
A: 官方文件位於 [Aspose.Tasks Java API 參考文件](https://reference.aspose.com/tasks/java/)。

**Q: 如何取得 Aspose.Tasks 的技術支援？**  
A: 前往 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 提問，與社群成員交流經驗。

**Q: 評估期間需要臨時授權嗎？**  
A: 有提供短期測試用的臨時授權，你可以在此處申請 [臨時授權](https://purchase.aspose.com/temporary-license/)。

---

**最後更新：** 2025-12-07  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}