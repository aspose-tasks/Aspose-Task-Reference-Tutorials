---
date: 2026-09-30
description: 了解如何使用 Java 與 Aspose.Tasks 在 MPP 專案中設定進度，這是一個強大的 Java 專案管理函式庫。請跟隨此逐步指南。
keywords:
- how to set progress
- java project management library
- Aspose.Tasks Java
- MPP project Java
lastmod: 2026-09-30
linktitle: 變更 Aspose.Tasks 任務的進度
og_description: 使用 Java 與 Aspose.Tasks 在 MPP 專案中設定進度，這是領先的 Java 專案管理函式庫。取得完整的無程式碼指南。
og_image_alt: Guide showing how to set task progress in an MPP file using Aspose.Tasks
  for Java
og_title: 如何使用 Java 設定 MPP 專案的進度 – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to set progress in an MPP project with Java using Aspose.Tasks,
    a robust java project management library. Follow this step‑by‑step guide.
  headline: How to set progress in an MPP project using Java and Aspose.Tasks
  type: TechArticle
- description: Learn how to set progress in an MPP project with Java using Aspose.Tasks,
    a robust java project management library. Follow this step‑by‑step guide.
  name: How to set progress in an MPP project using Java and Aspose.Tasks
  steps:
  - name: Set up your Java project
    text: Create a new Maven or Gradle project and add the Aspose.Tasks JAR to your
      classpath. This gives you access to the `Project`, `Task`, and related classes.
  - name: Define the document directory
    text: Specify where the project file will be stored. Replace the placeholder with
      the actual path on your machine. `dataDir` is a string that specifies the folder
      path where the MPP file will be saved.
  - name: Create a new project (create mpp project java)
    text: '`Project` represents an in‑memory Microsoft Project file that can be saved
      to .mpp format.'
  - name: Add a task to the project (add task project)
    text: '`Task` is an object representing a single work item within a Project.'
  - name: Set the task’s progress
    text: '`Tsk.PERCENT_COMPLETE` is the field that stores a task’s completion percentage.'
  - name: Display the updated progress
    text: Reading `Tsk.PERCENT_COMPLETE` returns the current progress value for the
      task. By following these steps you have successfully **created an MPP project
      in Java**, added a task, and **changed its progress** – all using Aspose.Tasks.
  type: HowTo
- questions:
  - answer: Any recent version (2023‑2025) supports `Project` creation; using the
      latest release ensures you have all bug fixes and performance improvements.
    question: What version of Aspose.Tasks is required to create an MPP file?
  - answer: Yes, call `project.save("output.pdf", SaveFileFormat.PDF);` after setting
      the progress to generate a visual report.
    question: Can I export the project to PDF after updating progress?
  - answer: Loop through `project.getRootTask().getChildren()` and set `Tsk.PERCENT_COMPLETE`
      for each task; the API updates each task efficiently.
    question: Is it possible to batch‑update progress for many tasks?
  - answer: Resources must be added explicitly; task progress does not affect resource
      allocation unless you modify resource‑related fields.
    question: Does the library handle resource assignments automatically?
  - answer: Use `project.setPassword("yourPassword");` before calling `project.save(...)`
      to encrypt the file.
    question: How do I protect the generated MPP file with a password?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task progress
title: 如何使用 Java 和 Aspose.Tasks 在 MPP 專案中設定進度
url: /zh-hant/java/task-properties/change-progress/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 MPP 專案中使用 Java 和 Aspose.Tasks 設定進度

## 簡介
在現代的 **java project management** 中，能夠 **create mpp project java** 檔案並保持任務進度即時更新對於按時交付至關重要。本教學示範如何使用 Aspose.Tasks 以程式方式 **設定進度**，Aspose.Tasks 是一個功能強大的 **java project management library**，可在 Windows、Linux 與 macOS 上運行。您將看到完整流程——從專案建立到驗證更新後的完成百分比——以對話式、逐步說明的方式呈現。

## 快速解答
- **「create mpp project java」是什麼意思？**  
  它指的是使用 Java 程式碼以程式方式產生 Microsoft Project（.mpp）檔案。  
- **哪個函式庫可以協助完成此工作？**  
  Aspose.Tasks for Java，一個專用的 **java project management library**。  
- **設定任務進度需要多少行程式碼？**  
  在專案實例化後，少於 10 行程式碼即可完成。  
- **在正式環境使用是否需要授權？**  
  是的，需要商業授權；亦提供免費試用版。  
- **可以在任何 Java IDE 上執行嗎？**  
  當然可以——任何支援 Java 8+ 的 IDE 都能運作。  

## 什麼是「create mpp project java」？
在 Java 中建立 MPP 專案是指使用程式碼產生 Microsoft Project 檔案（`.mpp`），該檔案可於 Microsoft Project 或任何相容檢視器開啟。此方式可實現排程自動產生、大量任務建立，以及與企業系統的無縫整合。

