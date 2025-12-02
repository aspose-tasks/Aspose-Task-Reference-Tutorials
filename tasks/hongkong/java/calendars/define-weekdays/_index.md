---
date: 2025-12-02
description: 學習如何設定日曆、在 MS Project 中定義工作日，並使用 Aspose.Tasks for Java 設定自訂工作日。只需幾行程式碼即可將專案儲存為
  XML。
language: zh-hant
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 MS Project 中使用 Aspose.Tasks 設定行事曆與定義工作日
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 MS Project 中使用 Aspose.Tasks 設定日曆與定義工作日

## 介紹
在本教學中，您將學會 **如何設定日曆**，透過 Aspose.Tasks for Java 程式化地設定 Microsoft Project 檔案的日曆與工作日。無論是建立標準工作週、加入週末工作日，或是配置短暫的星期五排程，本指南都會一步步帶您完成——從建立專案到以 XML 格式儲存檔案。

## 快速解答
- **需要哪個函式庫？** Aspose.Tasks for Java  
- **可以加入週末工作日嗎？** 可以，只要將星期六與星期日設為工作日即可。  
- **如何儲存專案？** 使用 `prj.save(..., SaveFileFormat.Xml)`。  
- **需要授權嗎？** 評估可使用免費試用版；正式環境必須購買授權。  
- **需要哪個 Java 版本？** Java 8 或以上。

## 在 MS Project 中「設定日曆」是什麼意思？
在 MS Project 中設定日曆即是定義哪些天是工作日、每日的工作時段，以及例外情況（例如假日）。此日曆會影響工作排程、資源分配與整體專案時程。

## 為什麼使用 Aspose.Tasks 來操作日曆？
- **完整控制** – 可程式化建立、修改或刪除日曆，無需開啟 UI。  
- **跨平台** – 在任何支援 Java 的作業系統上皆可執行。  
- **支援所有檔案格式** – MPP、MPT 與 XML，讓您能 *將專案另存為 XML*，方便與其他系統整合。  
- **無 COM 相依** – 不同於 Microsoft Project Interop 函式庫。

## 前置需求
開始之前，請確保您已具備：

1. **Java Development Kit (JDK) 8+** – 從 [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載。  
2. **Aspose.Tasks for Java** – 從 [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/) 取得最新 JAR。  
3. 具備 IDE 或建置工具（Maven/Gradle），以將 Aspose.Tasks JAR 加入專案的 classpath。

## 匯入套件
首先，匯入您需要的類別。這些匯入讓您可以存取專案、日曆與工作時間相關的物件。

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## 步驟說明

### 步驟 1：建立 Project 實例
建立一個新的 `Project` 物件。此物件代表您即將編輯的 MS Project 檔案。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### 步驟 2：定義新日曆
將全新日曆加入專案。為日曆命名有助於在有多個日曆時辨識。

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### 步驟 3：加入標準工作日（星期一至星期四）
使用內建輔助方法 `WeekDay.createDefaultWorkingDay`，為核心工作週設定預設的 9 am‑5 pm 時段。

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### 步驟 4：加入週末工作日
如果您的專案需要在週末執行，只要將星期六與星期日加入為一般工作日，即可示範 **加入週末工作日**。

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### 步驟 5：設定自訂的短工作日（星期五）
此處 **設定自訂工作日** 為星期五：上午班 (9 am‑12 pm) 與下午班 (1 pm‑4 pm)。

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

### 步驟 6：將專案另存為 XML
最後，將變更寫入檔案。`SaveFileFormat.Xml` 選項讓您 **將專案另存為 XML**，便於與其他工具整合。

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **工作時間未套用** | 確認已對自訂 `WeekDay` 呼叫 `setDayWorking(true)`。 |
| **儲存時找不到檔案** | 檢查 `dataDir` 是否指向已存在的資料夾，且應用程式具備寫入權限。 |
| **日曆未在工作項目中反映** | 使用 `task.setCalendar(cal)` 將新建立的日曆指派給資源或工作項目。 |

## 常見問答

**Q: 可以使用 Aspose.Tasks for Java 定義自訂的非工作日嗎？**  
A: 可以。將任意 `WeekDay` 的 `DayWorking` 屬性設為 `false` 即可。

**Q: 要如何加入假日或全公司例外？**  
A: 建立 `CalendarException` 物件，設定例外日期，然後加入 `cal.getExceptions()`。

**Q: 此函式庫是否相容舊版的 MS Project？**  
A: 完全相容。Aspose.Tasks 支援多個 Project 版本的 MPP、MPT 與 XML 格式。

**Q: 能否在匯入的專案中修改既有日曆？**  
A: 可以，使用 `new Project("existing.mpp")` 載入專案，取得目標日曆後進行修改，最後儲存。

**Q: Aspose.Tasks 也能處理週期性工作項目嗎？**  
A: 能，您可以使用 `RecurringTask` 類別建立與編輯週期性工作項目。

## 結論
現在您已掌握 **如何設定日曆**、**在 MS Project 中定義工作日**、加入週末工作日以及建立短暫的星期五排程，全部透過 Aspose.Tasks for Java 完成。將結果另存為 XML，便能將日曆邏輯整合至任何基於 Java 的專案管理解決方案。

---

**最後更新：** 2025-12-02  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}