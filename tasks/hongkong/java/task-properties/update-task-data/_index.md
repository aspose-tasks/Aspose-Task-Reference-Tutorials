---
date: 2026-03-03
description: 學習如何使用 Aspose.Tasks Java 將任務資料更新為 MPP 格式。請遵循我們的逐步指南，以提升專案管理效率。
linktitle: Update Task Data to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – 更新任務資料至 MPP 格式
url: /zh-hant/java/task-properties/update-task-data/
weight: 35
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將任務資料更新為 MPP 格式於 Aspose.Tasks

## Introduction
歡迎閱讀我們的逐步指南，內容是 **使用 Aspose.Tasks for Java 將任務資料更新為 MPP 格式**。在本教學中，您將學習如何以程式方式操作專案檔案，使用 *aspose tasks java*，從建立彙總任務到將 XML 專案轉換為 MPP 檔案。完成後，您將能有效管理專案任務，並將此解決方案整合至您的 Java 應用程式中。

## Quick Answers
- **本教學涵蓋什麼內容？** 使用 Aspose.Tasks for Java 更新任務資料並將專案儲存為 MPP。  
- **需要授權嗎？** 生產環境需使用臨時或正式授權；亦提供免費試用。  
- **哪種 IDE 最適合？** 任何 Java IDE（IntelliJ IDEA、Eclipse、VS Code）皆可。  
- **可以將 XML 轉換為 MPP 嗎？** 可以——範例會載入 XML 專案並儲存為 MPP。  
- **會建立多少個任務？** 範例會建立一個主要任務、一個彙總任務，以及十個額外任務。

## What is Aspose.Tasks for Java?
Aspose.Tasks for Java 是一套功能強大的 API，讓開發人員在未安裝 Microsoft Project 的情況下，讀取、寫入與修改 Microsoft Project 檔案（MPP、XML 等）。它支援完整的專案層級操作，包括任務建立、限制條件處理與檔案格式轉換。

## Why use Aspose.Tasks Java for project management?
- **Full control** over task properties such as start date, duration, and constraints.  
- **Seamless conversion** between XML and MPP, enabling integration with existing project data pipelines.  
- **No COM interop** – pure Java, ideal for cross‑platform environments.  
- **High performance** for large project files, making it suitable for enterprise‑scale solutions.

## Prerequisites
在開始教學之前，請確保已具備以下前置條件：
- Aspose.Tasks for Java：確保已安裝 Aspose.Tasks 程式庫。您可從 [release page](https://releases.aspose.com/tasks/java/) 下載。  
- Java Development Kit (JDK)：確保系統已安裝 Java。  
- Integrated Development Environment (IDE)：使用您偏好的 Java 開發 IDE。

## Import Packages
先在 Java 專案中匯入必要的套件。以下程式碼示範如何匯入套件：

```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```

## How to Create a Summary Task
彙總任務可將相關子任務分組，提供工作包的高階視圖。以下程式碼建立一個彙總任務，並將第一個任務設為其子任務。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Continue with the rest of the code)
```

## How to Set Start Date for a Task
設定開始日期對於排程的準確性至關重要。範例使用 `Calendar` 例項定義專案開始時間，並指派給任務。

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Continue with the rest of the code)
```

## How to Convert XML to MPP
此 API 能讀取 XML 專案檔並直接儲存為 MPP 檔，方便從舊有格式遷移。

```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Continue with the rest of the code)
```

## How to Set Deadline and Add Task Notes
截止日期可協助任務保持在預定軌道，備註則為團隊成員提供背景資訊。

```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Continue with the rest of the code)
```

## How to Configure Task Constraints and Update Task Duration
如 *Finish No Later Than* 等限制條件會指導排程器。您亦可變更持續時間格式，以顯示預估天數。

```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Continue with the rest of the code)
```

## How to Create Additional Tasks (Managing Project Tasks)
以下迴圈示範如何以程式方式產生多筆任務，這在匯入大量資料時相當常見。

```java
// Create 10 new tasks
for (int i = 0; i < 10; i++) {
    //... (Continue with the rest of the code)
}
//... (Continue with the rest of the code)
```

## How to Save the Project (Export to MPP)
最後，將變更寫入檔案，儲存為 MPP 格式。

```java
// Save the Project
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```

透過上述步驟，您已成功 **使用 aspose tasks java 將任務資料更新為 MPP 格式**。現在您已具備管理專案任務、建立彙總任務、設定開始日期以及將 XML 專案轉換為 MPP 的堅實基礎。

## Conclusion
恭喜您！您已完成使用 Aspose.Tasks for Java 更新任務資料為 MPP 格式的完整指南。此強大函式庫簡化了專案管理工作，對需要以程式方式 **管理專案任務** 的 Java 開發者而言，是一項寶貴工具。

## Frequently Asked Questions

### Q: Where can I find the Aspose.Tasks for Java documentation?
A: The documentation is available [here](https://reference.aspose.com/tasks/java/).

### Q: How can I download Aspose.Tasks for Java?
A: You can download it from the [release page](https://releases.aspose.com/tasks/java/).

### Q: Is there a free trial available?
A: Yes, you can access the free trial [here](https://releases.aspose.com/).

### Q: Where can I get support for Aspose.Tasks for Java?
A: Visit the support forum [here](https://forum.aspose.com/c/tasks/15).

### Q: Do you offer temporary licenses for testing purposes?
A: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-03-03  
**測試於：** Aspose.Tasks for Java 24.11 (latest)  
**作者：** Aspose