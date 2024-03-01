---
title: 使用 Aspose.Tasks 定義行事曆中的工作日
linktitle: 使用 Aspose.Tasks 定義行事曆中的工作日
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 在 MS Project Calendar 中定義工作日。輕鬆自訂工作日和時間安排。
type: docs
weight: 12
url: /zh-hant/java/calendars/define-weekdays/
---
## 介紹
在本教程中，我們將逐步介紹使用 Aspose.Tasks for Java 在 MS 專案日曆中定義工作日的過程。 Aspose.Tasks 是一個功能強大的 Java 程式庫，使開發人員能夠以程式設計方式操作 Microsoft Project 檔案。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1.  Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。您可以從[甲骨文網站](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)如果你還沒有。
2.  Aspose.Tasks for Java 函式庫：從下列位置下載並安裝 Aspose.Tasks for Java 函式庫：[下載頁面](https://releases.aspose.com/tasks/java/)。請按照文件中提供的安裝說明進行操作。

## 導入包
首先，匯入在 Java 專案中使用 Aspose.Tasks 所需的必要套件：
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## 步驟1：建立專案實例
實例化一個 Project 對象，它代表您將使用的 MS Project 檔案：
```java
//文檔目錄的路徑。
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## 第 2 步：定義日曆
建立一個新的日曆實例並將其新增至專案：
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## 第 3 步：新增工作日
透過新增週一到週四的預設時間來定義工作日：
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## 第 4 步：設定自訂工作日
將週六和週日定義為工作日：
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## 第 5 步：設定短工作日
將星期五設定為短工作日並具有自訂工作時間：
```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```
## 第 6 步：儲存項目
將修改後的項目儲存到 XML 檔案：
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 結論
恭喜！您已使用 Aspose.Tasks for Java 在 MS Project Calendar 中成功定義了工作日。現在您可以將此功能整合到 Java 應用程式中，以程式設計方式操作 MS Project 檔案。
## 常見問題解答
### Q1：我可以使用 Aspose.Tasks for Java 定義自訂非工作日嗎？
答：是的，您可以透過設定自訂非工作日`DayWorking`財產給`false`各個工作日。
### Q2: 如何在行事曆中新增假期？
答：您可以透過建立實例來新增假期`CalendarExceptions`並指定非工作日期。
### Q3：Aspose.Tasks 是否相容於不同版本的 MS Project 檔案？
答：是的，Aspose.Tasks 支援各種版本的 MS Project 文件，包括 MPP、MPT 和 XML 格式。
### 問題 4：我可以修改 MS Project 檔案中的現有日曆嗎？
答：是的，您可以載入現有日曆的現有項目，進行修改，然後將變更儲存回原始檔案。
### Q5：Aspose.Tasks 是否支援重複任務？
答：是的，Aspose.Tasks 可讓您處理重複任務，包括定義其重複模式和持續時間。