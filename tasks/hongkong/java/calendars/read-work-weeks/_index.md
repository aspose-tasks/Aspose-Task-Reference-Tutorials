---
date: 2025-12-03
description: 學習如何使用 Aspose.Tasks 從 Microsoft Project 行事曆中讀取 Java 工作週。請跟隨一步一步的指南，並附上完整程式碼範例。
language: zh-hant
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 在 Java 中從 MS Project 行事曆讀取工作週
url: /java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 從 MS Project 行事曆讀取工作週（Java） – Aspose.Tasks

## 介紹
在本教學中，您將 **使用 Aspose.Tasks 程式庫從 Microsoft Project 行事曆讀取工作週（Java）**。無論您是建立報表工具、同步排程，或是自動化專案資料擷取，能以程式方式取得工作週定義都能節省大量手動時間。我們將說明必要的設定步驟，提供完整程式碼範例，並逐步解說每個步驟，讓您能將此解決方案套用到自己的專案中。

## 快速回答
- **「read work weeks java」是什麼意思？** 指的是使用 Java 程式碼從 Project 檔案中擷取工作週定義。  
- **需要哪個程式庫？** Aspose.Tasks for Java（提供免費試用版）。  
- **開發時需要授權嗎？** 測試可使用試用版；正式上線需購買商業授權。  
- **支援哪些檔案格式？** 同時支援 *.mpp* 與 Project XML 檔案。  
- **實作需要多久？** 在安裝程式庫後，通常不超過 10 分鐘即可完成。

## 什麼是「read work weeks java」？
在 Java 中讀取工作週，即使用 Aspose.Tasks API 取得 Microsoft Project 檔案內行事曆物件的 `WorkWeekCollection`。每個 `WorkWeek` 包含開始/結束日期以及每日的工作時間定義，這些資訊決定資源的排程方式。

## 為什麼要從 Microsoft Project 行事曆讀取工作週（Java）？
- **自動化：** 消除手動複製排程資料的步驟。  
- **整合：** 將工作週資訊輸入 ERP、HR 或自訂報表系統。  
- **一致性：** 確保所有下游工具遵循 Project 檔案中定義的相同行事曆規則。

## 前置條件
在開始撰寫程式碼前，請先確保您已具備：

1. **Java Development Kit (JDK)** – 已安裝 8 版或更新版本。  
2. **Aspose.Tasks for Java** – 從官方網站下載最新 JAR 檔案：[Aspose.Tasks for Java 下載](https://releases.aspose.com/tasks/java/)。  
3. 一個 **範例 Project 檔案**（`ReadWorkWeeksInformation.mpp`），放置於已知資料夾中。

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
定義存放 `.mpp` 檔案的資料夾路徑。將佔位字串替換為您機器上的實際路徑：

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

> **小技巧：** 若不確定行事曆的 UID，可遍歷 `project.getCalendars()`，列印每個行事曆的名稱與 UID。

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

**您將看到的結果：** 主控台會印出每個工作週的標籤（例如「Standard」）、其有效日期範圍，並可深入查看每一天的具體工作時段。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| `NullPointerException` 於存取 `calendar` 時發生 | UID 錯誤或行事曆不存在 | 使用 `project.getCalendars().size()` 檢查 UID，先列出可用的行事曆 |
| 工作週沒有輸出 | 所選行事曆未設定自訂工作週（使用預設） | 改用預設行事曆 `project.getDefaultCalendar()`，或以程式方式建立工作週 |
| 日期格式怪異 | `System.out.println` 使用預設的 `java.util.Date` 格式 | 使用 `SimpleDateFormat` 依需求格式化日期 |

## 常見問答

**Q: 可以使用 Aspose.Tasks for Java 修改工作週資訊嗎？**  
A: 可以。API 提供 `addWorkWeek()`、`removeWorkWeek()` 以及屬性設定方法，讓您變更名稱、日期與工作時間。

**Q: Aspose.Tasks 是否相容不同版本的 Microsoft Project 檔案？**  
A: 完全相容。支援從 Project 98 到最新版本的 MPP 檔案，同時支援 Project XML 檔案。

**Q: 能否將 Aspose.Tasks 與其他 Java 框架整合？**  
A: 能。此程式庫為純 Java，您可以與 Spring、Jakarta EE 或其他框架一起使用。

**Q: 是否提供 Aspose.Tasks 的試用版？**  
A: 有，您可從官方網站下載 30 天免費試用版：[Aspose.Tasks 試用版](https://releases.aspose.com/)。

**Q: 在哪裡可以取得 Aspose.Tasks 的支援？**  
A: 最佳管道是 Aspose 社群論壇：[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)。

## 結論
您已掌握使用 Aspose.Tasks 讀取工作週（Java）的完整流程。依照上述步驟，即可程式化取得任何 MS Project 行事曆中的工作週定義，將資料整合至您的應用程式，並自動化排程相關工作流程。歡迎自行嘗試建立或更新工作週——Aspose.Tasks 讓這一切變得簡單。

---

**最後更新：** 2025-12-03  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}