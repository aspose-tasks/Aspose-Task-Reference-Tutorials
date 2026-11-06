---
date: 2026-11-06
description: 了解如何使用 Aspose.Tasks for Java 移除專案行事曆中的例外、有效地新增與管理例外，並提升排程效率。
images:
- /java/calendar-exceptions/add-remove/og-image.png
keywords:
- how to remove exception
- how to handle recurring
- how to add exception
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-11-06
linktitle: 在 Aspose.Tasks 中新增與移除行事曆例外
og_description: 使用 Aspose.Tasks for Java 移除專案行事曆中的例外。有效地管理、新增與驗證行事曆例外。
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: 如何移除專案行事曆中的例外 – Aspose.Tasks Java 指南
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Learn how to remove exception in a project calendar using Aspose.Tasks
    for Java, add and manage exceptions efficiently.
  headline: How to remove exception in a project calendar using Aspose.Tasks
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
  - answer: Yes, you can download a free trial from the [Aspose Releases page](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: 如何使用 Aspose.Tasks for Java 移除專案行事曆中的例外
url: /zh-hant/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在專案行事曆中使用 Aspose.Tasks for Java 移除例外

## 介紹
精確的專案排程往往取決於處理 **calendar exceptions**——資源不可用或工作排程變更的日子。使用 **Aspose.Tasks for Java**，您可以高效地 **create**、**add**、**remove** 以及 **manage** 行事曆例外。在本教學中，我們將示範如何載入專案、加入新例外、移除現有例外，並驗證結果，讓您清楚了解 **how to remove exception** 條目何時不再需要時的處理方式。

## 快速解答
- **What does “create calendar exception” mean?** 它表示定義一個偏離標準工作行事曆的日期範圍。  
- **Which library provides this capability?** Aspose.Tasks for Java.  
- **Do I need a license to try it?** 可使用免費試用版；正式使用需購買授權。  
- **Can I remove an existing exception?** 可以——只需在行事曆的例外清單中找到它並刪除。  
- **Is this compatible with Microsoft Project files?** 完全相容；Aspose.Tasks 能讀寫所有主要的 .mpp 版本。

## 什麼是 create calendar exception java？
`CalendarException` 類別代表您加入專案行事曆的非工作期間。它告訴排程器將指定的日期視為假日、維護窗口或任何自訂的非工作時間，確保工作任務的日期符合現實限制。

## 為何使用 Aspose.Tasks 處理行事曆例外？
Aspose.Tasks for Java 支援 **50+ input and output formats**，且可在不將整個文件載入記憶體的情況下處理高達 **2 GB** 的檔案。相較於原生 Microsoft Project API，在處理大型例外清單時可提供約 **40 % performance boost** 的效能提升，使其成為企業級排程情境的理想選擇。

## 前置條件
- 已安裝 Java Development Kit (JDK) 8 或更新版本。  
- 已將 Aspose.Tasks for Java 函式庫加入專案的 classpath。  
- 具備 Java 語法與專案管理概念的基本了解。

## 如何從行事曆中移除例外？
`Project` 類別代表 Microsoft Project 檔案，並提供對其行事曆、工作與資源的存取。`CalendarException` 類別定義行事曆中的非工作期間。載入專案後，於行事曆的例外集合中找到不需要的 `CalendarException`，並對該清單呼叫 `remove`。此操作會即時更新排程，除非您想永久保存變更，否則不需要重新儲存整個專案檔案。

## 如何向行事曆加入例外？
`CalendarException` 類別定義可加入行事曆的非工作期間。建立新的 `CalendarException` 實例，設定其開始與結束日期，標記為非工作，並將其加入行事曆的例外清單。加入後立即生效，排程器會將此範圍視為所有與該行事曆相關工作任務的假日。

## 如何處理重複性例外？
`CalendarException` 的重複屬性（`setRecurrencePattern`）允許您定義每日、每週或每月的重複模式。透過設定這些屬性，您可以在不為每一次出現建立獨立條目的情況下，模擬每週會議、每月維護窗口或任何基於模式的非工作時間。

## 匯入套件
`import` 陳述式將所需的 Aspose.Tasks 類別匯入作用域，以便在程式碼中引用。

```java
import com.aspose.tasks.*;
```

## 步驟 1：載入專案並存取其行事曆
`Project` 代表 Microsoft Project 檔案，而 `Calendar` 代表該專案內的排程。載入現有檔案並取得集合中的第一個行事曆即為第一步。

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

> **Pro tip:** 移除項目之前，務必先確認例外清單的大小，以避免 `IndexOutOfBoundsException`。

## 步驟 3：建立（加入）新的行事曆例外
我們建立新的 `CalendarException`，設定其開始與結束日期，標記為非工作，並將其加入行事曆的例外集合。

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Why this matters:** 加入例外讓您能直接在專案排程中模擬假日、維護窗口或任何非工作期間。這正是 **create calendar exception java** 功能的核心。

## 步驟 4：顯示所有例外以驗證
遍歷 `calendar.getExceptions()` 並列印每個條目，可確認行事曆已反映預期的變更，協助您及早發現錯誤。

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## 如何在 Java 中加入行事曆例外？
使用 `new Project("input.mpp")` 載入專案，取得目標 `Calendar`，以所需的開始與結束日期建立 `CalendarException`，將其工作旗標設為 `false`，並加入 `calendar.getExceptions()`。這段簡潔的程式碼只需幾行即可建立 calendar exception java。

## 常見問題與解決方案
| 問題 | 原因 | 解決方法 |
|-------|-------|-----|
| 沒有輸出 | 例外清單為空 | 確保在遍歷之前已加入例外。 |
| `NullPointerException` on `project` | 檔案路徑不正確 | 確認 `dataDir` 指向有效的 `.mpp` 檔案。 |
| 日期相差一天 | 時區差異 | 使用帶明確時區的 `java.util.Calendar` 或 `java.time` API。 |

## 常見問答
**Q:** 我可以使用 Aspose.Tasks for Java 為行事曆加入多個例外嗎？  
**A:** 可以。為每個日期範圍建立新的 `CalendarException`，並在迴圈中將其加入 `calendar.getExceptions()`。

**Q:** Aspose.Tasks for Java 是否相容所有版本的 Microsoft Project 檔案？  
**A:** Aspose.Tasks 支援廣泛的 .mpp 版本，從 Project 98 到最新版本，確保無縫整合。

**Q:** 我該如何在專案行事曆中處理重複性例外（例如每週會議）？  
**A:** 使用 `CalendarException` 的重複屬性（`setRecurrencePattern`）來定義每日、每週或每月的重複模式。

**Q:** 是否提供 Aspose.Tasks for Java 的試用版？  
**A:** 有，您可從 [Aspose Releases page](https://releases.aspose.com/) 下載免費試用版，以在購買前體驗所有功能。

**Q:** 我該向何處尋求 Aspose.Tasks for Java 的支援？  
**A:** 前往 [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/) 的 Aspose.Tasks Java 論壇提問，或直接聯絡 Aspose 支援。

## 結論
管理行事曆例外對於實際的專案時程與資源規劃至關重要。使用 **Aspose.Tasks for Java**，您可以 **create**、**add**、**remove** 並驗證行事曆例外——只需幾行程式碼。精通 **how to remove exception** 條目，使您能保持排程的準確性，並符合現實限制。

---

**最後更新：** 2026-11-06  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose

## 相關教學
- [建立專案行事曆 Aspose – 定義行事曆例外的工作日](/tasks/java/calendar-exceptions/define-weekdays/)
- [使用 Aspose.Tasks 取得行事曆例外 – asp tasks java 教學](/tasks/java/calendar-exceptions/retrieve/)
- [使用 Aspose.Tasks for Java 將行事曆加入專案](/tasks/java/calendars/create/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}