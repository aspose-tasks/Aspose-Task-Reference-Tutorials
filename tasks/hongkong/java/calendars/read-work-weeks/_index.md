---
date: 2026-08-13
description: 了解如何使用 Aspose.Tasks for Java 從 MS Project 行事曆讀取工作週。請依循逐步指南，參考程式碼範例與故障排除提示。
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: 使用 Aspose.Tasks 從行事曆讀取工作週
og_description: 使用 Aspose.Tasks for Java 從 MS Project 行事曆讀取工作週的方法。請參考簡明教學，包含設定步驟、程式碼片段與故障排除提示。
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: 使用 Aspose.Tasks 從 MS Project 行事曆讀取工作週的方法
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: 使用 Aspose.Tasks 從 MS Project 行事曆讀取工作週的方法
url: /zh-hant/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 從 MS 日曆讀取工作週

## 簡介
在本教學中，您將**學習如何從 Microsoft Project 日曆讀取工作週**，使用 Aspose.Tasks 的 Java 函式庫。無論您是建立報表儀表板、與 ERP 系統同步排程，或是自動化分析資料的抽取，程式化存取工作週定義都能節省大量手動時間。Aspose.Tasks 支援**超過 50 種輸入與輸出格式**，且能在不將整個檔案載入記憶體的情況下處理數百頁的專案檔，為您提供彈性與效能。

## 快速答案
- **什麼是「讀取工作週」？** 它指的是透過 Java 程式碼從 Project 檔案中提取工作週定義（日期與每日工作時間規則）。  
- **需要哪個函式庫？** Aspose.Tasks for Java（提供免費試用）。  
- **開發是否需要授權？** 試用版可用於測試；正式上線則需商業授權。  
- **支援哪些檔案格式？** 同時支援 *.mpp* 與 Project XML 檔案，另有超過 50 種其他匯入/匯出格式。  
- **實作需要多久時間？** 在設定好函式庫後，通常不到 10 分鐘即可完成。

## 什麼是 MS Project 中的工作週？
工作週定義了資源在特定期間內可用的日曆規則。它包含開始日期、結束日期，以及每日工作時間區間（例如，上午 9 時至下午 5 時）。在 MS Project 中，每個日曆可包含多個工作週，讓您能夠模擬假期、輪班模式或季節性排程。

## Aspose.Tasks 如何從日曆讀取工作週？
Aspose.Tasks 會公開 `Calendar` 物件的 `WorkWeekCollection`。透過建立 `Project` 實例、選取目標日曆（依 UID 或名稱），並遍歷其 `WorkWeekCollection`，即可取得每個工作週的標籤、有效日期範圍以及每日工作時間細節。API 會自動處理所有日期時間的轉換，並遵循專案的時區設定。

## 為什麼要從 Microsoft Project 日曆中以 Java 讀取工作週？
以程式方式讀取工作週可消除手動複製貼上，確保下游系統（ERP、HR、報表）使用完全相同的排程規則，並保證多個專案之間的一致性。自動化亦可減少人為錯誤，並加快整合流程，特別是當您需要每晚處理數十個專案檔時。

## 先決條件
在開始編寫程式碼之前，請確保您已具備以下條件：

1. **Java Development Kit (JDK)** – 已安裝 8 版或更新版本。  
2. **Aspose.Tasks for Java** – 從官方網站下載最新的 JAR： [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/)。  
3. 一個 **範例 Project 檔案** (`ReadWorkWeeksInformation.mpp`)，放置於您電腦上已知的資料夾中。

## 匯入套件
首先，匯入我們需要用來操作日曆與工作週的類別：

`Project` 代表 Microsoft Project 檔案，`Calendar` 提供其日曆，`WorkWeek` 定義工作週，`WeekDay` 代表一天。

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## 步驟 1：設定資料目錄
定義包含 `.mpp` 檔案的資料夾。將佔位符替換為您機器上的實際路徑：

```java
String dataDir = "Your Data Directory";
```

## 步驟 2：建立 Project 實例並存取日曆
`Project` 類別代表 Microsoft Project 檔案，並提供對其資料結構（包括日曆、工作與資源）的存取。  
建立 `Project` 物件，選取您想要的日曆（依 UID），並取得其 `WorkWeekCollection`：

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **小技巧：** 若不確定日曆的 UID，可遍歷 `project.getCalendars()`，先列印每個日曆的名稱與 UID。

## 步驟 3：遍歷工作週
`WorkWeek` 類別封裝工作週定義，包含開始/結束日期與每日工作時間設定。  
遍歷每個 `WorkWeek`，顯示其名稱、開始/結束日期以及每日工作時間：

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**您將看到：** 主控台會列印每個工作週的標籤（例如「Standard」）、其有效日期範圍，且您可以深入查看每一天的具體工作時段。

## 常見問題與解決方案
| 問題 | 原因 | 解決方法 |
|-------|--------|-----|
| `NullPointerException` 在存取 `calendar` 時發生 | UID 錯誤或日曆不存在 | 先使用 `project.getCalendars().size()` 檢查 UID，並先列出可用的日曆。 |
| 工作週無輸出 | 選取的日曆沒有自訂工作週（使用預設） | 使用預設日曆 (`project.getDefaultCalendar()`) 或以程式方式建立工作週。 |
| 日期格式異常 | `System.out.println` 使用預設的 `java.util.Date` 格式 | 使用 `SimpleDateFormat` 依需求格式化日期。 |

## 常見問答
**Q: 我可以使用 Aspose.Tasks for Java 修改工作週資訊嗎？**  
A: 可以。API 提供 `addWorkWeek()`、`removeWorkWeek()` 以及屬性設定方法，以變更名稱、日期與工作時間。

**Q: Aspose.Tasks 是否相容於不同版本的 Microsoft Project 檔案？**  
A: 完全相容。它支援從 Project 98 到最新版本的 MPP 檔案，以及 Project XML 檔案。

**Q: 我可以將 Aspose.Tasks 與其他 Java 框架整合嗎？**  
A: 可以。此函式庫純 Java，您可與 Spring、Jakarta EE 或其他任何框架一起使用。

**Q: Aspose.Tasks 有提供試用版嗎？**  
A: 有，您可從官方網站下載免費 30 天試用版： [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: 我該從哪裡取得 Aspose.Tasks 的支援？**  
A: Aspose 社群論壇是最佳管道： [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

---

**最後更新：** 2026-08-13  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.Tasks for Java 為專案新增日曆](/tasks/java/calendars/create/)
- [使用 Aspose.Tasks 取得日曆例外 – asp tasks java 教學](/tasks/java/calendar-exceptions/retrieve/)
- [如何在 MS Project 中設定日曆與定義工作日 – 使用 Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}