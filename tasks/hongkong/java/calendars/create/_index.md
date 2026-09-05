---
date: 2026-08-03
description: 了解如何使用 Aspose.Tasks for Java 建立 MS Project 行事曆、將行事曆加入專案，並將專案儲存為 XML。
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: 使用 Aspose.Tasks 將行事曆加入專案
og_description: 使用 Aspose.Tasks for Java 程式化建立 MS Project 行事曆。快速新增行事曆、客製化排程，並在數分鐘內匯出為
  XML。
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: 使用 Aspose.Tasks for Java 建立 MS Project 行事曆
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: 使用 Aspose.Tasks for Java 建立 MS Project 行事曆
url: /zh-hant/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 建立 ms project 行事曆

## 簡介
在現代專案管理工作流程中，程式化 **建立 ms project 行事曆** 的能力可以節省大量手動編輯的時間。Aspose.Tasks for Java 為您提供乾淨、型別安全的 API，讓您在不開啟桌面客戶端的情況下操作 Microsoft Project 檔案。在本教學中，您將學會如何新增行事曆、如何建立 MS Project 行事曆，以及如何將專案儲存為 XML——只需幾行 Java 程式碼。

## 快速解答
- **「create ms project calendar」是什麼意思？**  
  它表示透過程式碼在 Microsoft Project 檔案中插入一個新的工作時間定義（行事曆）。  
- **哪個函式庫負責此功能？**  
  Aspose.Tasks for Java 提供 `Calendar` 類別與 `Project` 容器來管理行事曆。  
- **我需要授權嗎？**  
  測試時使用臨時評估授權即可；正式上線需購買正式授權。  
- **可以將檔案儲存為 XML 嗎？**  
  可以——使用 `SaveFileFormat.Xml` 即可匯出專案為 XML 檔案。  
- **前置條件是什麼？**  
  Java JDK 8 以上以及 Aspose.Tasks for Java 的 JAR 必須在 classpath 中。

## 什麼是建立 ms project 行事曆？
建立 MS Project 行事曆是指以程式方式將新的行事曆定義加入專案檔案，設定工作日、例外日與每日工作時數，然後將該行事曆指派給工作、資源或整個專案，使排程計算遵循所定義的工作時間。

## 為什麼使用 Aspose.Tasks for Java 來為專案新增行事曆？
您應該使用 Aspose.Tasks for Java，因為它提供完整的型別安全 API，無需安裝 Microsoft Project，即可支援所有主要的 Project 版本（2007‑2021，超過 5 個版本），且能匯出為 XML、MPP 以及 **10+** 其他格式，讓您在任何伺服器上自動大量建立行事曆。

## 先決條件
- **Java Development Kit (JDK) 8 或更新版本** 已安裝並設定。  
- **Aspose.Tasks for Java** 函式庫——從[官方網站](https://releases.aspose.com/tasks/java/)下載，並將 JAR 加入專案的 classpath。  
- 您慣用的 IDE 或建置工具（Maven/Gradle）。

## 逐步指南

### 步驟 1：匯入所需的 Aspose.Tasks 套件
首先，將 Aspose.Tasks 類別匯入作用域，以便操作專案與行事曆。

```java
import com.aspose.tasks.*;
```

### 步驟 2：設定資料目錄路徑
定義產生的專案檔案要寫入的位置。請將佔位符替換為您機器上的絕對或相對路徑。

```java
String dataDir = "Your Data Directory";
```

### 步驟 3：建立新的 Project 實例
`Project` 是代表 Microsoft Project 檔案於記憶體中的核心類別。

```java
Project prj = new Project();
```

### 步驟 4：定義要新增的行事曆
`Calendar` 定義了專案的工作日、例外日與工作時間排程。

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **專業提示：** 新增行事曆後，您可以使用 `cal1.getWeekDays().add(...)` 自訂工作日，並透過 `cal1.getBaseCalendar().setWorkingTime(...)` 設定每日工作時數。

### 步驟 5：儲存專案（以 XML 格式儲存專案）
`SaveFileFormat.Xml` 告訴 Aspose.Tasks 以 XML 格式寫入專案。

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### 步驟 6：顯示完成訊息
讓使用者知道操作已成功完成。

```java
System.out.println("Process completed Successfully");
```

透過這六個簡潔步驟，您已成功 **將行事曆新增至專案**，並將結果儲存為 XML 檔案。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|-------|--------|-----|
| **`NullPointerException` on `prj.getCalendars()`** | Project 物件未正確初始化。 | 確保在存取行事曆前已呼叫 `new Project()`。 |
| **儲存時找不到檔案** | `dataDir` 指向不存在的資料夾。 | 先建立該目錄或使用絕對路徑。 |
| **行事曆名稱顯示為「no info」** | 範例中使用了佔位名稱。 | 請替換為能反映排程的有意義名稱（例如「US Holiday Calendar」）。 |
| **儲存的 XML 無法在 MS Project 開啟** | 使用了過時的 Aspose.Tasks 版本。 | 升級至最新的 Aspose.Tasks for Java 版本。 |

## 常見問題

**Q: Aspose.Tasks 能處理具有多個例外的複雜行事曆嗎？**  
A: 可以——新增行事曆後，您可以使用 `WeekDay` 與 `Exception` 類別定義例外、工作時數與非工作日。

**Q: 可以將新行事曆指派給特定工作嗎？**  
A: 當然可以。透過 `prj.getRootTask().getChildren().add("Task Name")` 取得工作，然後使用 `task.set(Tsk.CALENDAR, cal3);` 進行指派。

**Q: 函式庫是否支援以其他格式（如 MPP）儲存？**  
A: 支援。視需求將 `SaveFileFormat.Xml` 替換為 `SaveFileFormat.Mpp` 或 `SaveFileFormat.P6`；Aspose.Tasks 支援 **12** 種輸出格式。

**Q: 開發建置是否需要授權？**  
A: 測試時使用臨時評估授權即可；正式部署則需購買正式授權。

**Q: 若遇到問題，該向哪裡尋求協助？**  
A: Aspose.Tasks 社群論壇是極佳的資源：[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

---

**最後更新：** 2026-08-03  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何在 MS Project 行事曆中定義工作日 – Aspose.Tasks Java](/tasks/java/calendars/)
- [如何使用 Aspose.Tasks 設定 Java 專案行事曆](/tasks/java/calendars/properties/)
- [使用 Aspose.Tasks for Java 建立自訂行事曆例外](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}