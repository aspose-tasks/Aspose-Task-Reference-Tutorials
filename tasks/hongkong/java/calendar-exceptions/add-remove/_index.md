---
date: 2026-01-28
description: 學習如何使用 Aspose.Tasks for Java 建立行事曆例外、有效地新增與移除行事曆例外，並提升專案排程。
linktitle: Add and Remove Calendar Exceptions in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 為 Java 的 Aspose 建立日曆例外
url: /zh-hant/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 Calendar Exception Aspose for Java

## 介紹
準確的專案排程往往取決於處理 **calendar exceptions**——資源不可用或工作時間變更的日子。使用 **Aspose.Tasks for Java**，您可以 **建立 calendar exception** 物件，將它加入專案行事曆，或在不需要時將其移除。本教學將從載入專案檔案到驗證您所管理的例外，完整說明整個流程。本指南會精確示範如何在 Java 環境中 **create calendar exception aspose**。

### 快速解答
- **「create calendar exception」是什麼意思？** 意指定義一段與標準工作行事曆不同的日期範圍。  
- **哪個函式庫提供此功能？** Aspose.Tasks for Java。  
- **試用需要授權嗎？** 提供免費試用版；正式環境需購買授權。  
- **可以移除已存在的例外嗎？** 可以——只要在行事曆的例外清單中找到並刪除即可。  
- **這與 Microsoft Project 檔案相容嗎？** 完全相容；Aspose.Tasks 能讀所有主要的 .mpp 版本。

#### 前置條件
開始之前，請確保您已具備：

- 已安裝 Java Development Kit (JDK)。  
- 已將 Aspose.Tasks for Java 函式庫加入專案的 classpath。  
- 具備基本的 Java 與專案管理術語知識。

## 如何使用 Java 建立 calendar exception Aspose
以下提供逐步說明，並在每段程式碼執行前說明其目的。請依序閱讀，以確保您的行事曆例外能正確處理。

## 匯入套件
首先，匯入支援行事曆操作的核心 Aspose.Tasks 類別。

```java
import com.aspose.tasks.*;
```

## 步驟 1：載入專案並取得其行事曆
我們先載入既有的 Microsoft Project 檔案 (`input.mpp`)，並取得集合中的第一個行事曆。若需其他行事曆，可自行調整索引。

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## 步驟 2：移除已存在的例外（如有需要）
有時行事曆已包含例外，您可能想要清除。以下程式碼會檢查例外清單，當例外數量大於一筆時，移除第一筆。

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **專業提示：** 在移除項目之前，務必先確認例外清單的大小，以避免拋出 `IndexOutOfBoundsException`。

## 步驟 3：建立（加入）新的 Calendar Exception
現在我們 **create calendar exception** 物件。此範例建立一個涵蓋 2009 年 1 月 1 日至 3 日的例外。請依您的專案時程調整日期。

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **為何重要：** 加入例外可讓您在專案排程中直接模擬假日、維護窗口或任何非工作期間。這正是 **create calendar exception aspose** 功能的核心。

## 步驟 4：顯示所有例外以供驗證
加入（或移除）例外後，建議將其列印出來，以確認行事曆已正確反映變更。

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 沒有任何輸出 | 例外清單為空 | 確認在迭代前已加入例外。 |
| `NullPointerException` 發生在 `project` | 檔案路徑不正確 | 檢查 `dataDir` 是否指向有效的 `.mpp` 檔案。 |
| 日期相差一天 | 時區差異 | 使用帶明確時區的 `java.util.Calendar` 或 `java.time` API。 |

## 常見問答

**Q: 可以使用 Aspose.Tasks for Java 為行事曆加入多筆例外嗎？**  
A: 可以。只要在迴圈中為每個日期範圍建立新的 `CalendarException`，再加入 `cal.getExceptions()` 即可。

**Q: Aspose.Tasks for Java 是否相容所有版本的 Microsoft Project 檔案？**  
A: Aspose.Tasks 支援廣泛的 .mpp 版本，從 Project 98 到最新版本，確保無縫整合。

**Q: 如何在專案行事曆中處理週期性例外（例如每週會議）？**  
A: 使用 `CalendarException` 的週期屬性（`setRecurrencePattern`）來定義每日、每週或每月的重複模式。

**Q: 有提供 Aspose.Tasks for Java 的試用版嗎？**  
A: 有，您可從 [website](https://releases.aspose.com/) 下載免費試用版，先行體驗全部功能。

**Q: 若遇到問題或有疑問，該向哪裡尋求支援？**  
A: 前往 Aspose.Tasks Java 論壇的 [website](https://reference.aspose.com/tasks/java/) 提問，或直接聯絡 Aspose 客服。

## 結論
管理 calendar exceptions 對於打造符合實際情況的專案時程與資源規劃至關重要。透過 **Aspose.Tasks for Java**，您可以 **create calendar exception** 物件，將其加入任意專案行事曆，並在不再需要時將其移除，只需幾行程式碼。此 **create calendar exception aspose** 能力讓您建立的排程真正反映現實限制。

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}