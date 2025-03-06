---
title: 在 Aspose.Tasks 中將任務資料更新為 MPP 格式
linktitle: 在 Aspose.Tasks 中將任務資料更新為 MPP 格式
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 將任務資料更新為 MPP 格式。遵循我們的高效專案管理逐步指南。
weight: 35
url: /zh-hant/java/task-properties/update-task-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中將任務資料更新為 MPP 格式

## 介紹
歡迎閱讀我們有關使用 Aspose.Tasks for Java 將任務資料更新為 MPP 格式的逐步指南。在本教程中，我們將引導您完成整個過程，確保您清楚掌握每個步驟。 Aspose.Tasks for Java 提供了一個用於處理 Microsoft Project 檔案的強大解決方案，在本指南結束時，您將能夠有效率地更新 MPP 格式的任務資料。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
-  Aspose.Tasks for Java：確保您已安裝 Aspose.Tasks 函式庫。您可以從[發布頁面](https://releases.aspose.com/tasks/java/).
- Java 開發工具包 (JDK)：確保您的系統上安裝了 Java。
- 整合開發環境 (IDE)：使用您選擇的 IDE 進行 Java 開發。
## 導入包
首先將必要的套件匯入到您的 Java 專案中。以下程式碼片段示範如何匯入套件：
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
## 1. 建立並配置初始任務
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//……（繼續其餘代碼）
```
## 2. 設定開始日期和持續時間
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//……（繼續其餘代碼）
```
## 3. 建立摘要任務
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//……（繼續其餘代碼）
```
## 4.設定截止日期和任務說明
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//……（繼續其餘代碼）
```
## 5. 配置任務約束
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//……（繼續其餘代碼）
```
## 6. 建立附加任務
```java
//建立 10 個新任務
for (int i = 0; i < 10; i++) {
    //……（繼續其餘代碼）
}
//……（繼續其餘代碼）
```
## 7. 保存項目
```java
//保存項目
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
透過執行這些步驟，您已使用 Aspose.Tasks for Java 成功將任務資料更新為 MPP 格式。
## 結論
恭喜！您已經完成了使用 Aspose.Tasks for Java 更新 MPP 格式的任務資料的綜合指南。這個強大的程式庫簡化了專案管理任務，使其成為 Java 開發人員的寶貴工具。
## 常見問題解答
### Q：在哪裡可以找到 Aspose.Tasks for Java 文件？
答：文檔已提供[這裡](https://reference.aspose.com/tasks/java/).
### Q：如何下載 Aspose.Tasks for Java？
答：您可以從以下網址下載[發布頁面](https://releases.aspose.com/tasks/java/).
### Q：有免費試用嗎？
答：是的，您可以免費試用[這裡](https://releases.aspose.com/).
### Q：在哪裡可以獲得 Aspose.Tasks for Java 的支援？
答：造訪支援論壇[這裡](https://forum.aspose.com/c/tasks/15).
### Q：你們是否提供用於測試目的的臨時許可證？
答：是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
