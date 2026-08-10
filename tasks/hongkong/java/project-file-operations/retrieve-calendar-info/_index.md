---
date: 2026-03-27
description: 學習如何使用 Aspose 及 Aspose.Tasks 以 Java 從 Microsoft Project 檔案中擷取專案行事曆詳細資訊。逐步說明與程式碼範例。
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 取得 MS Project 行事曆資訊
url: /zh-hant/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 取得 MS Project 行事曆資訊

## Introduction
在本教學中，**您將了解如何使用 Aspose.Tasks**以程式方式從 Microsoft Project 檔案中取得行事曆資訊。取得工作天、工作時數與例外等行事曆資料在您需要**提取專案行事曆**以進行報告、整合或自訂排程邏輯時是必不可少的。讓我們一步一步走過整個流程，您將會看到**如何使用 Aspose**從 *.mpp* 檔案中提取這些資料。

## Quick Answers
- **此教學使用哪個函式庫？** Aspose.Tasks for Java.  
- **涵蓋的主要關鍵字是？** *how to use aspose*.  
- **您可以提取什麼？** 專案行事曆，包括工作天與工作時數。  
- **我需要授權嗎？** 可使用免費試用版；正式環境需購買授權。  
- **支援的 Java 版本為？** Java 8 或以上.

## What is Aspose.Tasks and Why Use It?
Aspose.Tasks 是一個功能強大的 Java API，讓開發人員能在不需要 Microsoft Project 本身的情況下讀取、寫入與操作 Microsoft Project 檔案。透過使用 Aspose.Tasks，您可以**如何提取行事曆**資訊、自動化排程計算，並將專案資料與其他企業系統整合——全部以純 Java 程式碼完成。

## Why extract project calendar information?
為何要提取專案行事曆資訊？

專案行事曆決定任務日期、資源分配與整體時間線計算。提取這些資料您可以：
- 產生反映實際工作排程的自訂報告。  
- 將 Microsoft Project 時間線與外部系統（ERP、BI 等）同步。  
- 透過程式方式修改行事曆設定，執行假設分析。  
- **提取 MS Project 行事曆**資料，以遷移至其他規劃工具。

## Prerequisites
先決條件

在開始之前，請確保您已具備：

- 基本的 Java 程式設計知識。  
- 系統已安裝 Java Development Kit (JDK)。  
- Aspose.Tasks for Java 函式庫。您可從 [here](https://releases.aspose.com/tasks/java/) 下載。

## Import Packages
匯入套件

首先，將必要的 Aspose.Tasks 類別匯入您的 Java 專案。

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Step 1: Set Data Directory
步驟 1：設定資料目錄

定義包含 *.mpp* 檔案的資料夾。

```java
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為 **project.mpp** 所在資料夾的絕對路徑。

## Step 2: Define Time Units
步驟 2：定義時間單位

建立常數以協助將內部時間表示轉換為人類可讀的時數。

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

這些值以微秒為單位，這是 Aspose.Tasks 內部儲存時間的方式。

## Step 3: Create Project Instance
步驟 3：建立 Project 實例

將 Microsoft Project 檔案載入 `Project` 物件。

```java
Project project = new Project(dataDir + "project.mpp");
```

`Project` 建構子會解析 *.mpp* 檔案，並使所有專案資料（包括行事曆）可透過 API 存取。

## Step 4: Retrieve Calendars Information
步驟 4：取得行事曆資訊

取得專案中定義的行事曆集合。

```java
CalendarCollection alCals = project.getCalendars();
```

一個專案可能包含多個行事曆（標準、資源與自訂行事曆）。此集合讓您可以存取每一個行事曆。

## Step 5: Iterate Through Calendars
步驟 5：遍歷行事曆

迴圈處理每個行事曆，顯示其 UID、名稱，以及對應的工作天與時數。

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

內部迴圈會檢查每個 `WeekDay` 物件。若該天被標記為工作日，則會列印出星期類型（Monday、Tuesday…）以及計算出的工作時數。

## Step 6: Display Completion Message
步驟 6：顯示完成訊息

表示提取程序已完成。

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
常見問題與解決方案

| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| **未返回行事曆** | 專案檔可能未包含任何自訂行事曆。 | 確認 *.mpp* 確實定義了行事曆，或在 Microsoft Project 中開啟檢查。 |
| **工作時數不正確** | 時間轉換常數與不同版本的 Project 不相符。 | 若使用較新版本的 Aspose.Tasks，請調整 `OneSec`、`OneMin`、`OneHour`。 |
| **`cal.getName()` 發生 NullPointerException** | 某些行事曆物件可能為 null。 | 在存取屬性前加入 null 檢查（已在示範中說明）。 |

## Frequently Asked Questions
常見問答

**Q: 我可以在其他程式語言中使用 Aspose.Tasks 嗎？**  
A: 可以，Aspose.Tasks 支援多種平台與程式語言，包括 .NET、C++、Python 與 Java。

**Q: Aspose.Tasks 有提供免費試用版嗎？**  
A: 有，您可從 [here](https://releases.aspose.com/) 下載免費試用版。

**Q: 我要如何取得 Aspose.Tasks 的支援？**  
A: 您可在 Aspose.Tasks 社群論壇取得支援，網址在 [here](https://forum.aspose.com/c/tasks/15)。

**Q: 我可以購買臨時授權給 Aspose.Tasks 嗎？**  
A: 可以，臨時授權可於 [here](https://purchase.aspose.com/temporary-license/) 購買。

**Q: 我在哪裡可以找到 Aspose.Tasks 的詳細文件？**  
A: 您可參考文件，網址在 [here](https://reference.aspose.com/tasks/java/)。

## Conclusion
結論

透過上述步驟，**您現在已了解如何使用 Aspose.Tasks 從 MS Project 檔案中提取專案行事曆**資訊，並以 Java 實作。您可以將此邏輯整合至更大的應用程式、自動化報告，或與其他企業系統同步排程。請記住，精通**如何使用 aspose**將為您開啟許多進階的專案管理自動化情境。

---

**最後更新：** 2026-03-27  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}