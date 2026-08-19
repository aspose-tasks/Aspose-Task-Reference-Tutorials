---
date: 2026-02-26
description: 學習如何使用 Aspose.Tasks for Java 分割工作——這本權威指南將教您如何分割工作、設定專案行事曆以及建立資源指派。
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中拆分任務
url: /zh-hant/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中拆分任務

## Introduction
如果您正在尋找 **如何拆分任務** 在基於 Java 的專案中，您來對地方了。Aspose.Tasks for Java 為您提供一種乾淨、程式化的方式，將長時間執行的任務拆分為較小、易於管理的部分，這有助於資源平衡、精確報告以及更緊湊的專案時間表。在本教學中，我們將逐步說明整個過程——從設定專案日曆、建立資源指派，到最終將任務拆分為多個段落。

## Quick Answers
- **什麼是任務拆分？** 將單一任務分割成多個較小的時間間隔，同時保留其總持續時間。  
- **為什麼在 Java 中拆分任務？** 它可實現精確的資源分配與更好的進度追蹤。  
- **哪個函式庫可以協助？** Aspose.Tasks for Java 提供內建的拆分與時間分段方法。  
- **我需要授權嗎？** 免費試用可用於開發；正式環境需購買授權。  
- **支援哪個 Java 版本？** 此函式庫支援 Java 8 及更新版本。

## Prerequisites
在深入教學之前，請確保您已具備以下前置條件：
- 已在機器上安裝 Java Development Kit (JDK)。  
- 已下載 Aspose.Tasks for Java 函式庫並加入專案。您可從 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) 下載。

## Import Packages
開始將必要的套件匯入您的 Java 專案：

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Step 1: Create a New Project
使用 Aspose.Tasks 函式庫建立新專案：

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Step 2: Set Project Calendar
設定 **專案日曆** 定義工作日、假期以及排程的整體時間線。此步驟對於精確的時間分段計算至關重要。

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Step 3: Add a Root Task
每個專案都需要一個根容器。新增根任務可為後續所有任務提供掛載點。

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Step 4: Add a New Task to Split
建立您打算拆分的任務。此處以三天的持續時間作為範例。

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Step 5: Create a Resource Assignment
**資源指派** 將資源（或佔位符）連結至任務。生成時間分段資料前必須先完成此步驟。

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Step 6: Generate Timephased Data
時間分段資料表示工作在任務持續期間的分配情形。產生此資料可為任務拆分做準備。

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Step 7: Split the Task
現在我們 **將任務拆分為多個部分**。在此範例中，我們將三天任務拆分為三個一天的段落。

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Why Split Tasks?
拆分任務可讓您對以下方面有更細緻的控制：
- **資源平衡：** 為每個段落指派不同的資源。  
- **進度追蹤：** 以每個段落為單位更新狀態。  
- **報告：** 產生更詳細的甘特圖與報表。

## Common Issues and Solutions
- **缺少日曆資料：** 確保在拆分前呼叫 `timephasedDataFromTaskDuration`。  
- **零時長段落：** 確認每個拆分區間的持續時間非零，否則函式庫會忽略。  
- **授權例外：** 未使用有效授權執行可能會在匯出檔案上加上浮水印。

## Frequently Asked Questions
### 我可以使用不同持續時間拆分任務嗎？
可以，您可以調整每個部分的持續時間，以符合專案需求。

### Aspose.Tasks for Java 是否相容所有 Java 版本？
Aspose.Tasks for Java 專為 Java 8 及更新版本設計，確保廣泛相容性。

### 我可以免費使用 Aspose.Tasks for Java 嗎？
Aspose.Tasks for Java 提供免費試用，讓您在購買前先體驗其功能。

### 如何取得 Aspose.Tasks for Java 的支援？
前往 [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15) 獲取協助並與社群交流。

### 我需要臨時授權才能使用 Aspose.Tasks for Java 嗎？
您可從 [this link](https://purchase.aspose.com/temporary-license/) 取得臨時授權，以供測試與評估使用。

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}