---
title: 在 Aspose.Tasks 中管理父任務和子任務
linktitle: 在 Aspose.Tasks 中管理父任務和子任務
second_title: Aspose.Tasks Java API
description: 使用 Aspose.Tasks for Java 提高專案管理效率。學習逐步管理父級和子級任務。現在就開始吧！
weight: 24
url: /zh-hant/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中管理父任務和子任務

## 介紹
在專案管理領域，有效的任務組織至關重要。 Aspose.Tasks for Java 提供了一個強大的解決方案來有效管理父任務和子任務。在本教程中，我們將指導您完成使用 Aspose.Tasks for Java 來簡化專案任務的過程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- 對 Java 程式設計有基本的了解。
- 安裝了 Java 函式庫的 Aspose.Tasks。你可以下載它[這裡](https://releases.aspose.com/tasks/java/).
- 在您的系統上設定 Java 整合開發環境 (IDE)。
## 導入包
首先，將必要的套件匯入到您的 Java 專案中。這些套件有助於與 Aspose.Tasks for Java 功能無縫整合。
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## 第 1 步：設定專案開始日期
首先設定項目的開始日期和其他相關參數。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
//可以在此處新增用於套件導入的附加程式碼
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## 步驟 2：新增父任務（任務 1）
建立名為「任務 1」的父任務並配置其屬性。
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## 步驟 3：新增父任務（任務 2）和子任務
現在，新增另一個名為「任務 2」的父任務並包含子任務（任務 3 和任務 4）。
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
//將子任務加入任務 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
//可以在此處新增任務 3 和任務 4 的其他配置
```
## 步驟 4：配置子任務
指定任務 3 和任務 4 的開始日期、持續時間和限制。
```java
//配置任務 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
//配置任務 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## 步驟 5：更新任務完成百分比
調整任務 3 和任務 4 的完成百分比。
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## 第 6 步：儲存項目
最後，儲存應用了變更的項目。
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
本逐步指南示範如何使用 Aspose.Tasks for Java 有效管理父任務和子任務。嘗試不同的配置以滿足您的專案要求。
## 結論
總之，Aspose.Tasks for Java 使開發人員能夠有效率地處理專案任務，確保無縫組織和追蹤。實施概述的步驟來增強您的專案管理能力。
## 常見問題解答
### Aspose.Tasks for Java 是否與不同的專案檔案格式相容？
是的，Aspose.Tasks for Java 支援各種專案文件格式，包括 MPP 和 XML。
### 我可以自訂超出本教學涵蓋範圍的任務屬性嗎？
絕對地！ Aspose.Tasks for Java 為任務屬性提供了廣泛的自訂選項。
### 是否有 Aspose.Tasks 社群論壇可供我尋求支援？
是的，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以獲得社區支持。
### 如何取得 Aspose.Tasks for Java 的臨時授權？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 在哪裡可以找到 Aspose.Tasks for Java 的綜合文件？
文件可用[這裡](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
