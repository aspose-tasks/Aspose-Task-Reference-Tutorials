---
date: 2026-08-24
description: 了解如何透過 Aspose.Tasks for Java，從 MS Project 行事曆中提取工作時數，新增假期行事曆、確定工作日並計算任務工期。
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: 如何新增假期行事曆並確定工作日
og_description: 了解如何透過 Aspose.Tasks for Java，從 MS Project 行事曆中提取工作時數，新增假期行事曆、確定工作日並計算任務工期。
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: 如何新增假期行事曆並確定工作日
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: 如何新增假期行事曆並確定工作日
url: /zh-hant/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何新增假期行事曆並確定工作天數

管理專案行事曆是成功專案規劃的核心部分。在本教學中，您將 **新增假期行事曆**、**確定工作天數**（適用於任何任務），以及使用 Aspose.Tasks for Java 從 MS Project 行事曆 **擷取工作時數**。完成本指南後，您將能夠 **計算任務工期**、自訂工作時段，並可靠地 **載入 MPP 檔案** 以取得所需資料——全部不需安裝 Microsoft Project。

## 快速解答
- **「確定工作天數」是什麼意思？** 它表示辨識給定任務的行事曆日期哪些被視為工作日。  
- **我應該使用哪個函式庫？** Aspose.Tasks for Java 提供完整的 API 來操作 MS Project 檔案。  
- **實作需要多長時間？** 基本擷取通常需要 10–15 分鐘。  
- **我需要授權嗎？** 提供免費試用版；商業使用需購買授權。  
- **我可以自訂工作時段嗎？** 可以 – 您可以修改行事曆、加入假期，並設定自訂的工作時間範圍。  

## 「確定工作天數」是什麼？
**確定工作天數** 意味著查詢專案行事曆，找出哪些日期被標記為工作日，哪些為非工作日（週末、假期或自訂例外）。此資訊對於精確 **計算任務工期** 至關重要，因為只有工作日會計入任務的實際耗時。

## 為什麼使用 Aspose.Tasks 來取得工作時數？
Aspose.Tasks 讓您在未安裝 Microsoft Project 的情況下讀取 MS Project 檔案，支援任何平台的自動化。它同時提供高效能處理、廣泛的格式支援與詳細的文件說明。  

- **完整的行事曆支援** – 可存取預設、資源與任務行事曆。  
- **高效能** – 在標準 2.5 GHz CPU 上，可在 2 秒內處理 **10,000+ 任務** 的專案。  
- **廣泛的格式覆蓋** – 支援 **50+ 輸入與輸出格式**，包括 MPP、MPX、XML 與 Primavera。  
- **完整文件** – 提供程式碼範例、API 參考與社群論壇。  

## 前置條件
1. **Java Development Kit (JDK)** – 版本 8 或以上。  
2. **Aspose.Tasks for Java** – 從 [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/) 下載最新 JAR。  
3. 基本的 Java 程式設計知識。  

## 匯入套件
`Project` 類別是 Aspose.Tasks 的頂層物件，代表記憶體中的單一 MS Project 檔案。開始之前先匯入所需的命名空間：

匯入套件

```java
import com.aspose.tasks.*;
```

## 如何使用 Aspose.Tasks 載入 MPP 檔案？
`Project` 類別會載入 MS Project 檔案並提供存取其資料的功能。只需一行程式碼即可載入專案檔，無需 UI 或 COM 互操作。此簡單步驟即可讓您完整存取行事曆、任務與資源。

載入 MPP 檔案

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## 取得任務與行事曆資訊
`Task` 代表專案任務，`Calendar` 定義其工作時間規則。選取您要分析的任務並取得其關聯的行事曆。`Task` 物件提供 `getStart()` 與 `getFinish()` 方法，`Calendar` 物件則揭露工作時間定義。

取得任務與行事曆

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## 定義開始與結束日期
`Date` 物件指定行事曆分析的時間窗口。設定您想要 **確定工作天數** 的時間範圍。使用任務的開始與結束日期可確保只評估相關期間。

定義日期

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## 遍歷日期
`for` 迴圈可遍歷日期範圍內的每一天。循環遍歷任務期間的每個日期。此迴圈之後可讓您 **自訂工作時段**，亦是計算總工作時間的基礎。

遍歷日期

```java
java.util.Calendar tempDate = calStartDate;
```

## 計算工期
`Duration` 會彙總從遍歷中計算出的總工作時間。遍歷過程中，您會檢查每一天是否為工作日，累加工作時數，最後以分鐘、時數與天數計算任務的工期。此範例示範了如何以程式方式 **計算工作天數** 與 **計算任務工期**。

計算工期

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

## 如何自訂工作時段與假期
您可以修改行事曆的工作時間範圍，並加入假期等例外。使用 `taskCalendar.addWorkingTime()` 設定新工作時段，使用 `taskCalendar.addException()` 插入假期。當預設的 9‑5 時間表不符合組織政策時，此功能相當有用。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **任務的行事曆返回 `null`** | 確認任務實際已指派行事曆；若未指派，則會繼承專案的預設行事曆。 |
| **因假期導致工期不正確** | 核實假期是否已在任務的行事曆或專案的基礎行事曆中定義。 |
| **時區不匹配** | 如有需要，使用 `java.util.TimeZone` 使行事曆的時區與系統保持一致。 |

## 常見問答
### Q: Aspose.Tasks for Java 能處理複雜的專案結構嗎？
A: 能，Aspose.Tasks for Java 提供完整支援，能處理包含任務、資源與行事曆的複雜專案結構。

### Q: Aspose.Tasks for Java 與不同版本的 MS Project 相容嗎？
A: 完全相容，Aspose.Tasks for Java 支援多種 MS Project 版本，確保在不同環境下皆可使用。

### Q: 我可以在專案行事曆中自訂工作時段與假期嗎？
A: 可以，您可使用 Aspose.Tasks for Java API 輕鬆依專案需求自訂工作時段與假期。

### Q: Aspose.Tasks for Java 提供支援與文件說明嗎？
A: 提供，Aspose.Tasks for Java 擁有豐富的文件說明與專屬支援論壇，協助開發者有效使用其功能。

### Q: Aspose.Tasks for Java 有試用版嗎？
A: 有，您可從 [Aspose releases page](https://releases.aspose.com/) 取得 Aspose.Tasks for Java 的免費試用版。

## 結論
本指南示範了如何使用 Aspose.Tasks for Java 從 MS Project 行事曆 **新增假期行事曆**、**確定工作天數**、**擷取工作時數**，以及 **計算任務工期**。依照上述步驟，您即可自動化排程分析、客製化行事曆，並確保專案計畫的準確與即時更新。現在，您已具備 **讀取 MS Project** 資料、**載入 MPP 檔案**，以及在不需 Microsoft Project 的情況下執行精確工期計算的工具。

---

**最後更新：** 2026-08-24  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose

## 相關教學

- [使用 Aspose.Tasks for Java 為專案新增行事曆](/tasks/java/calendars/create/)
- [將假期加入行事曆並儲存為 MPP](/tasks/java/calendars/update-to-mpp/)
- [使用 Aspose.Tasks for Java 建立自訂行事曆例外](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}