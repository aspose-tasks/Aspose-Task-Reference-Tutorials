---
date: 2026-08-08
description: 學習如何設定 MS Project 行事曆、設定每日工作時數，並使用 Aspose.Tasks for Java 新增週末工作日。只需幾行程式碼即可將專案儲存為
  XML。
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: 如何設定 MS Project 行事曆並定義工作日
og_description: 設定 MS Project 行事曆、定義工作日，並使用 Aspose.Tasks for Java 新增週末工作日。遵循此步驟教學並儲存為
  XML。
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: 使用 Aspose.Tasks 設定 MS Project 行事曆 – Java 指南
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: 如何設定 MS Project 行事曆並定義工作日
url: /zh-hant/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何設定 MS Project 行事曆並定義工作日

在本教學中，您將學習 **如何設定 MS Project 行事曆**（以程式方式），定義工作日，並使用 Aspose.Tasks for Java 庫設定自訂工作日。無論您是建立排程引擎、與 ERP 系統整合，或只是需要在不開啟 Microsoft Project 的情況下產生專案計畫，以下步驟將示範如何建立行事曆、設定每日工作時數，以及以少量程式碼新增週末工作日。

## 快速解答
- **需要哪個函式庫？** Aspose.Tasks for Java.  
- **我可以新增週末工作日嗎？** 可以 – 只需將星期六和星期日標記為工作日。  
- **如何儲存專案？** 呼叫 `prj.save(..., SaveFileFormat.Xml)`.  
- **是否需要授權？** 免費試用可用於評估；正式使用需購買授權。  
- **支援哪個 Java 版本？** Java 8 或更高。

## 什麼是設定 MS Project 行事曆？
在 MS Project 中設定行事曆會決定哪些天算作工作日、每天的工作時數，以及任何特殊例外（例如假日或全公司停工）。此資訊會影響工作排程、資源分配與整體專案時程，確保計算符合組織的實際工作模式。

## 為何使用 Aspose.Tasks 進行行事曆操作？
Aspose.Tasks 讓您在不啟動 Microsoft Project 介面的情況下，以程式方式控制行事曆。它可在任何支援 Java 的作業系統上執行，支援超過 50 種輸入與輸出格式，且能在不將整個檔案載入記憶體的情況下處理數百頁的專案，十分適合伺服器端自動化。

## 前置條件
- **Java Development Kit (JDK) 8+** – 從 [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載。  
- **Aspose.Tasks for Java** – 從 [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/) 取得最新的 JAR。  
- 開發環境或建置工具（Maven/Gradle），將 Aspose.Tasks JAR 加入 classpath。

## 匯入套件
匯入提供專案、行事曆與工作時間物件存取的類別。

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## 步驟說明

### 步驟 1：建立專案實例
建立一個 `Project` 物件，代表您將要操作的 MS Project 檔案。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### 步驟 2：定義新行事曆
`Calendar` 代表專案的一組工作時間、例外與假日。

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### 步驟 3：新增標準工作日（星期一至星期四）
`WeekDay` 定義特定星期幾的工作時間。

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### 步驟 4：新增週末工作日
如果您的專案在週末也執行，請將星期六與星期日加入為一般工作日。此範例示範 **新增週末工作日**。

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### 步驟 5：設定自訂短工作日（星期五）
將星期五設定為上午班（上午 9 時至 12 時）與下午班（下午 1 時至 4 時），以示範 **設定每日工作時數** 與自訂短工作日。

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

### 步驟 6：將專案儲存為 XML
`SaveFileFormat` 列舉儲存專案時支援的檔案格式，例如 XML 或 MPP。

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **工作時間未套用** | 確保在每個自訂的 `WeekDay` 上呼叫 `setDayWorking(true)`。 |
| **儲存時找不到檔案** | 確認 `dataDir` 指向已存在的資料夾，且應用程式具有寫入權限。 |
| **行事曆未在工作項目中反映** | 使用 `task.setCalendar(cal)` 將新建立的行事曆指派給資源或工作項目。 |

## 常見問答

**Q: 我可以使用 Aspose.Tasks for Java 定義自訂非工作日嗎？**  
A: 可以。將任意 `WeekDay` 的 `DayWorking` 屬性設為 `false` 即可將其視為非工作日。

**Q: 我該如何新增假日或全公司例外？**  
A: 建立 `CalendarException` 物件，指定例外日期，並將其加入 `cal.getExceptions()`。

**Q: 此函式庫是否相容於較舊的 MS Project 版本？**  
A: 完全相容。Aspose.Tasks 支援多個版本的 MPP、MPT 與 XML 格式。

**Q: 我可以在匯入的專案中修改現有的行事曆嗎？**  
A: 使用 `new Project("existing.mpp")` 載入專案，取得目標行事曆，進行修改後儲存。

**Q: Aspose.Tasks 也能處理週期性工作項目嗎？**  
A: 可以，您可以使用 `RecurringTask` 類別建立與編輯週期性工作項目。

## 結論
現在您已了解 **如何設定 MS Project 行事曆**、定義工作日、加入週末工作日，以及設定短星期五排程——全部透過 Aspose.Tasks for Java 完成。將結果儲存為 XML，並將行事曆邏輯整合至任何基於 Java 的專案管理解決方案中。

---

**最後更新：** 2026-08-08  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose

## 相關教學

- [使用 Aspose.Tasks for Java 為專案新增行事曆](/tasks/java/calendars/create/)
- [使用 Aspose.Tasks 判斷工作日與工作時數](/tasks/java/calendars/working-hours/)
- [使用 Aspose.Tasks 新增假日至行事曆並儲存為 MPP](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}