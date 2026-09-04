---
date: 2026-06-25
description: 了解如何使用 Aspose.Tasks for Java 新增任務並更新 MPP 檔案，這是一個 Java 專案管理函式庫，可讓您建立 Microsoft
  Project 任務檔並將專案儲存為 MPP。
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: 如何在 Aspose.Tasks 中新增任務並更新 MPP 檔案
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中新增任務並更新 MPP 檔案
url: /zh-hant/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中新增工作並更新 MPP 檔案

## 簡介
在本教學中，您將學習 **how to add task** 到現有的 Microsoft Project (MPP) 檔案，然後使用 Aspose.Tasks for Java（領先的 **java project management library**）儲存更新後的排程。無論您是建立自訂排程器、自動化大量更新，或將專案資料整合至更大的系統，下列逐步指南將精確說明如何載入專案、插入新工作、設定其日期，並將結果保存為全新的 MPP 文件。

## 快速解答
- **What does “how to add task” mean in this context?** 它表示在現有的 MPP 檔案中以程式方式建立新的工作項目。  
- **Which library handles the operation?** Aspose.Tasks for Java，一個強大的 java project management library。  
- **Do I need a license?** 免費試用可用於開發；商業授權則需於正式環境使用。  
- **Can I save the result as MPP?** 是的 — 使用 `project.save(..., SaveFileFormat.Mpp)` 以 **save project as mpp**。  
- **What Java version is required?** Java 8 或更新版本。  

## 在 MPP 檔案中「how to add task」是什麼？
新增工作表示將新的工作項目插入專案階層，定義其開始/結束日期，並將變更寫回 MPP 檔案。Aspose.Tasks 抽象化低層檔案格式細節，讓您專注於業務邏輯，同時自動處理資源指派、行事曆與相依關係計算。它亦會更新任何相關的指派，並重新計算專案排程，以維持相依工作之間的一致性。

## 為何使用 Aspose.Tasks for Java？
- **Full compatibility**: 支援 Microsoft Project 2007‑2021 的全部功能（超過 150 種工作類型與 200 個資源欄位），相容率 100%。  
- **Zero‑dependency**: 不需要 COM、Office 或本機函式庫——純 Java API 可在任何 JRE 環境下執行。  
- **Rich feature set**: 包含工作連結、資源分配、自訂欄位與內建報表功能。  
- **High performance**: 可處理多達 10,000 個工作項目的專案，使用低於 200 MB 的記憶體，適合伺服器端自動化。  

## 先決條件
1. **Java Development Environment** – 已安裝並設定 JDK 8+。  
2. **Aspose.Tasks for Java** – 從 [download page](https://releases.aspose.com/tasks/java/) 下載。  
3. **Basic Java knowledge** – 熟悉類別、物件與日期處理。  

## 匯入套件
首先，匯入您需要的類別。這讓您可以存取專案操作、工作屬性與日期處理。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` 代表已載入記憶體中的 Microsoft Project 檔案。`SaveFileFormat` 列舉可儲存的格式，如 MPP 或 PDF。`Task` 模型化專案階層中的單一工作項目。`Tsk` 提供設定或取得值時使用的工作欄位常數。`Calendar` 提供用於定義排程的日期時間工具。

## 步驟 1：定義資料目錄
```java
String dataDir = "Your Data Directory";
```  
將 `"Your Data Directory"` 替換為來源 MPP 檔案所在的絕對路徑。

## 步驟 2：讀取現有專案
`Project` 類別是 Aspose.Tasks 的核心物件，代表記憶體中的 Microsoft Project 檔案。  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
建構子會載入 **SampleMSP2010.mpp**，為您提供完整可操作的物件模型。

## 步驟 3：建立新工作（how to add task）
`Task` 類別代表專案階層中的單一工作項目。  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
此行 **creates task in mpp** 透過將名為 *Task1* 的子項目加入根工作來建立工作。

## 步驟 4：設定開始與結束日期
`Calendar` 類別提供日期時間工具；月份採零基制（例如 `Calendar.JULY`）。  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
此處定義新加入工作項目的排程。請依您的專案時間表調整日期。

## 步驟 5：儲存專案（save project as mpp）
`SaveFileFormat.Mpp` 告訴 Aspose.Tasks 以原生 Microsoft Project 格式寫回檔案。  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
更新後的專案已包含新工作，並以 **AfterLinking.mpp** 保存。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **File not found** | 確認 `dataDir` 以路徑分隔符 (`/` 或 `\\`) 結尾，且檔名正確。 |
| **Incorrect dates** | 請記得 `Calendar` 的月份是零基制；`Calendar.JULY` 代表七月。 |
| **License exception** | 在呼叫任何 API 前先安裝有效的 Aspose.Tasks 授權，以避免評估水印。 |

## 常見問與答
**Q: 如何一次新增多個工作？**  
A: 迭代工作名稱集合，並在迴圈內重複「create task」區塊。

**Q: 可以為新工作設定自訂欄位嗎？**  
A: 可以 — 使用 `task.set(Tsk.CUSTOM_FIELD_x, value)`，其中 *x* 為欄位索引。

**Q: 是否可以將現有工作複製為範本？**  
A: 複製來源工作 (`Task cloned = sourceTask.clone();`)，然後將其加入目標父工作。

**Q: 如果需要更新現有工作而非新增，該怎麼做？**  
A: 透過 ID 取得工作 (`Task existing = project.getRootTask().getChildren().getById(id);`)，並修改其屬性。

**Q: Aspose.Tasks 是否支援儲存為其他格式，例如 PDF 或 PNG？**  
A: 可以 — 使用 `project.save("output.pdf", SaveFileFormat.Pdf);` 或 `SaveFileFormat.Png` 以取得視覺化表示。

---

**最後更新：** 2026-06-25  
**測試版本：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相關教學

- [如何建立 MPP 檔案 – 使用 Aspose.Tasks 建立與儲存空白 MPP 專案](/tasks/java/project-configuration/create-save-mpp/)
- [如何建立專案 – 使用 Aspose.Tasks 設定新工作屬性](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [建立工作清單 Java – 使用 Aspose.Tasks 設定 MS Project 基線](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}