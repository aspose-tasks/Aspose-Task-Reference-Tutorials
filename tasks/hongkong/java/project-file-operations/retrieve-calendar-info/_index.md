---
title: 在 Aspose.Tasks 中檢索 MS 專案日曆信息
linktitle: 在 Aspose.Tasks 中檢索日曆信息
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 擷取 MS Project 行事曆資訊。以程式設計方式存取日曆詳細資訊的逐步指南。
weight: 14
url: /zh-hant/java/project-file-operations/retrieve-calendar-info/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中檢索 MS 專案日曆信息

## 介紹
在本教學中，我們將探討如何使用 Aspose.Tasks for Java 函式庫從 Microsoft Project 檔案中擷取行事曆資訊。 Aspose.Tasks 提供了強大的功能來操作專案數據，包括存取日曆詳細信息，例如工作日和時間。
## 先決條件
在我們開始之前，請確保您具備以下條件：
- Java 程式設計的基礎知識。
- 您的系統上安裝了 Java 開發工具包 (JDK)。
-  Java 函式庫的 Aspose.Tasks。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/java/).
## 導入包
首先，您需要在 Java 程式碼中匯入必要的套件才能使用 Aspose.Tasks 功能。
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
現在讓我們將提供的範例分解為多個步驟以便更好地理解。
## 第1步：設定資料目錄
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`以及專案檔案目錄的路徑。
## 第 2 步：定義時間單位
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
這些常數表示以微秒為單位的時間單位。
## 步驟3：建立專案實例
```java
Project project = new Project(dataDir + "project.mpp");
```
這一行建立了一個實例`Project`類，使用專案文件的路徑對其進行初始化（`project.mpp`）。
## 第 4 步：檢索日曆信息
```java
CalendarCollection alCals = project.getCalendars();
```
在這裡，我們檢索項目文件中存在的日曆集合。
## 第 5 步：迭代日曆
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        //日曆資訊
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        //迭代工作日
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); //時間（以毫秒為單位）
            double time = ts / (OneHour); //轉換為小時
            if (wd.getDayWorking()) {
                //顯示工作日和時間
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
此循環遍歷每個日曆並列印其 UID、名稱、工作日以及相應的工作時間。
## 第 6 步：顯示完成訊息
```java
System.out.println("Process completed Successfully");
```
最後，將顯示一條訊息，指示該過程已完成。
## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 從 MS Project 檔案檢索日曆資訊。透過執行這些步驟，您可以有效地存取和操作 Java 應用程式中的專案資料。

## 常見問題解答
### Q：我可以將 Aspose.Tasks 與其他程式語言一起使用嗎？
答：是的，Aspose.Tasks支援多種平台和程式語言，包括.NET、C++、Python 和 Java。
### Q：Aspose.Tasks 是否有免費試用版？
答：是的，您可以從以下位置下載免費試用版：[這裡](https://releases.aspose.com/).
### Q：如何獲得 Aspose.Tasks 的支援？
答：您可以從 Aspose.Tasks 社群論壇獲得支持[這裡](https://forum.aspose.com/c/tasks/15).
### Q：我可以購買 Aspose.Tasks 的臨時授權嗎？
答：是的，可以購買臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### Q：在哪裡可以找到 Aspose.Tasks 的詳細文件？
答：可以參考文檔[這裡](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
