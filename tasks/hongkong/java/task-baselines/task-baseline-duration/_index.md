---
title: Aspose.Tasks 中的任務基線持續時間管理
linktitle: Aspose.Tasks 中的任務基線持續時間管理
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 在 MS Project 中高效管理任務基準。本教學將引導您逐步完成流程。
weight: 12
url: /zh-hant/java/task-baselines/task-baseline-duration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的任務基線持續時間管理

## 介紹
在 MS Project 中管理任務基線對於專案規劃和追蹤至關重要。在本教程中，我們將探討如何使用 Aspose.Tasks for Java 有效管理任務基線持續時間。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1. Java 開發環境：確保您的系統上安裝了 Java 開發工具包 (JDK)。
2.  Aspose.Tasks 函式庫：下載並安裝 Aspose.Tasks for Java 函式庫[這裡](https://releases.aspose.com/tasks/java/).

## 導入包
首先，導入 Java 專案所需的套件：
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## 步驟1：建立專案實例
使用以下程式碼初始化一個新的專案實例：
```java
Project project = new Project();
```
## 第 2 步：建立任務基線
建立一個新任務並使用以下程式碼設定其基線：
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## 步驟 3：顯示任務基線訊息
檢索並顯示任務基線訊息，例如持續時間、開始日期、完成日期等：
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## 第 4 步：檢查中期基準和固定成本
檢查基線是否為臨時基線並檢索與其相關的任何固定成本：
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## 第 5 步：列印時間分段數據
列印與任務基線關聯的時間分段資料：
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
透過執行下列步驟，您可以使用 Aspose.Tasks for Java 有效管理 MS Project 中的任務基準持續時間。

## 結論
管理任務基準對於專案管理至關重要，它使您能夠追蹤與計劃進度的偏差。借助 Aspose.Tasks for Java，此流程變得精簡且高效，從而實現更好的專案控制和交付。
## 常見問題解答
### MS Project 中的任務基線是什麼？
MS Project 中的任務基準是任務的初始計畫時間表的快照，包括其開始日期、完成日期和持續時間。
### 為什麼管理任務基線很重要？
管理任務基準有助於將計畫進度與專案的實際進度進行比較，從而促進更好的追蹤和決策。
### 任務基線設定後我可以修改嗎？
是的，您可以在 MS Project 中修改任務基準以反映專案計畫中的變更。但是，必須記錄與原始基線的任何偏差。
### Aspose.Tasks 是否支援其他專案管理功能？
是的，Aspose.Tasks 為專案管理提供了廣泛的功能，包括任務排程、資源分配和甘特圖產生。
### 在哪裡可以找到對 Aspose.Tasks 的支援？
您可以在以下位置找到對 Aspose.Tasks 的支持[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)，您可以在其中提出問題並與其他用戶互動。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
