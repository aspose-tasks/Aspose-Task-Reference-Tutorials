---
date: 2025-12-20
description: 學習如何使用 Aspose.Tasks 透過 Java 從 Microsoft Project 檔案中提取專案行事曆詳細資訊。逐步說明與程式碼範例。
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

## 介紹
在本教學中，**您將學會如何使用 Aspose.Tasks** 以程式方式從 Microsoft Project 檔案中取得行事曆資訊。取得工作日、工時與例外情況等行事曆資料，對於需要**擷取專案行事曆**以進行報表、整合或自訂排程邏輯時相當重要。讓我們一步一步完成整個流程。

## 快速回答
- **本教學使用哪個函式庫？** Aspose.Tasks for Java。  
- **主要關鍵字是什麼？** *how to use aspose.tasks*。  
- **可以抽取什麼資訊？** 專案行事曆，包括工作日與工時。  
- **需要授權嗎？** 提供免費試用版；正式環境需購買授權。  
- **支援的 Java 版本？** Java 8 以上。

## 為什麼要抽取專案行事曆資訊？
專案行事曆決定工作任務的日期、資源分配與整體時間線計算。抽取這些資料您可以：
- 產生反映實際工作排程的自訂報表。  
- 將 Microsoft Project 時間線與外部系統（ERP、BI 等）同步。  
- 透過程式化修改行事曆設定，執行假設分析。

## 前置條件
在開始之前，請確保您已具備：

- 基本的 Java 程式開發知識。  
- 已在系統上安裝 Java Development Kit (JDK)。  
- Aspose.Tasks for Java 函式庫。您可從 [此處](https://releases.aspose.com/tasks/java/) 下載。

## 匯入套件
首先，將必要的 Aspose.Tasks 類別匯入您的 Java 專案。

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## 步驟 1：設定資料目錄
定義放置 *.mpp* 檔案的資料夾路徑。

```java
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為 **project.mpp** 所在資料夾的絕對路徑。

## 步驟 2：定義時間單位
建立常數，以協助將內部時間表示轉換為可讀的工時。

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

這些值以微秒為單位，正是 Aspose.Tasks 內部儲存時間的方式。

## 步驟 3：建立 Project 實例
將 Microsoft Project 檔案載入為 `Project` 物件。

```java
Project project = new Project(dataDir + "project.mpp");
```

`Project` 建構子會解析 *.mpp* 檔案，並讓您透過 API 存取所有專案資料，包括行事曆。

## 步驟 4：取得行事曆資訊
取得專案中定義的行事曆集合。

```java
CalendarCollection alCals = project.getCalendars();
```

一個專案可能包含多個行事曆（標準、資源與自訂行事曆）。此集合讓您可以存取每一個行事曆。

## 步驟 5：遍歷行事曆
逐一迭代每個行事曆，顯示其 UID、名稱以及對應的工作日與工時。

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

內部迴圈會檢查每個 `WeekDay` 物件。若該日被標記為工作日，則會印出星期類型（Monday、Tuesday…）以及計算出的工作時數。

## 步驟 6：顯示完成訊息
表示抽取程序已結束。

```java
System.out.println("Process completed Successfully");
```

## 結論
透過上述步驟，**您現在已掌握如何使用 Aspose.Tasks 以 Java 從 MS Project 檔案中抽取專案行事曆資訊**。您可以將此邏輯整合至更大型的應用程式、自動化報表，或與其他企業系統同步排程。

## 常見問與答

**Q: 可以在其他程式語言中使用 Aspose.Tasks 嗎？**  
A: 可以，Aspose.Tasks 支援多平台與程式語言，包括 .NET、C++、Python 與 Java。

**Q: Aspose.Tasks 有提供免費試用版嗎？**  
A: 有，您可從 [此處](https://releases.aspose.com/) 下載免費試用版。

**Q: 如何取得 Aspose.Tasks 的支援？**  
A: 您可在 Aspose.Tasks 社群論壇 [此處](https://forum.aspose.com/c/tasks/15) 取得支援。

**Q: 可以購買臨時授權嗎？**  
A: 可以，臨時授權可於 [此處](https://purchase.aspose.com/temporary-license/) 購買。

**Q: 哪裡可以找到 Aspose.Tasks 的詳細文件？**  
A: 請參考文件說明 [此處](https://reference.aspose.com/tasks/java/)。

---

**最後更新：** 2025-12-20  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}