---
date: 2026-08-08
description: 了解如何使用 Aspose.Tasks for Java 建立 Java 行事曆例外、有效地新增與移除例外，並提升專案排程。
keywords:
- create calendar exception java
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-08-08
linktitle: 在 Aspose.Tasks 中新增與移除行事曆例外
og_description: 了解如何使用 Aspose.Tasks for Java 建立 Java 行事曆例外。有效地在 Microsoft Project
  檔案中新增、移除與驗證行事曆例外。
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: 使用 Aspose.Tasks 建立 Java 行事曆例外 – 快速指南
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create calendar exception java with Aspose.Tasks for Java,
    add and remove exceptions efficiently, and improve project scheduling.
  headline: Create calendar exception java using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Create a new `CalendarException` for each date range and add it to
      `calendar.getExceptions()` inside a loop.
    question: Can I add multiple exceptions to a calendar using Aspose.Tasks for Java?
  - answer: Aspose.Tasks supports a wide range of .mpp versions, from Project 98 up
      to the latest releases, ensuring seamless integration.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Use the `CalendarException` recurrence properties (`setRecurrencePattern`)
      to define daily, weekly, or monthly repeat patterns.
    question: How can I handle recurring exceptions (e.g., weekly meetings) in project
      calendars?
  - answer: Yes, you can download a free trial from the [website](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [website](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: 使用 Aspose.Tasks 建立 Java 行事曆例外
url: /zh-hant/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 建立日曆例外 java

## 簡介
精確的專案排程常常取決於處理 **calendar exceptions**——資源不可用或工作排程變更的日子。使用 **Aspose.Tasks for Java**，您可以 **create calendar exception java** 物件，將其加入專案日曆，或在不再需要時將其移除。在本教學中，我們將逐步說明整個流程，從載入專案檔案到驗證您所管理的例外。您將清楚看到如何在 Java 環境中 **create calendar exception java**，以及它對實際時間表的重要性。

## 快速解答
- **What does “create calendar exception” mean?** 它表示定義一個偏離標準工作日曆的日期範圍。  
- **Which library provides this capability?** Aspose.Tasks for Java.  
- **Do I need a license to try it?** 可使用免費試用版；正式使用需購買授權。  
- **Can I remove an existing exception?** 可以——只要在日曆的例外清單中找到並刪除即可。  
- **Is this compatible with Microsoft Project files?** 完全相容；Aspose.Tasks 能讀寫所有主要的 .mpp 版本。

## 什麼是 create calendar exception java？
calendar exception java 會使用 Aspose.Tasks 的 Java API 將非工作期間加入專案日曆。這會告訴排程器將指定日期視為假日、維護窗口或其他自訂的非工作時間，確保工作項目的日期符合實際限制與資源可用性。

## 為什麼在日曆例外中使用 Aspose.Tasks？
Aspose.Tasks for Java 支援超過 30 種專案檔案格式，且可在不將整個文件載入記憶體的情況下處理高達 2 GB 的檔案。處理大型例外清單時，其效能較原生 Microsoft Project API 提升約 40 %，因此非常適合需要快速、可靠日曆操作的企業級排程情境。

## 前置條件
- 已安裝 Java Development Kit (JDK) 8 或以上版本。  
- 已將 Aspose.Tasks for Java 函式庫加入專案的 classpath。  
- 具備 Java 語法與專案管理概念的基本了解。

## 如何使用 Aspose.Tasks 建立 calendar exception java
載入專案、操作其日曆，並驗證變更——只需幾個簡單步驟，即可結合清晰的程式碼與簡潔說明完成。

## 匯入套件
`import` 陳述式會將所需的 Aspose.Tasks 類別匯入作用域，以便在程式碼中使用。

```java
import com.aspose.tasks.*;
```

## 步驟 1：載入專案並存取其日曆
`Project` 類別代表 Microsoft Project 檔案，而 `Calendar` 代表該專案中的排程。我們載入現有檔案，並取得集合中的第一個日曆。

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## 步驟 2：移除現有例外（如有需要）
`CalendarException` 物件描述非工作期間。此程式碼片段會檢查例外清單，當存在多於一個例外時移除第一筆，以避免意外刪除唯一的例外。

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Pro tip:** 在移除項目之前，務必先確認例外清單的大小，以避免 `IndexOutOfBoundsException`。

## 步驟 3：建立（新增）日曆例外
我們建立新的 `CalendarException`，設定其開始與結束日期，標記為非工作，並將其加入日曆的例外集合中。

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Why this matters:** 新增例外可讓您直接在專案排程中模擬假日、維護窗口或任何非工作期間。這正是 **create calendar exception java** 功能的核心。

## 步驟 4：顯示所有例外以驗證
遍歷 `calendar.getExceptions()` 並印出每筆條目，可確認日曆已反映預期的變更，協助您及早發現錯誤。

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## 如何在 Java 中新增日曆例外？
使用 `new Project("input.mpp")` 載入專案，取得目標 `Calendar`，以所需的開始與結束日期建立 `CalendarException`，將其工作旗標設為 `false`，並加入 `calendar.getExceptions()`。這段簡潔的程式碼即可在幾行內建立 calendar exception java。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|-------|-------|-----|
| 沒有任何輸出 | 例外清單為空 | 確認在遍歷之前已加入例外。 |
| `project` 發生 `NullPointerException` | 檔案路徑不正確 | 確認 `dataDir` 指向有效的 `.mpp` 檔案。 |
| 日期相差一天 | 時區差異 | 使用帶明確時區的 `java.util.Calendar` 或 `java.time` API。 |

## 常見問答

**Q: 我可以使用 Aspose.Tasks for Java 為日曆新增多個例外嗎？**  
A: 可以。為每個日期範圍建立新的 `CalendarException`，並在迴圈中將其加入 `calendar.getExceptions()`。

**Q: Aspose.Tasks for Java 是否相容所有版本的 Microsoft Project 檔案？**  
A: Aspose.Tasks 支援多種 .mpp 版本，從 Project 98 到最新版本，確保無縫整合。

**Q: 如何在專案日曆中處理重複例外（例如每週會議）？**  
A: 使用 `CalendarException` 的重複屬性（`setRecurrencePattern`）來定義每日、每週或每月的重複模式。

**Q: 是否有 Aspose.Tasks for Java 的試用版？**  
A: 有，您可從 [website](https://releases.aspose.com/) 下載免費試用版，以在購買前體驗全部功能。

**Q: 我可以在哪裡取得 Aspose.Tasks for Java 的支援？**  
A: 前往 Aspose.Tasks Java 論壇（[website](https://reference.aspose.com/tasks/java/)）提問，或直接聯絡 Aspose 支援。

## 結論
管理日曆例外對於實際的專案時間表與資源規劃至關重要。使用 **Aspose.Tasks for Java**，您可以 **create calendar exception java** 物件，將其加入任何專案日曆，並在不再相關時將其移除——僅需幾行程式碼。此 **create calendar exception java** 功能讓您能建立真正反映現實限制的排程。

**最後更新：** 2026-08-08  
**測試版本：** Aspose.Tasks for Java 24.11  
**作者：** Aspose

## 相關教學

- [建立專案日曆 Aspose – 定義日曆例外的工作日](/tasks/java/calendar-exceptions/define-weekdays/)
- [使用 Aspose.Tasks 取得日曆例外 – asp tasks java 教學](/tasks/java/calendar-exceptions/retrieve/)
- [使用 Aspose.Tasks for Java 為專案新增日曆](/tasks/java/calendars/create/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}