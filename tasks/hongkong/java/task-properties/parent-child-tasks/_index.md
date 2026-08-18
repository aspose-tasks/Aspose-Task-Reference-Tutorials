---
date: 2026-02-23
description: 學習如何使用 Aspose.Tasks for Java 設定專案開始日期、設定工作持續時間，並將專案另存為 MPP。有效管理父子任務。
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 設定專案開始日期並在 Aspose.Tasks 中管理父子任務
url: /zh-hant/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 設定專案開始日期並管理 Aspose.Tasks 中的父子任務

## 介紹
有效的任務組織是成功專案管理的基礎，而**正確設定專案開始日期**則是建立良好排程的第一步。在本教學中，您將學會如何**設定專案開始日期**、配置任務工期，並使用 Aspose.Tasks for Java 管理父子關係。完成後，您即可**將專案儲存為 MPP**、更新任務完成百分比，並自訂任務屬性以符合任何實務情境。

## 快速解答
- **如何設定專案開始日期？** 在初始化 `Project` 物件後，使用 `proj.set(Prj.START_DATE, startDate);`。  
- **可以在父任務下加入子任務嗎？** 可以 – 呼叫 `parentTask.getChildren().add("Child Task")`。  
- **Aspose.Tasks 以何種格式儲存檔案？** 使用 `SaveFileFormat.Mpp` **將專案儲存為 MPP**。  
- **如何更新任務完成度？** 在任務物件上設定 `Tsk.PERCENT_COMPLETE`。  
- **哪裡可以取得臨時授權？** 前往常見問題頁面中提供的臨時授權連結。

## 前置條件
在開始教學之前，請確保您已具備以下條件：
- 基本的 Java 程式設計概念。  
- 已安裝 Aspose.Tasks for Java 套件。您可以在此處下載 [here](https://releases.aspose.com/tasks/java/)。  
- 系統上已設定好 Java 整合開發環境 (IDE)。

## 匯入套件
首先，將必要的套件匯入您的 Java 專案。這些套件可協助您順利使用 Aspose.Tasks for Java 的功能。
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

## 步驟 1：設定專案開始日期
先設定專案的開始日期以及其他相關參數。
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## 步驟 2：新增父任務（Task 1）
建立名稱為「Task 1」的父任務，並設定其屬性，包括**設定任務工期**。
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## 步驟 3：新增父任務（Task 2）並加入子任務
接著，新增另一個名稱為「Task 2」的父任務，並加入子任務（Task 3 與 Task 4）。
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## 步驟 4：設定子任務
為 Task 3 與 Task 4 指定開始日期、工期與限制條件。
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## 步驟 5：更新任務完成百分比
調整 Task 3 與 Task 4 的完成百分比——這就是**更新任務完成度**的方式。
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## 步驟 6：儲存專案
最後，使用**將專案儲存為 MPP**，將變更寫入檔案。
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

本分步指南示範了如何使用 Aspose.Tasks for Java 有效管理父子任務。您可以依需求調整各種設定，以符合專案的實際需求。

## 為何要自訂任務屬性？
自訂任務屬性（如開始日期、工期、限制條件與完成百分比）可讓您對排程行為擁有精細的控制。無論是要配合資源可用性，或是強制執行業務規則，Aspose.Tasks 都能讓您以程式方式**自訂任務屬性**。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **開始日期未套用** | 確認在建立 `Project` 物件之**後**、加入任務之前，已呼叫 `proj.set(Prj.START_DATE, …)`。 |
| **子任務繼承了錯誤的限制** | 如步驟 4 所示，為每個子任務明確設定 `ConstraintType` 與 `ConstraintDate`。 |
| **儲存的檔案無法在 MS Project 開啟** | 確認使用最新版本的 Aspose.Tasks，並以 `SaveFileFormat.Mpp` 進行儲存。 |
| **完成百分比未在 UI 中顯示** | 在設定 `Tsk.PERCENT_COMPLETE` 後，若需要重新計算日期，請呼叫 `proj.calculateTaskSchedule()`。 |

## 常見問答
### Aspose.Tasks for Java 是否相容於不同的專案檔案格式？
是，Aspose.Tasks for Java 支援多種專案檔案格式，包括 MPP 與 XML。

### 我可以自訂超出本教學範圍的任務屬性嗎？
當然可以！Aspose.Tasks for Java 提供廣泛的任務屬性自訂選項。

### 是否有 Aspose.Tasks 社群論壇可供求助？
有，您可以前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 取得社群支援。

### 如何取得 Aspose.Tasks for Java 的臨時授權？
您可以在此處取得臨時授權 [here](https://purchase.aspose.com/temporary-license/)。  

### 哪裡可以找到 Aspose.Tasks for Java 的完整文件？
文件可於此取得 [here](https://reference.aspose.com/tasks/java/)。  

**其他問答**

**問：如何以程式方式取得臨時授權？**  
答：載入臨時授權檔案，例如 `License license = new License(); license.setLicense("Aspose.Tasks.lic");`。

**問：可以變更預設的任務工期單位嗎？**  
答：可以 – 在 `proj.getDuration(value, TimeUnitType.YourChoice)` 中修改 `TimeUnitType` 參數。

**問：使用 `SaveFileFormat.Mpp` 需要哪個版本的 Aspose.Tasks？**  
答：所有近期版本（2022‑2026）皆支援儲存為 MPP；請參考發行說明以確認是否有相容性變更。

---

**最後更新日期：** 2026-02-23  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}