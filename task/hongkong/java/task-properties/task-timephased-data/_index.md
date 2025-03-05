---
title: Aspose.Tasks 中的任務時間分段數據
linktitle: Aspose.Tasks 中的任務時間分段數據
second_title: Aspose.Tasks Java API
description: 探索 Aspose.Tasks for Java 和主任務時間分段資料管理。下載庫，享受免費試用，並簡化您的專案追蹤。
type: docs
weight: 34
url: /zh-hant/java/task-properties/task-timephased-data/
---
## 介紹
在專案管理領域，精確追蹤任務時間分段資料對於高效的專案執行至關重要。 Aspose.Tasks for Java 成為簡化此過程的強大工具，提供強大的功能和靈活性。本教學將引導您利用 Aspose.Tasks for Java 有效管理任務時間分段資料。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- Java 開發環境：確保您的系統上安裝了 Java。
-  Aspose.Tasks for Java Library：下載 Aspose.Tasks 函式庫並將其包含在您的專案中。你可以找到圖書館[這裡](https://releases.aspose.com/tasks/java/).
- 文檔目錄：為您的專案文檔設定目錄。
## 導入包
在您的 Java 專案中，匯入 Aspose.Tasks 所需的套件：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## 第 1 步：設定專案開始日期
```java
Project project = new Project(dataDir + "project.xml");
//包導入的附加程式碼
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
說明：初始化一個日曆對象，設定開始日期，並將其應用到專案中。
## 第 2 步：定義任務和資源
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
說明：建立任務和資源，設定標準加班費率。
## 第 3 步：設定任務持續時間
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
說明：定義任務的持續時間（例如，6 天）。
## 步驟 4：將資源分配給任務
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
說明：將資源分配給任務。
## 步驟 5：設定資源分配
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
說明： 設定資源分配的停止、復原、工作輪廓等參數。
## 第 6 步：設定基線
```java
project.setBaseline(BaselineType.Baseline);
```
說明： 為專案建立基線。
## 步驟7：更新任務完成狀況
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
說明：表示任務的完成百分比。
## 第 8 步：檢索時間分段數據
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
說明：檢索已指派的剩餘工時的時間分段資料。
## 第 9 步：顯示時間分段數據
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
//用於顯示其他值的附加程式碼
```
說明： 輸出並顯示時間分段資料。
## 結論
有效管理任務時間分段資料對於專案成功至關重要。 Aspose.Tasks for Java 簡化了這個過程，提供了一套全面的功能。透過遵循本教學課程，您可以將 Aspose.Tasks 無縫整合到您的 Java 專案中，確保精確控制專案時間表和資源分配。
## 經常問的問題
### Q：我可以在任何 Java 專案中使用 Aspose.Tasks for Java 嗎？
答：是的，Aspose.Tasks for Java 與任何基於 Java 的專案相容。
### Q：在哪裡可以找到 Aspose.Tasks for Java 的其他支援？
答：訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以尋求支持和討論。
### Q：Aspose.Tasks for Java 是否有免費試用版？
答：是的，您可以嘗試免費試用[這裡](https://releases.aspose.com/).
### Q：如何取得 Aspose.Tasks for Java 的臨時授權？
答：您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### Q：哪裡可以購買 Aspose.Tasks for Java？
答：您可以購買 Aspose.Tasks for Java[這裡](https://purchase.aspose.com/buy).