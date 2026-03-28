---
date: 2026-01-28
description: 了解如何使用 Aspose.Tasks for Java 建立專案行事曆、為行事曆例外設定工作日，並管理非工作日排程。
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: 建立專案行事曆 Aspose – 為行事曆例外定義工作日
url: /zh-hant/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立專案行事曆 Aspose – 定義行事曆例外的工作日

### 介紹
當您需要 **create project calendar aspose** 時，必須能夠建模非標準工作日，例如假期、特殊班次或臨時關閉。Aspose.Tasks for Java 為您提供完整的行事曆定義控制，讓您能加入反映真實情況的例外。在本教學中，我們將逐步說明如何為行事曆例外定義工作日，確保您的專案時間表保持精確可靠。最後，您還會了解此作法如何融入更廣泛的 **non‑working days schedule** 策略，適用於任何企業專案。

## 快速解答
- **「create project calendar aspose」是什麼意思？**  
  它指的是使用 Aspose.Tasks 建立一個自訂的行事曆物件，以驅動工作排程。  
- **執行範例是否需要授權？**  
  開發階段可使用免費試用版；正式上線則需商業授權。  
- **支援哪些 IDE？**  
  IntelliJ IDEA、Eclipse、NetBeans，或任何支援 Java 8+ 的 IDE。  
- **可以在同一行事曆中加入多個例外嗎？**  
  可以 — 您可以依需求加入任意數量的 `CalendarException` 物件。  
- **專案可以儲存為哪些檔案格式？**  
  XML、MPP，以及 Aspose.Tasks 支援的其他多種格式。  

## Aspose.Tasks 中的專案行事曆是什麼？
**專案行事曆** 定義了專案的工作日與工作時間。它會影響工作項目的開始/結束日期、資源分配以及整體排程計算。透過自訂行事曆，您可確保排程遵循真實世界的限制，例如公司假期或週末工作政策。

## 為什麼要為行事曆例外定義工作日？
- **準確的時間表：** 工作項目不會排程在標記為非工作日的日子。  
- **資源規劃：** 資源僅在有效的工作日分配。  
- **合規性：** 使專案排程符合組織政策或法定假期。  

## 使用行事曆例外的非工作日排程
當您維護 **non‑working days schedule** 時，通常會有一份包含假期、維護窗口或其他停工期間的主清單。將這些日期以 `CalendarException` 物件加入，可確保所有計算——無論是關鍵路徑分析或資源平衡——自動遵守這些限制。此做法可消除手動日期調整，降低排程漂移的風險。

## 前置條件
在開始之前，請確保您已具備以下項目：

1. **Java Development Kit (JDK)** – 8 版或更新版本。  
2. **Aspose.Tasks for Java** – 從官方 [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/) 下載。  
3. **IDE** – IntelliJ IDEA、Eclipse、NetBeans，或任何相容 Java 的編輯器。  

## 如何建立專案行事曆 Aspose – 定義行事曆例外的工作日

### 步驟指南

### 步驟 1：匯入必要的套件
我們需要匯入 Aspose.Tasks 的核心類別以及 Java 的 `GregorianCalendar` 以處理日期。

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
建立一個新的 `Project` 物件——它是所有專案資料（包括行事曆）的容器。

```java
Project project = new Project();
```

### 步驟 4：定義行事曆
將自訂行事曆加入專案。此行事曆將保存我們的例外設定。

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### 步驟 5：定義工作日例外
建立一個 `CalendarException`，將一段日期（例如十二月最後一週）標記為非工作日。  
範例將例外設定為 **2009 年 12 月 24 日** 至 **2009 年 12 月 31 日**，在這些日子停工，且將例外類型設為每日。

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
將專案（包含自訂行事曆及其例外）持久化為 XML 檔案。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **例外日期未套用** | 確保 `setEnteredByOccurrences(false)` 並使用正確的 `FromDate/ToDate` 值。 |
| **儲存的檔案為空** | 確認 `dataDir` 指向可寫入的資料夾，且檔名以 `.xml` 結尾。 |
| **行事曆未在工作排程中反映** | 使用 `task.setCalendar(cal)` 或 `resource.setCalendar(cal)` 將行事曆指派給工作或資源。 |

## 常見問答

**Q: 可以在同一行事曆中為不同的工作日定義多個例外嗎？**  
A: 可以。為每個不同的期間或規則向 `cal.getExceptions()` 新增 `CalendarException` 物件。

**Q: Aspose.Tasks for Java 是否相容於不同的 Java IDE？**  
A: 當然。此函式庫可在 IntelliJ IDEA、Eclipse、NetBeans 以及任何支援標準 Java 專案的 IDE 中使用。

**Q: 我可以自訂除每日例外之外的例外類型嗎？**  
A: 可以。使用 `CalendarExceptionType.Weekly`、`Monthly` 或 `Yearly` 以符合您的排程需求。

**Q: 如何根據專案需求動態處理例外？**  
A: 以程式方式建立例外物件——例如，從資料庫或設定檔讀取假期日期，並在迴圈中建立 `CalendarException` 實例。

**Q: 是否提供 Aspose.Tasks for Java 的試用版？**  
A: 有，您可從 [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/) 下載免費試用版。

## 結論
透過上述步驟，您現在已了解如何 **create project calendar aspose** 並定義能精確反映假期或特殊非工作期間的工作日例外。正確的行事曆設定對於實際的排程、資源分配及整體專案成功至關重要。您可進一步將自訂行事曆指派給工作或資源，並嘗試其他例外類型，以建立完整的 **non‑working days schedule**，適用於任何專案。

---

**最後更新：** 2026-01-28  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}