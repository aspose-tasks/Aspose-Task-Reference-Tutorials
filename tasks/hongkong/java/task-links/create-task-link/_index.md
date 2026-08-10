---
date: 2026-07-05
description: 了解如何在 Java 中使用 Aspose.Tasks 建立專案管理任務相依性。請跟隨本 step‑by‑step 指南及 code snippets。
keywords:
- project management task dependencies
- Aspose.Tasks Java
- task linking tutorial
linktitle: 在 Aspose.Tasks 中建立專案管理任務相依性
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  headline: Create Project Management Task Dependencies in Aspose.Tasks
  type: TechArticle
- description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  name: Create Project Management Task Dependencies in Aspose.Tasks
  steps:
  - name: Set Document Directory
    text: Define the directory where your documents are stored to ensure Aspose.Tasks
      locates and processes files correctly. The `java.nio.file.Paths` utility helps
      you build platform‑independent file paths. java // The path to the documents
      directory. String dataDir = "Your Document Directory";
  - name: Initialize Project and Tasks
    text: Create a new project and initialize tasks within it. In this example, "Task
      1" and "Task 2" are added to the root task. The `Task` class represents an individual
      work item; each task can have its own ID, name, and schedule. java Project project
      = new Project(dataDir + "project5.mpp"); Task pred = pr
  - name: Establish Task Link
    text: Utilize the `getTaskLinks()` method to add a link between two tasks. This
      example demonstrates linking "Task 1" as a predecessor to "Task 2." The `TaskLink`
      object defines the type of dependency (Finish‑to‑Start, Start‑to‑Start, etc.)
      and optional lag. java TaskLink link = project.getTaskLinks().add
  - name: Display Result
    text: Print a message indicating the successful completion of the task link creation
      process. This step is crucial for debugging and verification. A simple `System.out.println`
      call confirms that the link was added without errors. java // Display the result
      of the conversion. System.out.println("Task Link
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks seamlessly integrates with Spring, Jakarta EE, Android,
      and any standard Java environment.
    question: Can I use Aspose.Tasks for Java with other Java frameworks?
  - answer: Yes, explore the functionalities with the [free trial](https://releases.aspose.com/)
      before making a commitment.
    question: Is there a free trial available before purchasing the library?
  - answer: Acquire a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: Yes, check the documentation for comprehensive sample projects and code
      snippets.
    question: Are there any sample projects available for reference?
  - answer: Secure your copy by visiting the [purchase page](https://purchase.aspose.com/buy)
      and explore licensing options.
    question: What is the recommended way to purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks 中建立專案管理任務相依性
url: /zh-hant/java/task-links/create-task-link/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 建立專案管理任務相依性

## 介紹
專案管理任務相依性是任何結構良好排程的基礎，能自動計算開始日期、結束日期與關鍵路徑。在本教學中，您將學會如何使用 Aspose.Tasks 於 Java 中建立 **專案管理任務相依性**，此函式庫支援超過 50 種檔案格式，且可在不將整個檔案載入記憶體的情況下處理上千個任務的專案。依照以下步驟連結任務、驗證連結，並將解決方案整合至實務應用中。

## 快速解答
- **本教學涵蓋什麼內容？** 使用 Aspose.Tasks for Java 建立任務連結（相依性）。  
- **需要多少行程式碼？** 主要的連結邏輯僅需兩行程式碼。  
- **試用是否需要授權？** 提供 30 天免費試用；正式環境需購買授權。  
- **支援哪些 Java 版本？** 完全支援 Java 8 至 17。  
- **可以連結超過兩個任務嗎？** 可以——對任意數量的前置‑後置任務對重複此連結模式。

## 什麼是專案管理任務相依性？
專案管理任務相依性定義一個任務的開始或結束如何與另一個任務相關，決定工作必須執行的順序。Aspose.Tasks 透過 `TaskLink` 物件來表示這些關係，您可以以程式方式建立、修改或刪除它們。

## 為什麼使用 Aspose.Tasks 進行任務連結？
Aspose.Tasks 支援 **50+ 輸入與輸出格式**（包括 MPP、XML、CSV），且可在一般伺服器上使用不到 200 MB 記憶體處理 **10,000+ 任務** 的專案。其 API 讓您對連結類型、延遲時間與限制條件擁有精細控制，且不需安裝 Microsoft Project。

## 前置條件
在開始教學之前，請確保您已具備以下條件：
- Java 開發環境：在您的機器上設定可正常運作的 Java 開發環境。  
- Aspose.Tasks 程式庫：下載並整合 Aspose.Tasks for Java 程式庫，可於[此處](https://releases.aspose.com/tasks/java/)取得。

## 匯入套件
要開始使用，請在 Java 專案中匯入必要的套件。這對存取 Aspose.Tasks 功能至關重要。

`Project` 類別是 Aspose.Tasks 的入口點，代表記憶體中的整個專案檔案。  
```text
```java
import com.aspose.tasks.*;
```
```

## 如何使用 Aspose.Tasks for Java 建立任務連結？
載入或建立 `Project` 實例，加入所需任務，然後呼叫 `getTaskLinks().add()` 以建立相依性。此方法會建立一個 `TaskLink` 物件，連結前置與後置任務，並可選擇指定連結類型與延遲時間。以下步驟將逐步說明您所需的完整程式碼——不需要額外的樣板程式。

### 步驟 1：設定文件目錄
定義儲存文件的目錄，以確保 Aspose.Tasks 能正確找到並處理檔案。

`java.nio.file.Paths` 工具可協助您建立跨平台的檔案路徑。  
```text
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
```

### 步驟 2：初始化專案與任務
建立新專案並於其中初始化任務。本例在根任務下加入「Task 1」與「Task 2」。

`Task` 類別代表單一工作項目；每個任務都有自己的 ID、名稱與排程。  
```text
```java
Project project = new Project(dataDir + "project5.mpp");
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
```
```

### 步驟 3：建立任務連結
利用 `getTaskLinks()` 方法在兩個任務之間加入連結。本例示範將「Task 1」作為「Task 2」的前置任務。

`TaskLink` 物件定義相依類型（如 Finish‑to‑Start、Start‑to‑Start 等）以及可選的延遲時間。  
```text
```java
TaskLink link = project.getTaskLinks().add(pred, succ);
```
```

### 步驟 4：顯示結果
簡單的 `System.out.println` 呼叫可確認連結已成功加入且無錯誤。  
```text
```java
// Display the result of the conversion.
System.out.println("Task Link Creation Process Completed Successfully");
```
```

對於更複雜的任務連結情境，請重複這些步驟、客製化任務名稱，並依據專案需求建立相依性。

請參考 [Aspose.Tasks 文件](https://reference.aspose.com/tasks/java/) 以取得詳細的 API 資訊。  
如需社群支援，請造訪 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)。

## 常見問題與解決方案
`save` 方法會將專案寫入指定的檔案路徑，保存所有變更，包括已加入的連結。  
`TaskLinkType` 列舉定義相依關係類型，例如 `FinishToStart` 表示完成對開始的相依性。

- **連結未出現在已儲存的檔案中** – 確認在加入連結後呼叫 `project.save(outputPath)`。  
- **連結類型不正確** – 使用 `TaskLinkType.FinishToStart`、`StartToStart` 等，以符合您的排程邏輯。  
- **大型專案導致記憶體激增** – 在載入前啟用 `project.setReadOnly(true)`，以串流模式運作。

## 常見問答
**問：我可以將 Aspose.Tasks for Java 與其他 Java 框架一起使用嗎？**  
**答：可以，Aspose.Tasks 可無縫整合至 Spring、Jakarta EE、Android 以及任何標準 Java 環境。**

**問：購買程式庫前是否提供免費試用？**  
**答：是的，您可在作出決定前透過[免費試用](https://releases.aspose.com/) 了解功能。**

**問：如何取得 Aspose.Tasks for Java 的臨時授權？**  
**答：可於[此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權，用於測試與評估。**

**問：是否有可供參考的範例專案？**  
**答：有，請查閱文件以取得完整的範例專案與程式碼片段。**

**問：購買 Aspose.Tasks for Java 的建議方式是什麼？**  
**答：請前往[購買頁面](https://purchase.aspose.com/buy) 取得授權，並了解各種授權方案。**

---

**最後更新：** 2026-07-05  
**測試環境：** Aspose.Tasks 24.12 for Java  
**作者：** Aspose

## 相關教學

- [Create Tasks Aspose Java – Task Properties](/tasks/java/task-properties/)
- [Project Management Baseline – Task Scheduling with Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)
- [How to Create Resources – Resource Management with Aspose.Tasks for Java](/tasks/java/resource-management/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}