---
date: 2026-08-24
description: 了解如何從 MS Project 檔案中取得 Java 行事曆例外，以及如何使用 Aspose.Tasks for Java 讀取 mpp
  行事曆。本教學提供逐步的程式碼範例。
keywords:
- retrieve calendar exceptions java
- how to read mpp calendar
- Aspose.Tasks Java
- MS Project calendar API
lastmod: 2026-08-24
linktitle: 如何使用 Aspose.Tasks 於 Java 取得行事曆例外
og_description: 了解如何從 MS Project 檔案中取得 Java 行事曆例外，以及如何使用 Aspose.Tasks for Java 讀取
  mpp 行事曆。本逐步指南可協助您在 Java 應用程式中加入精確的行事曆處理。
og_image_alt: Developer guide showing Java code to read calendar exceptions from an
  MS Project file
og_title: 如何使用 Aspose.Tasks 於 Java 取得行事曆例外
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  headline: How to retrieve calendar exceptions java with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  name: How to retrieve calendar exceptions java with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
    text: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
    text: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
  type: HowTo
- questions:
  - answer: Retrieving calendar exceptions from an MPP file using Aspose.Tasks for
      Java.
    question: What does this tutorial cover?
  - answer: About 10‑15 minutes for a basic setup.
    question: How long does implementation take?
  - answer: JDK, Aspose.Tasks for Java, and an IDE (IntelliJ IDEA or Eclipse).
    question: Prerequisites?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: All major MS Project formats (MPP, MPT, XML).
    question: Supported Project versions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project scheduling
- calendar exceptions
- MS Project integration
- developer tutorial
title: 如何使用 Aspose.Tasks 於 Java 取得行事曆例外
url: /zh-hant/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 於 Java 取得行事曆例外

## 介紹
在本 **asp tasks java tutorial** 中，您將學習如何使用 Aspose.Tasks for Java 函式庫從 Microsoft Project 檔案中取得行事曆例外。行事曆例外代表非工作期間，例如假期或自訂工作時間規則，能以程式方式讀取它們對於資源平衡、報表以及自訂排程邏輯至關重要。我們將一步一步說明整個流程，讓您能自信地將此功能整合到自己的 Java 應用程式中。

## 快速解答
- **此教學涵蓋什麼內容？** 使用 Aspose.Tasks for Java 從 MPP 檔案取得行事曆例外。  
- **實作需要多久？** 基本設定約需 10‑15 分鐘。  
- **先決條件？** JDK、Aspose.Tasks for Java，以及 IDE（IntelliJ IDEA 或 Eclipse）。  
- **需要授權嗎？** 開發可使用免費試用版，正式上線需購買商業授權。  
- **支援的 Project 版本？** 所有主要的 MS Project 格式（MPP、MPT、XML）。

## 什麼是 asp tasks java tutorial？
**asp tasks java tutorial** 說明如何在 Java 專案中使用 Aspose.Tasks API。它提供具體的程式碼片段、最佳實踐說明以及真實情境，讓開發者在不安裝 Microsoft Project 的情況下操作 Project 檔案。透過此類教學，開發者能清楚且實作上掌握 API 結構、常見使用模式，以及如何將其功能整合至大型企業應用程式中。

## 為何要取得行事曆例外？
取得行事曆例外可讓您產生符合假期與自訂工作排程的精確專案時間表、建立突顯非工作日的報表工具，並將 Project 行事曆與 ERP 或 HR 等外部系統同步。Aspose.Tasks 能從 **30+** 種行事曆類型讀取例外，且支援 **3 大** MS Project 檔案格式（MPP、MPT、XML），無需將整個檔案載入記憶體，即可有效處理上百頁的專案。

## 先決條件
在開始之前，請確保您具備以下條件：

1. **Java Development Kit (JDK)** – 確保已安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)** 下載並安裝 Aspose.Tasks for Java。  
3. **Integrated Development Environment (IDE)** – 您可使用任何喜好的 IDE，例如 IntelliJ IDEA 或 Eclipse。

