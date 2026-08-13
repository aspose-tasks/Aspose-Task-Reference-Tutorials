---
date: 2026-08-13
description: 了解如何使用 Aspose.Tasks 於 Java 中建立標準的 MS Project 行事曆。本步驟指南將示範如何建立標準的 MS Project
  行事曆、將其設為預設，並儲存檔案。
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: 在 Aspose.Tasks 中建立標準行事曆
og_description: 如何在 Java 中使用 Aspose.Tasks 建立行事曆。了解如何快速建立標準的 MS Project 行事曆、將其設為預設，並在數分鐘內儲存專案檔案。
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: 如何建立行事曆 – 在 Aspose.Tasks 中建立標準行事曆
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: 如何建立行事曆 – 在 Aspose.Tasks 中建立標準行事曆
url: /zh-hant/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何建立行事曆 – 在 Aspose.Tasks 中建立標準行事曆

## 介紹
在本教學中，您將學習**如何建立行事曆**物件，為 Microsoft Project 檔案使用 Aspose.Tasks for Java 函式庫。我們將逐步說明如何建立標準的 MS Project 行事曆、將其設為預設（標準）行事曆，並儲存專案檔。完成本指南後，您即可將行事曆建立功能整合至任何基於 Java 的專案管理解決方案。

## 快速解答
- **「標準行事曆」是什麼意思？** 它是套用於未指派自訂行事曆之工作項目的預設工作時間定義。  
- **需要哪個函式庫？** Aspose.Tasks for Java – 一個純 Java API，無需安裝 Microsoft Project 即可運作。  
- **我需要授權嗎？** 免費試用版可用於開發；正式上線則需商業授權。  
- **產生的檔案格式為何？** 基於 XML 的 Microsoft Project 檔案（`.xml`）。  
- **實作需要多長時間？** 基本行事曆設定約需 5‑10 分鐘。

## Microsoft Project 中的標準行事曆是什麼？
標準行事曆定義了專案的預設工作日與工作時間，通常為週一至週五，上午 8 時至下午 5 時。當您新增標準行事曆時，未指派自訂行事曆的任何工作項目都會繼承此工作時間，確保整個專案的排程一致。

## 為什麼使用 Aspose.Tasks 來建立行事曆？
Aspose.Tasks for Java 支援 **超過 50 種輸入與輸出格式**，且可在不將整個檔案載入記憶體的情況下處理多達 **10,000 個工作項目** 的專案。這個純 Java 函式庫讓您能在伺服器、CI 流程或任何 Java 應用程式上自動化 Project 檔案的建立，免除安裝授權版 Microsoft Project 的需求。

## 前置條件
在開始之前，請確保以下條件已備妥：

### Java Development Kit (JDK) 安裝
從 Oracle 官方網站或 OpenJDK 發行版下載並安裝最新的 JDK。

### Aspose.Tasks for Java 函式庫
從[下載頁面](https://releases.aspose.com/tasks/java/)下載函式庫，並將 JAR 檔加入專案的 classpath。

## 匯入套件
本教學僅需匯入以下一個套件：

```java
import com.aspose.tasks.*;
```

## 步驟說明

### 步驟 1：設定資料目錄
定義產生的專案檔案要儲存的位置。

```java
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為您機器上的絕對路徑（例如 `C:/Projects/Output/`）。

### 步驟 2：建立專案實例
`Project` 是 Aspose.Tasks 的頂層物件，代表記憶體中的單一 Microsoft Project 檔案。建立它的實例即可取得行事曆、工作項目、資源及其他專案資料的容器。

```java
Project project = new Project();
```

### 步驟 3：定義並設為標準行事曆
`Calendar` 是用來建模工作時間表的類別。新增一個名為 **「My Cal」** 的行事曆，並呼叫 `makeStandardCalendar`，即可將其提升為整個專案的預設行事曆。

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **小技巧：** `makeStandardCalendar` 方法會自動將提供的行事曆標記為專案的預設行事曆，這正是您想要 **加入標準行事曆** 功能時所需要的。

### 步驟 4：儲存專案
SaveFileFormat 是一個列舉，用於指定儲存專案時的檔案格式。  
將專案（包括新行事曆）持久化為 XML 檔案。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

如果您想使用其他 Project 版本，可變更檔名或格式（例如 `SaveFileFormat.Pp`）。

### 步驟 5：顯示完成訊息
提供一個視覺提示，表示流程已順利完成且未發生錯誤。

```java
System.out.println("Process completed Successfully");
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|-------|-------|-----|
| **找不到檔案** | `dataDir` 指向不存在的資料夾 | 建立該資料夾或改用絕對路徑 |
| **授權例外** | 在正式環境中未使用有效的 Aspose.Tasks 授權執行 | 透過 `License license = new License(); license.setLicense("Aspose.Tasks.lic");` 套用授權檔案 |
| **行事曆為空** | 忘記加入工作時間定義 | 若需要自訂時段，可使用 `cal1.getWeekDays().add(WeekDay.DayType.Monday)` 等方法 |

## 常見問答

**Q: Aspose.Tasks 是否相容於所有版本的 Microsoft Project？**  
A: 是，Aspose.Tasks 支援廣泛的 Microsoft Project 版本，從 2000 版一直到最新發行版。

**Q: 我可以進一步自訂行事曆設定嗎？**  
A: 當然可以！您可以使用 `WeekDay` 與 `WorkingTime` 類別修改工作日、加入例外，並定義特定的工作時間。

**Q: Aspose.Tasks 適合企業級應用嗎？**  
A: 當然。此函式庫設計用於高效能、可擴充的環境，並提供對大型 Project 檔案的完整支援。

**Q: Aspose.Tasks 是否提供開發者技術支援？**  
A: 有，Aspose 提供專屬論壇、票務支援以及豐富的文件，協助您快速解決各種問題。

**Q: 我可以在購買前先試用 Aspose.Tasks 嗎？**  
A: 可以，您可在[網站](https://purchase.aspose.com/buy)上取得免費試用版，讓您在正式購買前評估所有功能。

**最後更新：** 2026-08-13  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相關教學

- [使用 Aspose.Tasks for Java 為專案新增行事曆](/tasks/java/calendars/create/)
- [如何使用 Aspose.Tasks 設定 Java 專案行事曆](/tasks/java/calendars/properties/)
- [使用 Aspose.Tasks for Java 建立自訂行事曆例外](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}