---
date: 2026-07-29
description: 了解如何透過 Aspose.Tasks for Java 建立專案行事曆來排程非工作日，定義工作日例外並管理假期排程。
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: 排程非工作日 – 建立專案行事曆 Aspose
og_description: 使用 Aspose.Tasks for Java 排程非工作日。了解如何定義工作日、加入行事曆例外，並有效管理假期排程。
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: 排程非工作日 – 建立專案行事曆 Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: 排程非工作日 – 建立專案行事曆 Aspose
url: /zh-hant/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 排程非工作日 – 建立專案行事曆 Aspose

### 簡介
當您需要為專案 **排程非工作日** 時，必須能在專案計畫中直接建模假期、特殊班次或臨時關閉。Aspose.Tasks for Java 為您提供完整的行事曆定義控制，讓您加入與實際時間表相符的例外。於本教學中，我們將逐步說明如何為行事曆例外定義工作日，確保專案時間線保持精確可靠。最後，您也會了解此作法如何融入更廣泛的 **非工作日排程** 策略，適用於任何企業專案。

## 快速解答
- **「排程非工作日」是什麼意思？**  
  這表示使用 Aspose.Tasks 建立行事曆，將特定日期標記為非工作日，從而自動影響任務日期。  
- **我需要授權才能執行範例嗎？**  
  免費試用可用於開發；正式上線則需商業授權。  
- **支援哪些 IDE？**  
  IntelliJ IDEA、Eclipse、NetBeans，或任何支援 Java 8+ 的 IDE。  
- **我可以在同一個行事曆中加入多個例外嗎？**  
  可以——您可以根據需要加入任意多個 `CalendarException` 物件。  
- **我可以將專案儲存為哪些檔案格式？**  
  XML、MPP 以及 Aspose.Tasks 支援的其他多種格式。  

## Aspose.Tasks 中的專案行事曆是什麼？
**專案行事曆** 是 Aspose.Tasks 的最高層級物件，用於定義專案的工作日與工作時間。它直接影響任務的開始/結束日期、資源分配以及整體排程計算。透過自訂行事曆，您可確保排程遵守實際限制，例如公司假期或週末工作政策。

## 為何要為行事曆例外定義工作日？
為工作日設定例外可確保專案引擎將這些日子視為非工作日，避免任務自動排程至該日，並使時間線與實際限制（如假期、維護窗口或全公司特殊班次模式）保持一致。

- **精確的時間線：** 任務不會排在假期或停工期間。  
- **資源規劃：** 資源僅在有效工作日分配，避免過度分配。  
- **合規性：** 排程自動遵循組織政策或法定假期行事曆。  

## 使用行事曆例外的非工作日排程
當您維護 **非工作日排程** 時，通常會有一份假期、維護窗口或其他停工期間的主清單。將這些日期加入為 `CalendarException` 物件，可保證所有計算——無論是關鍵路徑分析或資源平衡——自動遵守這些限制。此方式消除手動日期調整，降低排程漂移的風險。

## 前置條件
1. **Java Development Kit (JDK)** – 版本 8 或更新。  
2. **Aspose.Tasks for Java** – 從官方 [Aspose.Tasks Java 下載頁面](https://releases.aspose.com/tasks/java/) 下載。  
3. **IDE** – IntelliJ IDEA、Eclipse、NetBeans，或任何相容 Java 的編輯器。  

## 如何使用行事曆例外排程非工作日

載入您的專案，建立自訂行事曆，並加入將指定工作日標記為非工作日的 `CalendarException` 物件。整個流程只需幾個簡單步驟，最終的行事曆會自動影響所有任務排程邏輯。

### 步驟說明

### 步驟 1：匯入必要的套件
我們需要 Aspose.Tasks 的核心類別以及 Java 的 `GregorianCalendar` 來處理日期。

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### 步驟 2：定義資料目錄
指定產生的專案檔案要儲存的位置。

```java
String dataDir = "Your Data Directory";
```

### 步驟 3：建立 Project 實例
`Project` 是主要物件，保存所有專案資料，包括任務、資源與行事曆。

```java
Project project = new Project();
```

### 步驟 4：定義行事曆
`Calendar` 代表專案內的工作與非工作時間排程。

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### 步驟 5：定義工作日例外
`CalendarException` 代表在行事曆中標記為非工作日的期間。

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### 步驟 6：儲存專案
將專案（包括自訂行事曆及其例外）持久化為 XML 檔案。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **例外日期未套用** | 確保 `setEnteredByOccurrences(false)` 並使用正確的 `FromDate/ToDate` 值。 |
| **儲存的檔案為空** | 確認 `dataDir` 指向可寫入的資料夾，且檔名以 `.xml` 結尾。 |
| **行事曆未在任務排程中反映** | 使用 `task.setCalendar(cal)` 或 `resource.setCalendar(cal)` 將行事曆指派給任務或資源。 |

## 常見問答

**Q: 我可以在同一個行事曆中為不同工作日定義多個例外嗎？**  
A: 可以。對於每個不同的期間或規則，將額外的 `CalendarException` 物件加入 `cal.getExceptions()`。

**Q: Aspose.Tasks for Java 是否相容於不同的 Java IDE？**  
A: 完全相容。此函式庫可在 IntelliJ IDEA、Eclipse、NetBeans 以及任何支援標準 Java 專案的 IDE 中使用。

**Q: 我可以自訂除每日例外之外的例外類型嗎？**  
A: 可以。使用 `CalendarExceptionType.Weekly`、`Monthly` 或 `Yearly` 以符合您的排程需求。

**Q: 如何根據專案需求動態處理例外？**  
A: 以程式方式建立例外物件——例如，從資料庫或設定檔讀取假期日期，並在迴圈中建立 `CalendarException` 實例。

**Q: 是否提供 Aspose.Tasks for Java 的試用版？**  
A: 有，您可從 [Aspose.Tasks Java 下載頁面](https://releases.aspose.com/tasks/java/) 下載免費試用版。

## 結論
透過上述步驟，您現在了解如何透過建立專案行事曆並定義工作日例外，**排程非工作日**，以精確反映假期或特殊非工作期間。正確的行事曆設定對於實際排程、資源分配與專案成功至關重要。可進一步將自訂行事曆指派給任務或資源，並嘗試其他例外類型，打造任何專案的完整 **非工作日排程**。

---

**最後更新：** 2026-07-29  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose

## 相關教學

- [將行事曆加入專案（使用 Aspose.Tasks for Java）](/tasks/java/calendars/create/)
- [建立行事曆例外（Aspose for Java）](/tasks/java/calendar-exceptions/add-remove/)
- [如何在 MS Project 中設定行事曆與定義工作日（使用 Aspose.Tasks）](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}