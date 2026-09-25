---
date: 2026-09-25
description: 了解如何在 Java 中使用 Aspose.Tasks 建立專案排程。本指南將示範如何新增彙總任務、管理專案層級結構，以及有效設定文件目錄。
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: 在 Aspose.Tasks 中建立任務
og_description: 了解如何在 Java 中使用 Aspose.Tasks 建立專案排程。遵循逐步說明，新增彙總任務、管理層級結構，並設定文件目錄。
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: 如何使用 Aspose.Tasks for Java 建立專案排程
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: 如何使用 Aspose.Tasks for Java 建立專案排程
url: /zh-hant/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks for Java 建立專案排程

## 介紹
在本教學中，您將學習如何在 Java 應用程式中使用 Aspose.Tasks **建立專案排程**。無論您是要建立簡單的待辦清單，還是複雜的企業級規劃工具，以下步驟都會帶您逐步加入彙總工作、管理專案層級，並設定文件目錄——全部以清晰、可執行的程式碼片段示範。完成後，您將擁有一個完整結構的排程，可供進一步操作或匯出。

## 快速解答
- **Aspose.Tasks 管理什麼？** 它處理工作層級、資源、行事曆以及專案檔案格式（MS‑Project、Primavera 等）。  
- **開發時需要授權嗎？** 評估期間可使用免費臨時授權；正式上線則需完整授權。  
- **支援哪個 Java 版本？** 完全支援 Java 8 及更新版本。  
- **可以為工作新增自訂欄位嗎？** 可以，透過 API 您可以使用使用者自訂欄位擴充工作。  
- **內建支援甘特圖嗎？** Aspose.Tasks 可匯出包含甘特圖視覺化的 PDF/HTML。

## 什麼是 Aspose.Tasks 中的專案排程？
專案排程是指完整的工作、相依性與時間線集合，定義工作如何執行。Aspose.Tasks 將此資訊儲存在 `Project` 物件中，您可以讀取、修改並以各種格式儲存。它包含開始與結束日期、限制條件以及資源指派，提供完整的規劃與報表功能。

## 為何在 Java 專案管理中使用 Aspose.Tasks？
Aspose.Tasks 支援 **30 多種輸入與輸出格式**，且可在不將整個檔案載入記憶體的情況下處理 **多達 10,000 個工作**，為大型 Java 專案管理場景提供高效能。

## 前置條件
在開始教學之前，請確保已具備以下條件：
- **Java Development Kit (JDK)** – 已在機器上安裝 JDK 8 或更新版本。  
- **Aspose.Tasks for Java library** – 從 [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/) 下載並安裝程式庫。  
- **Integrated Development Environment (IDE)** – 使用 Eclipse、IntelliJ IDEA，或任何您偏好的 Java 開發環境。

## 匯入套件
`Project`、`Task` 以及相關類別位於 `com.aspose.tasks` 命名空間。請在 Java 檔案的頂部匯入它們：

`Project` 類別代表完整的專案排程，提供操作工作與資源的方法。

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

`Project` 類別是所有專案檔案操作的入口點。

## 如何使用 Aspose.Tasks 建立專案排程？

載入新的 `Project` 實例，設定文件目錄，然後開始新增工作。以下段落說明核心流程：您先建立 `Project`，設定其 `RootFolder`（文件目錄），接著加入彙總工作，再加入子工作。所有變更會保留在記憶體中，直到呼叫 `save` 將排程寫入檔案。

### 步驟 1：設定文件目錄
定義最終產生的專案檔案寫入位置。提前設定目錄可確保之後的所有儲存操作使用一致的路徑。

`RootFolder` 屬性指定讀取或寫入專案檔案的基礎資料夾。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### 步驟 2：建立新專案
建立一個全新的 `Project` 物件，用以保存您的排程。您也可以選擇傳入既有檔案路徑，以載入現有排程進行修改。

`Project` 建構函式會建立一個空的排程，準備加入工作。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 步驟 3：新增彙總工作
彙總工作用於將相關子工作分組，並在甘特圖中顯示為可折疊節點。使用 `Task` 類別並將 `IsSummary` 設為 `true`。

`addTask` 方法會在指定的父項下建立新工作，並回傳其 ID。

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### 步驟 4：新增子工作
子工作會繼承其彙總工作設定的開始/結束日期，除非您自行覆寫。新增子工作只需再次呼叫 `addTask`，並指定父工作 ID。

使用帶有父項 ID 的 `addTask` 會在該彙總工作下加入子工作。

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

持續依需求新增任意數量的工作與子工作。每一步都在構建結構化的專案層級，最終可匯出為 MS‑Project、PDF 或其他支援格式。

## 常見問題與解決方案
- **問題：**「找不到文件目錄。」  
  **解決方案：**確認您指派給 `RootFolder` 的路徑在檔案系統中確實存在，且 Java 程序具備寫入權限。  
- **問題：**子工作未出現在彙總工作下。  
  **解決方案：**呼叫 `addTask` 時務必傳入正確的父工作 ID。API 需要將父 ID 作為第二個參數。  
- **問題：**大型專案導致 OutOfMemoryError。  
  **解決方案：Aspose.Tasks 以串流模式處理工作；可增加 JVM 堆積大小（`-Xmx2g`）或將排程拆分為多個檔案。

## 常見問與答
**Q: Aspose.Tasks 適用於小型專案嗎？**  
A: 絕對適用。此程式庫可從單一工作清單擴展至具千餘工作項的企業級排程。

**Q: 在哪裡可以找到 Aspose.Tasks for Java 的詳細文件？**  
A: 請參考文件 [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/)。

**Q: 如何取得 Aspose.Tasks 的臨時授權？**  
A: 前往 [temporary license request page](https://purchase.aspose.com/temporary-license/) 取得可用於開發與測試的時限授權。

**Q: 我可以使用 Aspose.Tasks 自訂工作屬性嗎？**  
A: 可以，您能透過自訂欄位、指派資源以及程式化修改行事曆來擴充工作。

**Q: 是否有 Aspose.Tasks 使用者的支援社群？**  
A: 當然！請加入 Aspose.Tasks 社群於 [the support forum](https://forum.aspose.com/c/tasks/15)。

---

**最後更新：** 2026-09-25  
**測試環境：** Aspose.Tasks 24.12 for Java  
**作者：** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## 相關教學

- [在 MS Project 中使用 Aspose.Tasks for Java 設定專案開始日期](/tasks/java/project-properties/write-project-info/)
- [在 Aspose.Tasks 中建立專案管理工作相依性](/tasks/java/task-links/create-task-link/)
- [如何在 Aspose.Tasks 中新增資源至專案並建立資源指派](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}