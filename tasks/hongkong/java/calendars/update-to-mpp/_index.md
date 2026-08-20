---
date: 2026-08-13
description: 了解如何將假期加入日曆、將日曆指派給專案，並使用 Aspose.Tasks for Java 將 MS Project 檔案儲存為 MPP。
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: 在 Aspose.Tasks 中將日曆更新為 MPP 格式
og_description: 將假期加入日曆、指派給專案，並使用 Aspose.Tasks for Java 將排程轉換為 MPP。了解一步一步的自動化流程。
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: 使用 Aspose.Tasks 將假期加入日曆並儲存為 MPP
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: 使用 Aspose.Tasks 將假期加入日曆並儲存為 MPP
url: /zh-hant/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 將假期加入行事曆並儲存為 MPP

## 介紹

在現代專案管理中，您常常需要 **將假期加入行事曆** 檔案、建立 **MS Project 行事曆**，然後以原生 MPP 格式分享排程。無論是整合多個來源的時間線或是遷移舊有資料，程式化產生行事曆都能消除手動錯誤並加快交付速度。本教學將帶您完整了解如何在 MS Project 中建立行事曆、加入假期、**將行事曆指派給專案**，最後使用 Aspose.Tasks Java API **將專案轉換為 MPP**。

## 快速解答
- **本教學涵蓋什麼內容？** 加入假期至行事曆、將其指派給專案，並使用 Aspose.Tasks for Java 將結果儲存為 MPP 檔案。  
- **我需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **需要哪個 Java 版本？** Java 8 或更高（JDK 8+）。  
- **我可以自訂行事曆嗎？** 可以——您可以新增工作時間、例外與假期。  
- **實作需要多長時間？** 基本行事曆約需 10‑15 分鐘。  

## 什麼是「建立 MS Project 行事曆」？

建立 MS Project 行事曆是指定義工作天、工作時數與例外情況，以驅動 Microsoft Project 檔案中的工作排程。使用 Aspose.Tasks，您可以以程式方式建構此行事曆、設定假期，並將其嵌入專案，而無需開啟 MS Project 使用者介面。

## 為何使用 Aspose.Tasks 完成此任務？

您應該使用 Aspose.Tasks，因為它提供完整的 Java 相容性，無需安裝 Microsoft Office，且可直接從程式碼產生並儲存原生 MPP 檔案。此函式庫支援所有行事曆功能，可在任何伺服器環境執行，且能在一秒內處理多達 10,000 個工作的專案。

## 前置條件

1. **Java Development Kit (JDK) 8+** – 確認 `java -version` 顯示 1.8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 [Aspose 官方網站](https://releases.aspose.com/tasks/java/) 下載最新的 JAR。  
3. **IDE** – IntelliJ IDEA、Eclipse 或您偏好的任何編輯器。  
4. **Basic Java knowledge** – 熟悉類別、方法與檔案 I/O。  

## 如何將假期加入行事曆

若要加入假期，您需要建立新的 `Calendar` 物件，取得其 `Exceptions` 集合，並為每個假日日期新增 `DateException` 條目。`DateException` 代表行事曆中的單一天或日期範圍的非工作日。Aspose.Tasks 會將這些日期視為非工作日，確保工作排程繞過已定義的假期。

### 步驟 1：匯入必要的套件

首先，將 Aspose.Tasks 類別與 Java 工具類別匯入至程式範圍內。

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### 步驟 2：設定資料目錄

定義輸入範本與輸出檔案的存放位置。請將佔位符替換為您機器上的實際路徑。

```java
String dataDir = "Your Data Directory";
```

### 步驟 3：定義輸入與輸出檔案名稱

我們將載入現有的 MPP 檔案（或空白專案），並將結果寫入新檔案。

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### 步驟 4：載入專案並新增行事曆

`Project` 類別在記憶體中代表一個 MS Project 檔案，並提供對其行事曆、工作與資源的存取。

從來源檔案建立 `Project` 實例，並新增名為 **「Calendar 1」** 的行事曆。

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### 步驟 5：自訂行事曆（可選）

`Calendar` 物件定義專案排程的工作天、工作時數與例外情況。

若需特定的工作時間、假期或例外，請呼叫您自己的輔助方法。範例使用 `GetTestCalendar` 作為佔位符。

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **專業提示：** 您可以直接操作 `cal1.getWeekDays()` 以設定每週各天的工作時數，或使用 `cal1.getExceptions()` 來 **將假期加入行事曆**。

### 步驟 6：將行事曆指派給專案

告訴專案使用新建立的行事曆進行所有排程計算。

```java
project.set(Prj.CALENDAR, cal1);
```

### 步驟 7：將專案儲存為 MPP

`SaveFileFormat` 列舉指定輸出格式，其中 `Mpp` 代表原生 Microsoft Project 格式。

現在透過使用 `SaveFileFormat.Mpp` 選項儲存，即可 **將專案轉換為 MPP**。

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### 步驟 8：確認成功完成

簡單的主控台訊息會告訴您此程序已順利完成，且未發生錯誤。

```java
System.out.println("Process completed Successfully");
```

## 常見使用情境

- **自動排程產生** 用於重複性專案（例如每週衝刺）。  
- **將舊有 CSV 或 Excel 行事曆** 移植至功能完整的 MS Project 檔案。  
- **伺服器端報表**，透過 Web 服務即時回傳 MPP 檔案。  

## 疑難排解與常見陷阱

| 問題 | 原因 | 解決方案 |
|-------|-------|-----|
| `project.save` 時的 `NullPointerException` | `dataDir` 指向不存在的資料夾 | 確保目錄存在，或以程式方式建立它。 |
| 行事曆未套用至工作 | 工作仍參考預設行事曆 | 在設定 `Prj.CALENDAR` 後，若工作先前已覆寫，亦需更新每個工作之 `Task.CALENDAR`。 |
| 輸出檔案為 0 KB | 缺少寫入權限 | 以適當的檔案系統權限執行 JVM，或選擇可寫入的路徑。 |

## 常見問題

**問：Aspose.Tasks for Java 是否相容於不同版本的 MS Project？**  
答：是的，Aspose.Tasks 支援從 Project 2007 到 Project 2024 的所有 Microsoft Project 檔案格式，涵蓋超過 10 個版本。

**問：我可以依據特定專案需求自訂行事曆嗎？**  
答：當然可以。您可以定義工作天、設定自訂工作週、加入假期，甚至在同一專案檔案中建立多個行事曆。

**問：Aspose.Tasks for Java 是否提供疑難排解與協助支援？**  
答：是的，您可在 Aspose.Tasks 社群論壇取得協助 [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)。

**問：Aspose.Tasks for Java 是否提供免費試用？**  
答：是的，提供功能完整的免費試用版 [Aspose.Tasks free trial](https://releases.aspose.com/)。

**問：如何取得 Aspose.Tasks for Java 的臨時授權？**  
答：可透過 Aspose 官方網站申請臨時授權 [Aspose temporary license request](https://purchase.aspose.com/temporary-license/)。

---

**最後更新：** 2026-08-13  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.Tasks for Java 為專案新增行事曆](/tasks/java/calendars/create/)
- [如何在 MS Project 行事曆中定義工作日 – Aspose.Tasks Java](/tasks/java/calendars/)
- [使用 Aspose.Tasks for Java 建立自訂行事曆例外](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}