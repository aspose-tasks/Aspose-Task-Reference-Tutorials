---
date: 2026-07-19
description: 了解如何使用 Aspose.Tasks for Java 將 aspose tasks 資源備註新增至資源分配。遵循此一步一步的指南，以提升專案溝通。
keywords:
- aspose tasks resource notes
- resource assignment notes
- aspose.tasks java
lastmod: 2026-07-19
linktitle: 如何在 Aspose.Tasks 中向資源分配加入備註
og_description: 了解如何使用 Aspose.Tasks for Java 將 aspose tasks 資源備註新增至資源分配。本教學將逐步說明從設定到取得備註的每個環節。
og_image_alt: 'Guide: Adding resource assignment notes with Aspose.Tasks for Java'
og_title: Aspose.Tasks 資源備註 – 向分配加入備註
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add aspose tasks resource notes to resource assignments
    using Aspose.Tasks for Java. Follow this step‑by‑step guide to improve project
    communication.
  headline: aspose tasks resource notes – Add Notes to Assignments
  type: TechArticle
- description: Learn how to add aspose tasks resource notes to resource assignments
    using Aspose.Tasks for Java. Follow this step‑by‑step guide to improve project
    communication.
  name: aspose tasks resource notes – Add Notes to Assignments
  steps:
  - name: Set Data Directory
    text: Set the path to your data directory where your project files are located.
  - name: Load Project File
    text: Load the project file into your Java application.
  - name: Get Task and Resource
    text: Retrieve the task and resource to which you want to add notes.
  - name: Create Resource Assignment
    text: Create a resource assignment for the task and resource.
  - name: Set Notes
    text: Set the notes for the resource assignment.
  - name: Display Notes
    text: Display the notes text and RTF format.
  - name: Process Completion
    text: Print a success message indicating the completion of the process.
  type: HowTo
- questions:
  - answer: Yes, simply call `assn.set(Asn.NOTES_TEXT, "Updated note")` again with
      the new content.
    question: Can I edit notes after they have been set?
  - answer: Absolutely. When you save the `Project` object, the notes become part
      of the assignment data inside the file.
    question: Are notes stored in the .mpp file?
  - answer: You must open the project with the correct password using the appropriate
      `Project` constructor overload before accessing assignments.
    question: Does this work with encrypted project files?
  - answer: Practically, notes can be several kilobytes long; extremely large notes
      may affect performance when loading the project.
    question: Is there a limit to the length of a note?
  - answer: Yes, iterate over `prj.getResourceAssignments()` and set `Asn.NOTES_TEXT`
      for each assignment as needed.
    question: Can I add notes to multiple assignments in a loop?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- resource notes
- java project management
- resource assignments
- aspose tasks java
title: Aspose.Tasks 資源備註 – 向分配加入備註
url: /zh-hant/java/resource-assignments/resource-assignment-notes/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中為資源指派新增備註

## 介紹
在本教學中，您將學會 **如何在 Aspose.Tasks for Java 中為資源指派新增備註**——這是一套業界領先的專案管理檔案處理函式庫。完成本指南後，您即可直接在任務與資源的關聯上附加純文字或富文字備註，讓您的專案資料更具可溝通性且符合稽核需求。

## 快速解答
- **「新增備註」會影響什麼？** 它會在資源指派上儲存純文字與 RTF 形式的備註。  
- **哪個類別保存備註資料？** `Asn` 類別（例如 `Asn.NOTES_TEXT`）。  
- **測試是否需要授權？** 不需要，Aspose 官方網站提供免費試用。  
- **可以取得 RTF 格式的備註嗎？** 可以，使用 `Asn.NOTES_RTF`。  
- **此功能是否相容所有 Java IDE？** 完全相容——IntelliJ IDEA、Eclipse、NetBeans 等皆可使用。  

## 什麼是為資源指派新增備註？
為資源指派新增備註是指在任務與資源之間的連結上附加說明文字——可以是純文字或富文字（RTF）。此功能讓專案經理能直接在指派上嵌入背景說明、特殊指示或變更紀錄，確保檢視排程的任何人都能即時了解每筆分配背後的「原因」。

## 為什麼要新增備註？
新增備註在專案檔內建立即時的溝通管道。它免除外部試算表或電子郵件討論的需求，提供內建的稽核追蹤，且因支援 RTF，您可使用粗體或斜體等樣式強調關鍵資訊——全部都在專案管理環境中完成。

## 前置條件
在開始之前，請確保您已具備以下項目：