## 匯入套件
以下匯入語句將 Aspose.Tasks 類別帶入您的 Java 原始檔，使您能操作專案、行事曆與例外。

```java
import com.aspose.tasks.*;
import java.util.*;
```

## 步驟 1：設定資料目錄
定義一個資料夾，放置您要分析的 Project 檔案。使用絕對路徑或相對於專案 resources 資料夾的路徑，可避免 `FileNotFoundException`。

```java
String dataDir = "C:/Projects/Data/";
```

> **專業提示：** 將 Project 檔案存放於專用的 resources 資料夾，並使用 `Paths.get(...)` 以取得跨平台的路徑。

## 步驟 2：載入 MS Project 檔案
`Project` 類別代表一個 MS Project 檔案，提供對其行事曆、工作、資源及其他專案資料的存取。將 Project 檔案載入 `Project` 物件。此物件在記憶體中代表整個 MS Project 檔案，並可存取行事曆、工作、資源等。

```java
Project project = new Project(dataDir + "project.mpp");
```

## 步驟 3：取得行事曆例外
遍歷專案中的每個行事曆，然後遍歷該行事曆內的每個例外，印出每個例外的開始與結束日期。

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("Exception from " + calExc.getFromDate() + " to " + calExc.getToDate());
    }
}
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|-------|--------|-----|
| **未輸出任何內容** | Project 檔案未包含任何行事曆例外。 | 確認 MS Project 中的行事曆已定義例外（例如假期）。 |
| **`NullPointerException`** | `dataDir` 路徑不正確或找不到檔案。 | 再次確認目錄路徑，並確保 `project.mpp` 存在。 |
| **時區不匹配** | 日期顯示為 UTC。 | 如有需要，使用 `calExc.getFromDate().toLocalDateTime()` 轉換為本地時間。 |

## 常見問答
### Aspose.Tasks 能處理不同版本的 MS Project 檔案嗎？
是的，Aspose.Tasks 支援 **所有主要** 的 MS Project 格式，包括 MPP、MPT 與 XML，涵蓋 2000 版至最新版本。

### 是否提供 Aspose.Tasks 的免費試用？
是的，您可從 **[Aspose free trial download page](https://releases.aspose.com/)** 下載 Aspose.Tasks 的免費試用版。

### 在哪裡可以找到 Aspose.Tasks for Java 的文件？
您可參考 **[Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/)**。

### 如何取得 Aspose.Tasks 的支援？
您可在社群論壇 **[Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)** 取得支援。

### 是否有 Aspose.Tasks 的臨時授權選項？
是的，您可於 **[temporary license purchase page](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**其他問答**

**Q:** *取得例外後，我可以修改行事曆例外嗎？*  
**A:** 當然可以。使用 `CalendarException.setFromDate()` 與 `setToDate()` 調整日期，然後以 `project.save(...)` 儲存專案。

**Q:** *Aspose.Tasks 會保留行事曆的自訂欄位嗎？*  
**A:** 會的，載入與儲存專案時，所有自訂欄位與擴充屬性皆會被保留。

## 結論
在本 **asp tasks java tutorial** 中，我們學會如何使用 Aspose.Tasks for Java 從 MS Project 取得行事曆例外。依循這些簡易步驟，您即可將此功能無縫整合至 Java 應用程式，提供更豐富的排程功能與更精確的專案分析。

---

**最後更新：** 2026-08-24  
**測試版本：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  








```java
import com.aspose.tasks.*;
```

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

```java
Project project = new Project(dataDir + "project.mpp");
```

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

## 相關教學

- [使用 Aspose.Tasks for Java 建立自訂行事曆例外](/tasks/java/calendar-exceptions/)
- [如何使用 Aspose.Tasks 取得 MS Project 行事曆資訊](/tasks/java/project-file-operations/retrieve-calendar-info/)
- [如何使用 Aspose.Tasks 於 Java 讀取 MS Project 行事曆工作週](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}