---
title: 使用 Aspose.Tasks 從日曆取得工作時間
linktitle: 使用 Aspose.Tasks 從日曆取得工作時間
second_title: Aspose.Tasks Java API
description: 使用 Aspose.Tasks for Java 輕鬆從 MS Project 行事曆中擷取工作時間。簡化專案管理任務。
type: docs
weight: 13
url: /zh-hant/java/calendars/working-hours/
---
## 介紹
管理專案日曆和提取工作時間對於有效的專案管理至關重要。 Aspose.Tasks for Java 提供了強大的功能，可以輕鬆地從 MS Project 日曆中檢索工作時間。在本教程中，我們將逐步指導您完成流程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. 您的系統上安裝了 Java 開發工具包 (JDK)。
2.  Aspose.Tasks for Java 程式庫下載並新增到您的專案中。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/java/).
3. 對 Java 程式語言有基本的了解。
## 導入包
首先，導入使用 Aspose.Tasks for Java 所需的套件：
```java
import com.aspose.tasks.*;
```
## 第 1 步：載入專案文件
首先載入您的 MS Project 檔案：
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## 第 2 步：檢索任務和日曆信息
從專案中提取任務和日曆詳細資訊：
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## 第 3 步：定義開始和結束日期
設定任務的開始和結束日期：
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## 第 4 步：迭代日期
迭代任務持續時間內的日期：
```java
java.util.Calendar tempDate = calStartDate;
```
## 第 5 步：計算持續時間
計算持續時間（以分鐘、小時和天為單位）：
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## 結論
在本教學中，我們介紹如何使用 Aspose.Tasks for Java 從 MS Project 行事曆中擷取工作時間。透過執行這些步驟，您可以有效地管理專案進度並輕鬆計算任務工期。
## 常見問題解答
### Q：Aspose.Tasks for Java 可以處理複雜的專案結構嗎？
答：是的，Aspose.Tasks for Java 為處理複雜的專案結構（包括任務、資源和行事曆）提供了全面的支援。
### Q：Aspose.Tasks for Java 是否與不同版本的 MS Project 相容？
答：當然，Aspose.Tasks for Java 支援各種版本的 MS Project，確保不同環境之間的相容性。
### Q：我可以在專案日曆中自訂工作時間和假期嗎？
答：是的，您可以使用 Aspose.Tasks for Java API 根據您的專案要求輕鬆自訂工作時間和假期。
### Q：Aspose.Tasks for Java 是否提供支援和文件？
答：是的，Aspose.Tasks for Java 提供了廣泛的文件和專門的支援論壇，以幫助開發人員有效地利用其功能。
### Q：Aspose.Tasks for Java 有試用版嗎？
答：是的，您可以存取 Aspose.Tasks for Java 的免費試用版：[這裡](https://releases.aspose.com/).