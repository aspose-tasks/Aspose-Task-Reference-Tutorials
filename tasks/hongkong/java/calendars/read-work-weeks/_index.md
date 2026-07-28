---
date: 2026-02-05
description: 學習如何使用 Aspose.Tasks 從 Microsoft Project 行事曆讀取工作週（Java）。請跟隨一步一步的指南，內含完整程式碼範例。
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 從 MS Project 行事曆讀取工作週（Java）
url: /zh-hant/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何從 MS Project 行事曆使用 Aspose.Tasks 讀取 Workweeks Java

## 簡介
在本教學中，您將 **學會如何使用 Aspose.Tasks 套件從 Microsoft Project 行事曆讀取 workweeks Java**。無論您是要建立報表工具、同步排程，或是自動化專案資料抽取，能以程式方式存取工作週定義都能省下大量手動時間。我們將說明必要的設定步驟、提供完整的程式碼範例，並解釋每一步的原理，讓您能將此解決方案套用到自己的專案中。

## 快速解答
- **「read workweeks java」是什麼意思？** 它指的是使用 Java 程式碼從 Project 檔案中提取工作週定義。  
- **需要哪個函式庫？** Aspose.Tasks for Java（提供免費試用）。  
- **開發時需要授權嗎？** 試用版可用於測試；正式環境需購買商業授權。  
- **支援哪些檔案格式？** 同時支援 *.mpp* 與 Project XML 檔案。  
- **實作大約需要多久？** 在設定好函式庫後，通常不超過 10 分鐘。

## 如何從 Microsoft Project 行事曆讀取 Workweeks Java
在 Java 中讀取工作週即是使用 Aspose.Tasks API 取得 Microsoft Project 檔案內行事曆物件的 `WorkWeekCollection`。每個 `WorkWeek` 包含開始/結束日期以及每日工作時間的定義，這些定義決定資源的排程方式。

## 為什麼要從 Microsoft Project 行事曆讀取 Workweeks Java？
- **自動化：** 消除手動複製排程資料的步驟。  
- **整合：** 將工作週資訊輸入 ERP、HR 或自訂報表系統。  
- **一致性：** 確保所有下游工具遵循 Project 檔案中定義的相同行事曆規則。

## 先決條件
在開始撰寫程式碼之前，請確保您已具備以下條件：

1. **Java Development Kit (JDK)** – 安裝 8 版或更新版本。  
2. **Aspose.Tasks for Java** – 從官方網站下載最新 JAR：[Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/)。  
3. 一個 **範例 Project 檔案** (`ReadWorkWeeksInformation.mpp`)，放置於已知資料夾。

## 匯入套件
首先，匯入與行事曆及工作週互動所需的類別：

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
定義存放 `.mpp` 檔案的資料夾路徑。請將佔位符替換為您機器上的實際路徑：

```java
String dataDir = "Your Data Directory";
```

## 步驟 2：建立 Project 實例並存取行事曆
建立 `Project` 物件，依 UID 取得目標行事曆，並取得其 `WorkWeekCollection`：

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **專業提示：** 如果不確定行事曆的 UID，可以遍歷 `project.getCalendars()`，並印出每個行事曆的名稱與 UID。

## 步驟 3：遍歷工作週
迭代每個 `WorkWeek`，顯示其名稱、開始/結束日期以及每日工作時間：

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

**您將看到：** 主控台會印出每個工作週的標籤（例如「Standard」）、其有效日期範圍，並可深入查看每一天的工作時間。

## 常見問題與解決方案
| 問題 | 原因 | 解決方法 |
|------|------|----------|
| `NullPointerException` 於存取 `calendar` 時發生 | UID 錯誤或行事曆不存在 | 先使用 `project.getCalendars().size()` 檢查 UID，並先列出可用的行事曆。 |
| 工作週無輸出 | 所選行事曆沒有自訂工作週（使用預設） | 使用預設行事曆 (`project.getDefaultCalendar()`) 或以程式方式建立工作週。 |
| 日期格式異常 | `System.out.println` 使用預設的 `java.util.Date` 格式 | 使用 `SimpleDateFormat` 依需求格式化日期。 |

## 常見問答

**Q: 我可以使用 Aspose.Tasks for Java 修改工作週資訊嗎？**  
A: 可以。API 提供 `addWorkWeek()`、`removeWorkWeek()` 等方法，以及屬性設定子，用於變更名稱、日期與工作時間。

**Q: Aspose.Tasks 是否相容於不同版本的 Microsoft Project 檔案？**  
A: 絕對相容。支援從 Project 98 到最新版本的 MPP 檔案，以及 Project XML 檔案。

**Q: 我可以將 Aspose.Tasks 與其他 Java 框架整合嗎？**  
A: 可以。此函式庫純粹為 Java 實作，可與 Spring、Jakarta EE 或其他任何框架一起使用。

**Q: Aspose.Tasks 有提供試用版嗎？**  
A: 有，您可從官方網站下載免費 30 天試用版：[Aspose.Tasks trial](https://releases.aspose.com/)。

**Q: 我可以在哪裡取得 Aspose.Tasks 的支援？**  
A: Aspose 社群論壇是最佳支援管道：[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

## 結論
您已掌握 **如何使用 Aspose.Tasks 讀取 workweeks Java** 的完整流程。依照上述步驟，您可以程式化地從任何 MS Project 行事曆中抽取工作週定義，將資料整合至應用程式，並自動化排程相關的工作流程。歡迎嘗試建立或更新工作週——Aspose.Tasks 讓這些操作變得相當簡單。

---

**最後更新：** 2026-02-05  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}