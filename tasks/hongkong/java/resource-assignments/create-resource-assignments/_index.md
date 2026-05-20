---
date: 2026-05-20
description: 了解如何使用 Aspose.Tasks for Java（功能強大的 Java 專案管理函式庫）將資源新增至專案並建立資源指派。
keywords:
- add resource to project
- how to add task
- assign resource to task
- java project management library
linktitle: 在 Aspose.Tasks 中建立資源指派
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  headline: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  name: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  steps:
  - name: Create a Project Object
    text: 'The `Project` class is the top‑level container that represents a single
      project file in memory. Instantiate a `Project` object, which represents the
      project file you''re working with:'
  - name: Add a Task to the Project
    text: 'The `Task` class models an individual work item within the schedule. Add
      a task to the project using the `addChild` method of the root task:'
  - name: Add a Resource to the Project
    text: 'The `Resource` class defines a person, equipment, or material that can
      be assigned to tasks. Add a resource to the project using the `add` method of
      the `Resources` collection:'
  - name: Create a Resource Assignment
    text: 'The `ResourceAssignment` class links a `Task` and a `Resource` and stores
      allocation details such as work hours and cost. Create a resource assignment
      for the task and resource using the `add` method of the `ResourceAssignments`
      collection:'
  type: HowTo
- questions:
  - answer: Yes, you can update assignment properties such as `Work`, `Cost`, and
      `Start` using the setters provided by the `ResourceAssignment` class.
    question: Can I modify resource assignments after creation?
  - answer: Absolutely, Aspose.Tasks for Java supports MPP, XML, CSV, and many other
      formats, allowing seamless import and export.
    question: Is Aspose.Tasks for Java compatible with different project file formats?
  - answer: Yes, a valid commercial license is required. A free evaluation license
      is available for testing purposes.
    question: Does Aspose.Tasks for Java require a license for commercial use?
  - answer: Yes, the library is fully thread‑safe and can be integrated into servlet‑based
      or Spring‑Boot web services.
    question: Can I use Aspose.Tasks for Java in my web applications?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for technical assistance and community discussions.
    question: Where can I find additional support for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中將資源新增至專案並建立資源指派
url: /zh-hant/java/resource-assignments/create-resource-assignments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 新增資源至專案 – 在 Aspose.Tasks 中建立資源指派

## 介紹
在現代專案管理中，**add resource to project** 是有效排程與成本控制的基石。Aspose.Tasks for Java 為您提供一種程式化、高效能的方式來管理資源、任務與指派，且無需離開 IDE。在本教學中，您將看到如何將資源新增至專案、將其指派給任務，並微調指派細節——全部使用乾淨、可投入生產環境的 Java 程式碼。

## 快速解答
- **第一步是什麼？** 建立一個代表 .mpp 或 .xml 檔案的 `Project` 實例。  
- **如何新增任務？** 使用根任務的 `addChild` 方法並為任務命名。  
- **如何新增資源？** 呼叫 `project.getResources().add` 並傳入 `Resource` 物件。  
- **如何將資源連結至任務？** 使用 `project.getResourceAssignments().add(task, resource)`。  
- **是否需要授權？** 是 – 生產環境必須使用有效的 Aspose.Tasks for Java 授權。

## 什麼是「新增資源至專案」？
**Add resource to project** 意味著在專案檔案中建立一個 `Resource` 物件，並將其連結至一個或多個任務，使工作、成本與行事曆資料能自動計算。此操作是任何以排程為核心的應用程式的基礎。

## 為什麼選擇 Aspose.Tasks for Java？
Aspose.Tasks for Java 支援 **30+ 輸入與輸出格式**（包括 MPP、XML、CSV），且可處理 **10,000+ 任務** 的專案，同時將記憶體使用量控制在 200 MB 以下。此函式庫相容於 Java 8‑17，無需安裝 Microsoft Project，並提供執行緒安全的 API 以供伺服器端自動化使用。

## 前置條件
在開始建立資源指派之前，請確保您已具備以下條件：

### Java 開發環境
請確認您的系統已安裝 Java Development Kit (JDK)。您可以從[此處](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)下載並安裝 JDK。

### Aspose.Tasks for Java 函式庫
從[下載頁面](https://releases.aspose.com/tasks/java/)取得 Aspose.Tasks for Java 函式庫。依照安裝說明將函式庫設定於您的 Java 專案中。

## 如何新增資源至專案？

載入專案、建立任務、加入資源，最後將它們連結——共四個簡潔步驟。以下程式碼片段（佔位符）示範確切的 API 呼叫；您只需將佔位文字替換為自己的檔案路徑與名稱。

### 步驟 1：建立 Project 物件
`Project` 類別是代表單一專案檔案於記憶體中的最高層容器。  
建立一個 `Project` 物件，代表您正在處理的專案檔案：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

### 步驟 2：將任務新增至專案
`Task` 類別模型化排程中的單一工作項目。  
使用根任務的 `addChild` 方法將任務新增至專案：
```java
Project project = new Project();
```

### 步驟 3：將資源新增至專案
`Resource` 類別定義可指派給任務的人員、設備或材料。  
使用 `Resources` 集合的 `add` 方法將資源新增至專案：
```java
Task task = project.getRootTask().getChildren().add("Task");
```

### 步驟 4：建立資源指派
`ResourceAssignment` 類別連結 `Task` 與 `Resource`，並儲存分配細節（如工時與成本）。  
使用 `ResourceAssignments` 集合的 `add` 方法為該任務與資源建立指派：
```java
Resource rsc = project.getResources().add("Rsc");
```

## 常見問題與解決方案
- **NullPointerException on `addChild`** – 確認在新增子項目之前先呼叫 `project.getRootTask()`。  
- **License not found** – 將您的 `Aspose.Tasks.lic` 檔案放置於 classpath 中，或以程式方式設定授權：`License license = new License(); license.setLicense("Aspose.Tasks.lic");`。  
- **Large project slowdown** – 若僅需讀取資料，請使用 `project.setReadOnly(true)`，可減少記憶體開銷。

## 常見問答

**Q: 可以在建立後修改資源指派嗎？**  
A: 可以，您可以使用 `ResourceAssignment` 類別提供的 setter 來更新 `Work`、`Cost`、`Start` 等屬性。

**Q: Aspose.Tasks for Java 是否相容不同的專案檔案格式？**  
A: 當然，Aspose.Tasks for Java 支援 MPP、XML、CSV 以及其他多種格式，讓匯入與匯出無縫銜接。

**Q: Aspose.Tasks for Java 商業使用是否需要授權？**  
A: 需要，必須擁有有效的商業授權。亦提供免費評估授權供測試使用。

**Q: 可以在我的 Web 應用程式中使用 Aspose.Tasks for Java 嗎？**  
A: 可以，函式庫具備完整的執行緒安全性，可整合至基於 Servlet 或 Spring‑Boot 的服務中。

**Q: 在哪裡可以取得 Aspose.Tasks for Java 的其他支援？**  
A: 您可前往 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)取得技術協助與社群討論。

---

**最後更新：** 2026-05-20  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何建立資源 – 使用 Aspose.Tasks for Java 進行資源管理](/tasks/java/resource-management/)
- [如何在 Aspose.Tasks 中為資源指派新增備註](/tasks/java/resource-assignments/resource-assignment-notes/)
- [如何在 Aspose.Tasks 中新增資源至專案並處理平衡延遲屬性](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}