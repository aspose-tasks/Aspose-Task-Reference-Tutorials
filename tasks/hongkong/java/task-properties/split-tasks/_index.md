---
title: 在 Aspose.Tasks 中分割任務
linktitle: 在 Aspose.Tasks 中分割任務
second_title: Aspose.Tasks Java API
description: 使用 Aspose.Tasks 掌握 Java 中的任務管理！了解如何有效地拆分任務以優化專案時間表。現在下載！
type: docs
weight: 29
url: /zh-hant/java/task-properties/split-tasks/
---
## 介紹
您是否正在為 Java 專案中的任務管理而苦苦掙扎？ Aspose.Tasks for Java 提供了一個強大的解決方案，可以有效地分割任務，增強專案管理能力。在本教程中，我們將引導您完成使用 Aspose.Tasks for Java 分割任務的過程，幫助您最佳化專案時間表和資源分配。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- 您的電腦上安裝了 Java 開發工具包 (JDK)。
-  Aspose.Tasks for Java 程式庫下載並新增到您的專案中。您可以從[Aspose.Tasks for Java 文檔](https://reference.aspose.com/tasks/java/).
## 導入包
首先將必要的套件匯入到您的 Java 專案中：
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
## 第 1 步：建立一個新項目
首先使用 Aspose.Tasks 庫建立一個新專案：
```java
//建立一個新項目
Project splitTaskProject = new Project();
```
## 第 2 步：設定專案日曆
設定項目的日曆設定以建立時間表：
```java
//取得標準日曆
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
//設定項目的日曆設置
java.util.Calendar cal = java.util.Calendar.getInstance();
//……（繼續舉例）
```
## 步驟 3：新增根任務
將根任務加入您的專案：
```java
//根任務
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## 第 4 步：新增任務到拆分
將新任務新增至要拆分的項目：
```java
//新增任務
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## 步驟 5：建立資源分配
為任務建立新的資源分配：
```java
//建立新的資源分配
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## 第 6 步：產生時間分段數據
產生資源分配時間分段資料：
```java
//產生資源分配時間分段數據
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## 第 7 步：拆分任務
將任務分成多個部分：
```java
//將任務分成 3 部分
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
//……（繼續舉例）
```
## 結論
恭喜！您已經成功學習如何使用 Aspose.Tasks for Java 來拆分任務。這個強大的函式庫簡化了 Java 專案中的任務管理，為優化專案時程和資源分配提供了有效的解決方案。
## 經常問的問題
### 我可以將任務拆分為不同的持續時間嗎？
是的，您可以根據專案要求調整任務的持續時間。
### Aspose.Tasks for Java 是否與所有 Java 版本相容？
Aspose.Tasks for Java 旨在與各種 Java 版本無縫協作，確保相容性。
### 我可以免費使用 Aspose.Tasks for Java 嗎？
Aspose.Tasks for Java 提供免費試用版，讓您在購買之前探索其功能。
### 我如何獲得 Aspose.Tasks for Java 的支援？
參觀[Aspose.Tasks for Java 支援論壇](https://forum.aspose.com/c/tasks/15)獲得協助並與社區建立聯繫。
### 我需要 Aspose.Tasks for Java 的臨時授權嗎？
您可以從以下地址取得臨時許可證[這個連結](https://purchase.aspose.com/temporary-license/)用於測試和評估目的。