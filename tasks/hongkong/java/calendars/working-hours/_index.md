---
date: 2025-12-05
description: 學習如何透過使用 Aspose.Tasks for Java 從 MS Project 行事曆提取工作時數，以確定工作天數並計算任務持續時間。
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 確定工作天數與工作時數
url: /zh-hant/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 確定工作日與工作時間（使用 Aspose.Tasks）

## 介紹
管理專案行事曆是成功專案規劃的核心部分。在本教學中，您將 **確定任何工作項目的工作日**，並使用 Aspose.Tasks for Java 從 MS Project 行事曆 **擷取工作時間**。完成本指南後，您將能夠 **計算工作項目持續時間**、自訂工作時間，並可靠地 **載入 MPP 檔案** 以取得所需資料。

## 快速解答
- **「確定工作日」是什麼意思？** 它指的是識別給定工作項目被視為工作日的行事曆日期。  
- **我應該使用哪個函式庫？** Aspose.Tasks for Java 提供完整功能的 API 以處理 MS Project 檔案。  
- **實作需要多長時間？** 基本擷取通常需要 10–15 分鐘。  
- **我需要授權嗎？** 提供免費試用版；正式使用需購買商業授權。  
- **我可以自訂工作時間嗎？** 可以 – 您可以修改行事曆、加入假期，並設定自訂的工作時間範圍。

## 什麼是「確定工作日」？
當工作項目排程時，專案行事曆會定義哪些日子是工作日，哪些是非工作日（週末、假期）。確定工作日即是查詢該行事曆，以確切了解何時可以進行工作，這對於精確的 **計算工作項目持續時間** 計算至關重要。

## 為什麼使用 Aspose.Tasks 取得工作時間？
- **不需要 Microsoft Project** – 可在任何平台上處理 .MPP 檔案。  
- **完整的行事曆支援** – 包括預設、資源與工作項目行事曆。  
- **高效能** – 快速處理大型專案。  
- **豐富的文件** – 範例與 API 參考隨手可得。

## 前置條件
在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 版本 8 或以上。  
2. **Aspose.Tasks for Java** – 從 [here](https://releases.aspose.com/tasks/java/) 下載最新的 JAR。  
3. 基本的 Java 程式設計知識。  

## 匯入套件
首先，匯入 Aspose.Tasks 的核心命名空間：

```java
import com.aspose.tasks.*;
```

## 步驟 1：載入 MPP 檔案
載入您的專案檔案（**載入 mpp 檔案** 步驟），以便操作其行事曆：

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## 步驟 2：取得工作項目與行事曆資訊
選取您要分析的工作項目，並取得其關聯的行事曆。這裡會 **取得工作項目的工作時間**：

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## 步驟 3：定義開始與結束日期
設定您想要 **確定工作日** 的時間範圍：

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## 步驟 4：遍歷日期
遍歷工作項目持續期間的每一天。若需要，此迴圈可協助我們稍後 **自訂工作時間**：

```java
java.util.Calendar tempDate = calStartDate;
```

## 步驟 5：計算持續時間
在迭代過程中，我們會檢查每一天是否為工作日，累加工作小時，最後計算工作項目的持續時間（以分鐘、時數與天數表示）：

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **工作項目返回 `null` 行事曆** | 確保該工作項目已指派行事曆；否則會繼承專案的預設行事曆。 |
| **因假期導致的持續時間不正確** | 確認假期已在工作項目的行事曆或專案的基礎行事曆中定義。 |
| **時區不匹配** | 如有需要，使用 `java.util.TimeZone` 使行事曆的時區與系統對齊。 |

## 常見問答
### Q：Aspose.Tasks for Java 能處理複雜的專案結構嗎？
A：是的，Aspose.Tasks for Java 提供完整支援，能處理包括工作項目、資源與行事曆在內的複雜專案結構。

### Q：Aspose.Tasks for Java 與不同版本的 MS Project 相容嗎？
A：當然，Aspose.Tasks for Java 支援多個版本的 MS Project，確保在不同環境中的相容性。

### Q：我可以在專案行事曆中自訂工作時間與假期嗎？
A：是的，您可以使用 Aspose.Tasks for Java API，輕鬆依照專案需求自訂工作時間與假期。

### Q：Aspose.Tasks for Java 是否提供支援與文件？
A：是的，Aspose.Tasks for Java 提供豐富的文件與專屬支援論壇，協助開發者有效使用其功能。

### Q：是否有 Aspose.Tasks for Java 的試用版？
A：是的，您可從 [here](https://releases.aspose.com/) 取得 Aspose.Tasks for Java 的免費試用版。

## 結論
本指南示範了如何使用 Aspose.Tasks for Java 從 MS Project 行事曆 **確定工作日**、**取得工作時間**，以及 **計算工作項目持續時間**。依照上述步驟，您即可自動化排程分析、客製化行事曆，並確保專案計畫的準確與即時更新。

---

**最後更新：** 2025-12-05  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}