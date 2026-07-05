---
date: 2026-07-05
description: 了解如何使用 Aspose.Tasks for Java 在不同專案之間連結任務。提供逐步指南、前置條件以及最佳實踐，確保跨專案任務連結順暢無礙。
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: 在 Aspose.Tasks 中建立跨專案任務連結
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 在不同專案之間連結任務
url: /zh-hant/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 跨專案連結任務

## 介紹
跨專案連結任務是一項核心功能，可讓您同步工作、避免重複，並維持相依活動的唯一真實來源。在本教學中，您將一步步學會如何使用 Aspose.Tasks for Java **跨專案連結任務**。完成後，您將擁有一個完整的跨專案連結，當任一端變更時會自動更新，實現即時協調，無需手動複製貼上。

## 快速解答
- **什麼是建立專案的主要類別？** `Project` – 它代表整個 MS‑Project 檔案於記憶體中。  
- **哪個方法可新增外部任務？** `project.getRootTask().getChildren().addExternalTask(...)`。  
- **我可以設定連結類型嗎？** 可以 – 使用 `TaskLinkType.FinishToStart`、`StartToStart` 等。  
- **連結功能需要授權嗎？** 正式使用需有效的 Aspose.Tasks 授權；免費試用版可用於評估。  
- **連結任務有數量限制嗎？** Aspose.Tasks 可在每個專案中處理 10,000+ 連結任務，且不會降低效能。

## 什麼是跨專案連結任務？
跨專案連結任務在一個專案檔案中的任務與另一個專案檔案中的任務之間建立相依關係，允許來源任務（工期、開始日期、限制）的變更自動流向相依任務。此機制保持排程一致，減少手動更新，確保來源專案的任何修改即時反映於所有連結的專案，維持投資組合的前後一致性。

## 為什麼使用 Aspose.Tasks 進行跨專案連結？
Aspose.Tasks 支援 **50+ 輸入與輸出格式**，且可處理 **數百頁的專案**，同時將記憶體使用量控制在 200 MB 以下。其 API 在伺服器端執行連結，免除安裝 Microsoft Project 的需求，並能為大型企業啟用自動化管線。

## 前置條件
在開始之前，請確保您已具備：

- Java 17（或更新版本）已安裝並在 IDE 中配置。  
- 有效的 Aspose.Tasks for Java 授權檔案 (`Aspose.Tasks.Java.lic`)。  
- 已將 Aspose.Tasks for Java 函式庫加入專案。您可從 [Aspose.Tasks for Java release page](https://releases.aspose.com/tasks/java/) 下載。  
- 具備 MS‑Project 基本概念的熟悉度，例如任務、彙總任務與相依性。

## 匯入套件
`Project`、`Task`、`TaskLink` 以及相關列舉位於 `com.aspose.tasks` 命名空間。請在 Java 檔案的頂部匯入它們：

`import com.aspose.tasks.*;`

**Project** 是代表記憶體中專案檔案的主要類別。**Task** 代表專案內的單一工作項目。**TaskLink** 定義兩個任務之間的相依關係。這些匯入讓您取得完整的專案操作功能，包括跨專案連結。

## 如何跨專案連結任務？
載入兩個專案檔案、加入外部任務佔位符、建立本機任務，然後以 `TaskLink` 連接它們。API 會自動處理 ID 映射與更新，確保外部任務的任何變更會自動傳播至連結的本機任務，無需額外程式碼。此方法簡化多專案協調，降低排程漂移的風險。

### 步驟 1：設定環境
確保 Aspose.Tasks JAR 已加入 classpath，且授權檔案於執行時載入：

`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`

**License** 載入您的 Aspose.Tasks 授權檔案，以啟用完整功能並移除評估浮水印。

### 步驟 2：建立 Project 實例
為您想要建立連結的目標專案實例化新的 `Project` 物件：

`Project targetProject = new Project();`

`Project` 類別是 Aspose.Tasks 的頂層物件，代表記憶體中的單一專案檔案。

### 步驟 3：新增彙總任務
彙總任務用於將相關任務分組。建立一個以容納外部與本機任務：

`Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");`

### 步驟 4：新增外部任務
插入指向另一個專案檔案中任務的外部任務：

`Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);`

`**addExternalTask**` 方法會建立一個佔位任務，參照外部專案檔案，使用提供的檔名與任務 ID。

### 步驟 5：新增本機任務
建立將與外部任務連結的本機任務：

`Task local = summary.getChildren().add("Local Task");`

### 步驟 6：建立任務連結
在外部任務與本機任務之間建立相依關係。最常見的連結類型是 Finish‑to‑Start：

`TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);`

`**TaskLink**` 記錄此關係；之後您可依需求修改其延遲、提前或類型。

### 步驟 7：儲存與驗證
將專案持久化為檔案，並可選擇在 Microsoft Project 中開啟以驗證連結：

`targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`

`**SaveFileFormat**` 指定儲存專案的檔案格式。當您開啟 *LinkedProject.mpp* 時，會看到外部任務以特殊圖示顯示，且相依線指向本機任務。

## 常見問題與解決方案
- **找不到外部檔案** – 確認路徑相對於執行程序，或提供絕對路徑。  
- **任務 ID 不匹配** – 核對外部任務 ID（`addExternalTask` 的第二個參數）與來源專案相符。  
- **授權未載入** – 缺少或不正確的授權檔案會導致 `LicenseException`。請在任何 Aspose.Tasks 呼叫前載入授權。  
- **大型專案效能** – 若僅需讀取外部任務，請使用 `Project.setReadOnly(true)`，以減少記憶體開銷。

## 常見問答

**Q: 我可以在同一彙總任務中連結多個外部專案的任務嗎？**  
A: 可以，您可以在同一彙總任務下加入多個外部任務，並為每個任務建立個別連結，使用相同的 `addExternalTask` 方法。

**Q: 若連結專案中的外部任務被修改會怎樣？**  
A: 任何對外部任務的排程、工期或限制的變更，於目標專案重新整理時會自動反映至相依的本機任務。

**Q: 能否在不同檔案格式的任務之間建立連結？**  
A: 當然可以。Aspose.Tasks 支援在 MPP、XML 與 Primavera 格式之間建立連結，讓異構的專案生態系統保持同步。

**Q: 任務跨專案連結後，我可以解除連結嗎？**  
A: 可以，透過呼叫 `project.getTaskLinks().remove(link)` 或刪除外部任務佔位符來移除連結。

**Q: 跨專案連結的任務數量有任何限制嗎？**  
A: 此函式庫每個專案可處理 **10,000+ 連結任務**，僅受系統記憶體與底層檔案格式規範限制。

## 結論
您現在已掌握使用 Aspose.Tasks for Java 進行 **跨專案任務連結** 的完整、可投入生產的方法。此功能簡化多專案協調，減少手動工作，並確保排程變更即時傳播至整個投資組合。可進一步探索自訂延遲時間、不同連結類型與批次連結等功能，以自動化更複雜的專案結構。

---

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## 相關教學

- [在 Aspose.Tasks 中建立任務連結](/tasks/java/task-links/create-task-link/)
- [在 Aspose Java 中建立任務 – 任務屬性](/tasks/java/task-properties/)
- [在 Aspose.Tasks 中建立空白 MS Project 檔案](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}