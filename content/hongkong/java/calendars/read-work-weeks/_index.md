---
title: 使用 Aspose.Tasks 從 MS 專案行事曆中讀取工作週
linktitle: 使用 Aspose.Tasks 從行事曆中讀取工作週
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 從 MS Project 行事曆中讀取工作週。在此綜合教程中取得逐步說明。
type: docs
weight: 15
url: /zh-hant/java/calendars/read-work-weeks/
---
## 介紹
在本教程中，我們將探討如何使用 Aspose.Tasks for Java 從 Microsoft Project 日曆中讀取工作週資訊。 Aspose.Tasks 是一個功能強大的 Java 程式庫，可讓您以程式設計方式操作和管理 Microsoft Project 文件。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1. 您的系統上安裝了 Java 開發工具包 (JDK)。
2. 下載並安裝了 Java 函式庫的 Aspose.Tasks。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/java/).
## 導入包
首先，讓我們匯入必要的套件來開始使用我們的程式碼：
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## 第 1 步：設定您的資料目錄
設定 MS Project 檔案所在的目錄路徑：
```java
String dataDir = "Your Data Directory";
```
## 步驟 2：建立專案實例並存取日曆
建立 Project 類別的新實例並存取日曆和工作週集合：
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## 第 3 步：迭代工作週
迭代工作週的集合並顯示其資訊：
```java
for (WorkWeek workWeek : collection) {
    //顯示工作週名稱、開始日期和結束日期
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    //訪問工作日和工作時間
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        //如果需要進一步處理工作時間
    }
}
```
## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 從 Microsoft Project 日曆中讀取工作週資訊。這個功能強大的庫可以無縫操作專案文件，使開發人員能夠有效地自動執行各種任務。
## 常見問題解答
### 我可以使用 Aspose.Tasks for Java 修改工作週資訊嗎？
是的，Aspose.Tasks 提供了 API 來修改、新增或刪除工作週及其相關資訊。
### Aspose.Tasks 是否與不同版本的 Microsoft Project 檔案相容？
是的，Aspose.Tasks 支援各種版本的 Microsoft Project 文件，包括 MPP 和 XML 格式。
### 我可以將 Aspose.Tasks 與其他 Java 框架整合嗎？
當然，Aspose.Tasks 可以與其他 Java 框架和函式庫無縫集成，以增強功能。
### Aspose.Tasks 有試用版嗎？
是的，您可以從以下位置下載 Aspose.Tasks 的免費試用版：[這裡](https://releases.aspose.com/).
### 在哪裡可以找到對 Aspose.Tasks 的支援？
您可以在 Aspose.Tasks 論壇上找到支援和協助[這裡](https://forum.aspose.com/c/tasks/15).