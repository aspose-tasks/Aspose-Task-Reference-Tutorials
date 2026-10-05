---
date: 2026-10-05
description: 了解如何使用 Aspose.Tasks for Java 建立測試專案並計算日期之間的天數、加入自訂欄位，以及有效地操作 MPP 檔案。
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: 在 Aspose.Tasks 中使用公式
og_description: 使用 Aspose.Tasks for Java 建立測試專案並計算日期之間的天數。本指南說明如何加入自訂欄位、設定工作任務截止日期，並將專案儲存為
  MPP 檔案。
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: 建立測試專案並計算日期之間的天數
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: 建立測試專案並計算日期之間的天數
url: /zh-hant/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立測試專案並計算日期之間的天數

在本教學中，您將 **建立測試專案** 並 **計算日期之間的天數**，方法是加入自訂欄位、定義延伸屬性，並透過 Aspose.Tasks for Java 套件套用 Microsoft Project 公式。無論是產生排程、計算截止日期，或是自動化報表，Aspose.Tasks 都能在不需安裝桌面版的情況下以程式方式操作 Project 資料，支援 50 多種輸入與輸出格式，且能在記憶體效能模式下處理上百頁的檔案。

## 快速解答
- **本教學涵蓋什麼內容？** 示範如何建立測試專案、定義延伸屬性、設定工作截止日期，並使用公式計算日期之間的天數。  
- **需要哪個程式庫？** Aspose.Tasks for Java（最新版）。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式環境需購買商業授權。  
- **可以使用哪種 IDE？** 任何支援 JDK 8+ 的 Java IDE（IntelliJ IDEA、Eclipse、VS Code 等）。  
- **實作大約需要多久？** 約 10‑15 分鐘即可複製程式碼並執行。

## Aspose.Tasks 中的「計算日期之間的天數」是什麼？
在 Aspose.Tasks 中，公式是一段字串，可參照工作欄位並執行計算。`[Deadline] - [Finish]` 為 Aspose.Tasks 用來回傳兩個日期欄位之間天數差異的公式語法。結果以數值形式儲存，代表完整天數，可顯示於自訂欄位或用於後續計算。

## 為什麼使用 Aspose.Tasks 計算日期之間的天數？
Aspose.Tasks 提供 **完整的 API 覆蓋**，涵蓋每個 Project、Task 與 Resource 屬性，支援 Windows、Linux 與 macOS，且 **不需要安裝 Microsoft Project 或 Office**。此引擎可在一般伺服器硬體上於一秒內處理 **500+ 工作**，非常適合 CI 流程、Docker 容器與高容量批次處理。

## 如何為工作設定截止日期
java.util.Calendar 是 Java 中表示特定時間點的類別。您可以將 `java.util.Calendar` 值指派給工作之 `Tsk.DEADLINE` 欄位，以設定截止日期。建立 Calendar 例項後，設定年份、月份與日期為目標截止日，然後呼叫 `task.set(Tsk.DEADLINE, calendar);`。此截止日期會儲存在專案檔中，並可在公式如 `[Deadline] - [Finish]` 中使用。

## 如何定義延伸屬性
延伸屬性是一個自訂欄位，用來儲存公式的結果。您只需建立一次，給予易讀的別名，並附加 `[Deadline] - [Finish]` 表達式，讓每個工作自動計算間隔。透過實例化 `ExtendedAttribute`、設定 Alias、指派公式，最後加入專案的集合即可完成。

## 前置條件
在開始之前，請確保您已具備以下項目：

- **Java Development Kit (JDK) 8+** – 從 Oracle 官方網站或 AdoptOpenJDK 下載。  
- **Aspose.Tasks for Java** – 從 [Aspose.Tasks for Java 下載頁面](https://releases.aspose.com/tasks/java/) 取得最新 JAR，並加入專案的 classpath 或 Maven/Gradle 相依性。

## 匯入套件
首先，匯入我們需要的類別：

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## 步驟說明

### 步驟 1：建立帶有自訂欄位的測試專案
我們先 **建立測試專案**，並加入一個稍後會存放公式結果的自訂欄位。

```java
Project project = CreateTestProjectWithCustomField();
```

> *小技巧：* `CreateTestProjectWithCustomField()` 是一個輔助方法，用於建立最小排程並註冊可供公式指派的延伸屬性。

### 步驟 2：定義延伸屬性（新增自訂欄位）
接著，我們 **定義延伸屬性**——即自訂欄位——並給予易讀的別名。這裡會 **新增自訂欄位** 的邏輯。

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** 讓欄位在 Project 中易於辨識。  
- **Formula** 計算工作 *Finish* 日期與 *Deadline* 之間的天數——即 *計算日期之間的天數* 的核心。

### 步驟 3：為工作設定截止日期（新增截止日期工作並設定工作截止日期）
現在，我們透過設定特定工作之 *Deadline* 屬性來 **新增截止日期工作** 資料。

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` 例項定義了精確的截止時間點。  
- `set(Tsk.DEADLINE, …)` **設定工作截止日期** 給予選定的工作。

### 步驟 4：儲存專案（操作 Microsoft Project 檔案）
最後，我們 **操作 Microsoft Project**，將變更寫入 MPP 檔案。

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

您可以在 Microsoft Project 中開啟 `SaveFile.mpp`，查看自訂欄位、公式結果與截止日期在排程中的呈現。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **公式未評估** | 確認屬性的 `Formula` 字串使用正確的欄位名稱（例如 `[Deadline]`、`[Finish]`）。 |
| **找不到工作** | 核實範例中的工作 ID（`1`）是否存在；可使用 `project.getRootTask().getChildren().size()` 進行除錯。 |
| **授權例外** | 在呼叫任何 API 方法前先套用有效的 Aspose.Tasks 授權 (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`)。 |

## 常見問答

**Q: 我可以在其他程式語言中使用 Aspose.Tasks 嗎？**  
A: 可以，Aspose.Tasks 提供 .NET、Java 以及其他平台的 API，讓您以自己熟悉的語言操作 Microsoft Project 檔案。

**Q: Aspose.Tasks 有免費試用版嗎？**  
A: 當然有。可從 [Aspose.Tasks 下載頁面](https://releases.aspose.com/) 取得功能完整的試用版。

**Q: 哪裡可以找到 Aspose.Tasks 的詳細文件？**  
A: 官方文件位於 [Aspose.Tasks Java API 參考文件](https://reference.aspose.com/tasks/java/)。

**Q: 如何取得 Aspose.Tasks 的支援？**  
A: 前往 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 提問，與社群分享與交流經驗。

**Q: 評估時需要臨時授權嗎？**  
A: 可取得臨時授權以進行短期測試；請至 [臨時授權申請頁面](https://purchase.aspose.com/temporary-license/) 申請。

**最後更新：** 2026-10-05  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時最新版本）  
**作者：** Aspose

## 相關教學

- [如何建立 MPP 檔案 – 使用 Aspose.Tasks 建立並儲存空白專案](/tasks/java/project-configuration/create-save-mpp/)
- [使用 Aspose.Tasks for Java 設定 MS Project 專案開始日期](/tasks/java/project-properties/write-project-info/)
- [在 Java 中使用 Aspose.Tasks 建立延伸屬性](/tasks/java/resource-management/extended-resource-attributes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}