1. **Java Development Kit (JDK)** – 版本 8 或以上，已在您的機器上正確設定。  
2. **Aspose.Tasks for Java** – 從[官方網站](https://releases.aspose.com/tasks/java/)下載最新 JAR。  
3. **IDE** – IntelliJ IDEA、Eclipse、NetBeans，或任何您偏好的 Java 相容編輯器。  

## 匯入套件
在您的 Java 專案中匯入必要的套件：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

## 如何為資源指派新增備註
本節將逐步說明將備註附加至資源指派的完整工作流程。從設定資料目錄、載入專案、取得相關任務與資源、建立指派、最後設定與顯示純文字與 RTF 備註，每一步皆以可自行替換為原始程式碼片段的佔位符示範。

### 步驟 1：設定資料目錄
設定您的資料目錄路徑，該目錄存放專案檔案。
```java
String dataDir = "Your Data Directory";
```

### 步驟 2：載入專案檔案
將專案檔案載入您的 Java 應用程式。
```java
Project prj = new Project(dataDir + "UpdateResourceAssignment.mpp");
```

### 步驟 3：取得任務與資源
取得您想要新增備註的任務與資源。
```java
Task task = prj.getRootTask().getChildren().getById(1);
Resource rsc = prj.getResources().getById(1);
```

### 步驟 4：建立資源指派
為該任務與資源建立資源指派。
```java
ResourceAssignment assn = prj.getResourceAssignments().add(task, rsc);
```

### 步驟 5：設定備註
為資源指派設定備註。
```java
assn.set(Asn.NOTES_TEXT, "Newly added assignment");
```

### 步驟 6：顯示備註
顯示備註的純文字與 RTF 內容。
```java
System.out.println("Notes text: " + assn.get(Asn.NOTES_TEXT));
System.out.println("Notes RTF: " + assn.get(Asn.NOTES_RTF));
```

### 步驟 7：流程完成
列印成功訊息，表示流程已完成。
```java
System.out.println("Process completed Successfully");
```

## Asn 類別是什麼？
`Asn` 類別定義了資源指派上各欄位的常數，例如備註、成本與工時。您可使用這些常數搭配 `ResourceAssignment` 物件的 `set` 與 `get` 方法，讀寫對應資料。例如，`Asn.NOTES_TEXT` 儲存純文字備註，而 `Asn.NOTES_RTF` 則保存富文字版本。

## 常見問題與解決方案
- **取得任務/資源時拋出 NullPointerException：** 請確認範例中的 ID（如 `1`）在您的 `.mpp` 檔案中確實存在。  
- **備註未在 UI 中顯示：** 請確保您在 Microsoft Project 或其他支援指派備註的檢視器中開啟「指派備註」窗格。  
- **RTF 輸出為空白：** 只有當備註包含富文字格式時 API 才會回傳 RTF，純文字會得到空的 RTF 字串。  

## 常見問與答
**Q: 設定完備註後可以再編輯嗎？**  
A: 可以，只需再次呼叫 `assn.set(Asn.NOTES_TEXT, "Updated note")` 並傳入新內容。

**Q: 備註會儲存在 .mpp 檔案中嗎？**  
A: 會的。當您儲存 `Project` 物件時，備註會成為檔案內指派資料的一部份。

**Q: 這能用於加密的專案檔嗎？**  
A: 必須使用正確的密碼，透過相應的 `Project` 建構子重載開啟專案後，才能存取指派。

**Q: 備註長度有限制嗎？**  
A: 實務上備註可達數千位元組；過大的備註可能會影響載入專案時的效能。

**Q: 可以在迴圈中為多筆指派新增備註嗎？**  
A: 可以，遍歷 `prj.getResourceAssignments()`，對每筆指派使用 `Asn.NOTES_TEXT` 進行設定即可。

## 結論
依照上述步驟，您現在已掌握 **如何在 Aspose.Tasks for Java 中為資源指派新增備註**。善用 Aspose.Tasks 的資源備註功能，可提升專案透明度、建立內建稽核追蹤，且能在排程檔內嵌入富文字評論，無需離開檔案。進一步探索 API 如批次更新、自訂欄位，以及與現有專案管理流程的整合。

---

**最後更新：** 2026-07-19  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時最新版本）  
**作者：** Aspose

## 相關教學

- [Add resource to project with Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)
- [How to Add Resource to Project and Handle Leveling Delay Properties in Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)
- [How to Stop Assignment and Resume Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}