## 為什麼要將 Aspose.Tasks 作為 java project management library 使用？
Aspose.Tasks 提供 **full API coverage** 以進行專案建立、任務操作與報告。它支援 **30 多種輸入與輸出格式**，且能在不將整個檔案載入記憶體的情況下處理 **多達 10,000 個任務** 的專案，於一般硬體上提供高效能處理。

## 先決條件
在開始之前，請確保您具備以下條件：

1. **Java Development Environment** – JDK 8 或以上已安裝並設定。  
2. **Aspose.Tasks for Java Library** – 從官方網站下載：[Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/)。  
3. **Document Directory** – 您機器上用於儲存產生的 `.mpp` 檔案的資料夾。  

## 匯入套件
首先，匯入您需要的 Aspose.Tasks 類別。此程式碼片段會設定環境，稍後我們會加入一個 50% 進度的任務。  
`com.aspose.tasks.*` 提供核心類別，例如 **Project**、**Task** 與 **Tsk**，用於操作 MPP 檔案。  

```java
import com.aspose.tasks.*;
```

## 逐步指南

### 步驟 1：設定您的 Java 專案
建立一個新的 Maven 或 Gradle 專案，並將 Aspose.Tasks JAR 加入 classpath。這樣即可使用 `Project`、`Task` 以及相關類別。

### 步驟 2：定義文件目錄
指定專案檔案的儲存位置。將佔位符替換為您機器上的實際路徑。  
`dataDir` 是一個字串，用於指定儲存 MPP 檔案的資料夾路徑。  

```java
String dataDir = "Your Document Directory";
```

### 步驟 3：建立新專案（create mpp project java）
`Project` 代表一個位於記憶體中的 Microsoft Project 檔案，可儲存為 .mpp 格式。  

```java
Project project = new Project(dataDir + "project.mpp");
```

### 步驟 4：向專案新增任務（add task project）
`Task` 是代表專案內單一工作項目的物件。  

```java
Task task = project.getRootTask().getChildren().add("Task");
```

### 步驟 5：設定任務的進度
`Tsk.PERCENT_COMPLETE` 是儲存任務完成百分比的欄位。  

```java
task.set(Tsk.PERCENT_COMPLETE, percent(50));
```

### 步驟 6：顯示更新後的進度
讀取 `Tsk.PERCENT_COMPLETE` 可取得該任務目前的進度值。  

```java
System.out.println(task.get(Tsk.PERCENT_COMPLETE));
```

依照上述步驟，您已成功 **在 Java 中建立 MPP 專案**、新增任務，並 **變更其進度**——全部皆透過 Aspose.Tasks 完成。

## 如何在 Aspose.Tasks 中設定任務的進度？
載入現有的 `Project` 物件，定位目標 `Task`（或建立新任務），並為 `Tsk.PERCENT_COMPLETE` 指派新值。函式庫會自動重新計算父任務的彙總值，使整體排程保持一致。只需這一行程式碼即可更新進度。

## 常見問題與疑難排解
- **FileNotFoundException** – 確認 `dataDir` 以檔案分隔符（`/` 或 `\`）結尾，且目錄已存在。  
- **LicenseException** – 在正式環境使用時，於建立 `Project` 物件之前載入 Aspose.Tasks 授權。  
- **Incorrect percent value** – `percent` 方法期望的值介於 0 到 100 之間，超出此範圍會拋出例外。  

## 常見問答

**Q: 建立 MPP 檔案需要哪個版本的 Aspose.Tasks？**  
A: 任何近期版本（2023‑2025）皆支援 `Project` 建立；使用最新發行版可確保取得所有錯誤修正與效能提升。  

**Q: 更新進度後可以將專案匯出為 PDF 嗎？**  
A: 可以，於設定進度後呼叫 `project.save("output.pdf", SaveFileFormat.PDF);` 以產生視覺化報告。  

**Q: 能否批次更新多個任務的進度？**  
A: 透過迴圈 `project.getRootTask().getChildren()`，為每個任務設定 `Tsk.PERCENT_COMPLETE`；API 會有效率地更新每個任務。  

**Q: 函式庫會自動處理資源指派嗎？**  
A: 必須手動加入資源；任務進度不會影響資源分配，除非您修改與資源相關的欄位。  

**Q: 如何使用密碼保護產生的 MPP 檔案？**  
A: 在呼叫 `project.save(...)` 前使用 `project.setPassword("yourPassword");` 以加密檔案。  

## 結論
掌握在 Java 中 **設定 MPP 專案進度** 的技巧，可讓您自動化排程維護、讓利害關係人即時掌握資訊，並將專案資料整合至更大的企業工作流程。Aspose.Tasks 作為領先的 **java project management library**，使這些工作變得簡單且具高效能。

---

**最後更新：** 2026-09-30  
**測試環境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose

## 相關教學

- [Java 專案管理：使用 Aspose.Tasks 設定任務完成百分比](/tasks/java/task-properties/percentage-complete-calculations/)
- [如何使用 Aspose.Tasks for Java 更新任務資料為 MPP 格式](/tasks/java/task-properties/update-task-data/)
- [使用 Aspose.Tasks for Java 讀取與設定任務優先順序](/tasks/java/task-properties/handle-priorities/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}