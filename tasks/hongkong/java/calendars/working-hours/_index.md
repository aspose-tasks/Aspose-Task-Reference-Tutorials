---
date: 2026-02-05
description: 學習如何透過 Aspose.Tasks for Java 從 MS Project 行事曆中提取工作時數，以確定工作天數並計算任務工期。
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 確定工作天與工作時數
url: /zh-hant/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 確定工作日與工作時間

## 介紹
管理專案行事曆是成功專案規劃的核心工作之一。在本教學中，您將使用 Aspose.Tasks for Java **確定任何工作項目的工作日**，並 **從 MS Project 行事曆中擷取工作時間**。完成本指南後，您將能夠 **計算工作項目工期**、自訂工作時間，並可靠地 **載入 MPP 檔案** 以取得所需資料。您還會看到如何在未安裝 Microsoft Project 的情況下 **讀取 MS Project** 檔案，讓自動化在任何平台上皆可實現。

## 快速答覆
- **「確定工作日」是什麼意思？** 指的是辨識給定工作項目在行事曆中被視為工作日的日期。  
- **應該使用哪個函式庫？** Aspose.Tasks for Java 提供完整的 API 來操作 MS Project 檔案。  
- **實作需要多長時間？** 基本擷取通常只需 10–15 分鐘。  
- **需要授權嗎？** 提供免費試用版；正式環境需購買商業授權。  
- **可以自訂工作時間嗎？** 可以 – 您可以修改行事曆、加入假日，並設定自訂的工作時間區段。  

## 什麼是「確定工作日」？
當工作項目排程時，專案行事曆會定義哪些日子是工作日、哪些是非工作日（週末、假日）。確定工作日即是查詢該行事曆，以確切知道何時可以進行工作，這對於正確 **計算工作項目工期** 至關重要。

## 為什麼使用 Aspose.Tasks 取得工作時間？
- **不需 Microsoft Project** – 可直接在 Java 程式碼中讀取 MS Project 檔案。  
- **完整的行事曆支援** – 包含預設行事曆、資源行事曆與工作項目行事曆。  
- **高效能** – 能快速處理大型專案。  
- **豐富文件** – 範例與 API 參考隨手可得。  

## 前置條件
在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 版本 8 或以上。  
2. **Aspose.Tasks for Java** – 從 [此處](https://releases.aspose.com/tasks/java/) 下載最新 JAR。  
3. 基本的 Java 程式開發知識。  

## 匯入套件
首先，匯入 Aspose.Tasks 的核心命名空間：

```java
import com.aspose.tasks.*;
```

## 如何使用 Aspose.Tasks 載入 MPP 檔案？
載入專案檔案是進行任何行事曆分析的第一步。API 讓您只需一行程式碼即可 **載入 MPP 檔案**，無需使用 MS Project UI。

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## 取得工作項目與行事曆資訊
選取您想分析的工作項目，並取得其關聯的行事曆。這裡我們 **擷取工作項目的工作時間**：

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## 定義開始與結束日期
設定您想 **確定工作日** 的時間範圍。使用工作項目的開始與結束日期，可確保只評估相關期間。

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## 逐日遍歷
遍歷工作項目期間的每一天。此迴圈稍後可用於 **自訂工作時間**（如有需要）：

```java
java.util.Calendar tempDate = calStartDate;
```

## 計算工期
在遍歷過程中，我們會檢查每一天是否為工作日，累加工作小時，最終計算出工作項目的分鐘、時數與天數。此步驟示範如何以程式方式 **計算工作日** 與 **計算工作項目工期**。

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

## 如何自訂工作時間與假日
Aspose.Tasks 允許您修改行事曆的工作時間區段，並加入例外（如假日）。您可以呼叫 `taskCalendar.addWorkingTime()` 或 `taskCalendar.addException()`，依照組織政策調整排程。當預設的 9‑5 工作制不符合實際情況時，這非常有用。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **工作項目返回 `null` 行事曆** | 確認該工作項目確實指派了行事曆；若未指派，則會繼承專案的預設行事曆。 |
| **因假日導致工期不正確** | 檢查假日是否已在工作項目的行事曆或專案的基礎行事曆中定義。 |
| **時區不匹配** | 如有需要，使用 `java.util.TimeZone` 使行事曆的時區與系統保持一致。 |

## 常見問答
### Q: Aspose.Tasks for Java 能處理複雜的專案結構嗎？
A: 能，Aspose.Tasks for Java 提供完整支援，能處理包含工作項目、資源與行事曆在內的複雜專案結構。

### Q: Aspose.Tasks for Java 與不同版本的 MS Project 相容嗎？
A: 完全相容，Aspose.Tasks for Java 支援多種版本的 MS Project，確保在不同環境下皆可使用。

### Q: 我可以在專案行事曆中自訂工作時間與假日嗎？
A: 可以，您可透過 Aspose.Tasks for Java API 輕鬆依專案需求自訂工作時間與假日。

### Q: Aspose.Tasks for Java 提供支援與文件嗎？
A: 提供，Aspose.Tasks for Java 擁有豐富的文件與專屬支援論壇，協助開發者有效使用其功能。

### Q: 有提供 Aspose.Tasks for Java 的試用版嗎？
A: 有，您可從 [此處](https://releases.aspose.com/) 取得 Aspose.Tasks for Java 的免費試用版。

## 結論
本指南示範了如何使用 Aspose.Tasks for Java 從 MS Project 行事曆 **確定工作日**、**取得工作時間**，以及 **計算工作項目工期**。依照上述步驟，您即可自動化排程分析、客製化行事曆，並確保專案計畫的準確與即時更新。現在，您已具備 **讀取 MS Project** 資料、**載入 MPP 檔案**，以及在不依賴 Microsoft Project 的情況下執行精確工期計算的工具。

---

**最後更新：** 2026-02-05  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}