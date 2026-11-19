---
date: 2026-11-19
description: 了解如何從 MS Project 檔案中取得 Java 行事曆例外，以及如何使用 Aspose.Tasks for Java 讀取 MPP
  行事曆。本教學提供逐步程式碼範例。
images:
- /java/calendar-exceptions/retrieve/og-image.png
keywords:
- retrieve calendar exceptions java
- Aspose.Tasks for Java
- MS Project calendar API
- read MPP calendar
- Java project scheduling
lastmod: 2026-11-19
linktitle: 如何使用 Aspose.Tasks 在 Java 中取得行事曆例外
og_description: 了解如何從 MS Project 檔案中取得 Java 行事曆例外，並使用 Aspose.Tasks for Java 讀取 MPP
  行事曆。本指南說明如何在 Java 應用程式中加入精確的行事曆處理。
og_image_alt: Developer guide showing Java code to read calendar exceptions from an
  MS Project file
og_title: 如何使用 Aspose.Tasks 取得 Java 行事曆例外
schemas:
- author: Aspose
  dateModified: '2026-11-19'
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
title: 如何使用 Aspose.Tasks 在 Java 中取得行事曆例外
url: /zh-hant/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 於 Java 取得行事曆例外

## 簡介
在本 **asp tasks java tutorial** 中，您將學習如何使用 Aspose.Tasks Java 函式庫從 Microsoft Project 檔案中取得行事曆例外。行事曆例外代表非工作期間，例如假期或自訂工作時間規則，能以程式方式讀取它們對於資源平衡、報表以及自訂排程邏輯至關重要。我們將一步一步說明整個流程，讓您能自信地將此功能整合到自己的 Java 應用程式中。

## 快速回答
- **此教學涵蓋什麼內容？** Retrieving calendar exceptions from an MPP file using Aspose.Tasks for Java.  
- **實作需要多長時間？** About 10‑15 minutes for a basic setup.  
- **先決條件？** JDK, Aspose.Tasks for Java, and an IDE (IntelliJ IDEA or Eclipse).  
- **需要授權嗎？** A free trial works for development; a commercial license is required for production.  
- **支援的 Project 版本？** All major MS Project formats (MPP, MPT, XML).

## 什麼是 asp tasks java tutorial？
在 **asp tasks java tutorial** 中說明如何在 Java 專案中使用 Aspose.Tasks API。它提供具體的程式碼範例、最佳實踐說明以及實務情境，讓開發者無需安裝 Microsoft Project 即可操作 Project 檔案。透過此類教學，開發者能清楚且實作地了解 API 結構、常見使用模式，並將其功能整合至更大型的企業應用程式中。

## 為什麼要取得行事曆例外？
取得行事曆例外可讓您產生符合假期與自訂工作排程的精確專案時間表、建立突顯非工作日的報表工具，並將 Project 行事曆與 ERP 或 HR 等外部系統同步。Aspose.Tasks 能從 **30+** 種行事曆類型讀取例外，且支援 **3 major** MS Project 檔案格式（MPP、MPT、XML），無需將整個檔案載入記憶體，從而有效處理數百頁的專案。

## 先決條件
在開始之前，請確保您具備以下先決條件：

1. **Java Development Kit (JDK)** – 確保已安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)** 下載並安裝 Aspose.Tasks for Java。  
3. **Integrated Development Environment (IDE)** – 您可以使用任何喜好的 IDE，例如 IntelliJ IDEA 或 Eclipse。  

您也可以在教學後期需要提醒時，從 **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)** 取得 Aspose.Tasks for Java。

## 如何設定資料目錄？
定義一個資料夾以放置您要分析的 Project 檔案。使用絕對路徑或相對於專案 resources 資料夾的路徑可避免 `FileNotFoundException`。將檔案存放在專屬的 `resources` 資料夾中，並使用 `Paths.get(...)` 來引用，確保程式碼平台無關，避免硬編碼 Windows 路徑。

## 匯入套件
import 陳述式會將 Aspose.Tasks 類別匯入您的 Java 原始檔，使您能操作專案、行事曆與例外。

```java
import com.aspose.tasks.*;
import java.util.*;
```

## 什麼是 Project 類別？
`Project` 代表已載入記憶體的 MS Project 檔案。它是 Aspose.Tasks 的主要物件，透過乾淨的物件導向 API 讓您存取行事曆、工作、資源與其他專案資料。使用 `Project` 類別，您可以在不安裝 Microsoft Project 的情況下查詢與操作專案的每個元素，非常適合伺服器端處理與自動化報表。

## 步驟 1：設定資料目錄
定義一個資料夾以放置您要分析的 Project 檔案。使用絕對路徑或相對於專案 resources 資料夾的路徑可避免 `FileNotFoundException`。

```java
String dataDir = "C:/Projects/Data/";
```

> **專業提示：** 將您的 Project 檔案存放於專屬的 resources 資料夾，並使用 `Paths.get(...)` 以取得平台無關的路徑。

## 步驟 2：載入 ms project 檔案
`Project` 類別代表一個 MS Project 檔案，並提供對其行事曆、工作、資源與其他專案資料的存取。將 Project 檔案載入至 `Project` 物件中。此物件在記憶體中代表整個 MS Project 檔案，並提供行事曆、工作、資源等的存取。

```java
Project project = new Project(dataDir + "project.mpp");
```

## 如何從已載入的專案取得行事曆例外？
遍歷專案中的每個行事曆，然後遍歷該行事曆內的每個行事曆例外。列印每個例外的開始與結束日期。此兩層迴圈確保即使專案包含多個行事曆（標準、資源或自訂），也能捕捉到所有例外。透過檢查每個 `CalendarException`，您可以建立自訂報表、調整排程，或將資料匯出至其他系統。

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("Exception from " + calExc.getFromDate() + " to " + calExc.getToDate());
    }
}
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方法 |
|-------|--------|-----|
| **未輸出任何內容** | Project 檔案未包含任何行事曆例外。 | 確認 MS Project 中的行事曆已定義例外（例如假期）。 |
| **`NullPointerException`** | `dataDir` 路徑不正確或檔案未找到。 | 再次檢查目錄路徑，並確保 `project.mpp` 存在。 |
| **時區不匹配** | 日期以 UTC 顯示。 | 如有需要，使用 `calExc.getFromDate().toLocalDateTime()` 轉換為本地時間。 |

## 常見問與答
### Aspose.Tasks 能處理不同版本的 MS Project 檔案嗎？
是的，Aspose.Tasks 支援 **all major** MS Project 格式，包括 MPP、MPT 與 XML，涵蓋從 2000 年版至最新版本。

### 是否提供 Aspose.Tasks 的免費試用？
是的，您可從 **[Aspose free trial download page](https://releases.aspose.com/)** 下載 Aspose.Tasks 的免費試用版。

### 哪裡可以找到 Aspose.Tasks for Java 的文件？
您可以參考文件 **[Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/)**。

### 如何取得 Aspose.Tasks 的支援？
您可從社群論壇 **[Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)** 取得支援。

### 是否有 Aspose.Tasks 的臨時授權選項？
是的，您可從 **[temporary license purchase page](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**其他問答**

**Q:** *取得行事曆例外後，我可以修改它們嗎？*  
**A:** 當然可以。使用 `CalendarException.setFromDate()` 與 `setToDate()` 來調整日期，然後使用 `project.save(...)` 儲存專案。

**Q:** *Aspose.Tasks 會保留行事曆的自訂欄位嗎？*  
**A:** 會的，載入與儲存專案時，所有自訂欄位與擴充屬性皆會被保留。

## 結論
在本 **asp tasks java tutorial** 中，我們學會了如何使用 Aspose.Tasks for Java 從 MS Project 取得行事曆例外。遵循這些簡單步驟，您即可將此功能無縫整合至 Java 應用程式中，實現更豐富的排程功能與更精確的專案分析。

---

**最後更新:** 2026-11-19  
**測試環境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose  








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
- [如何從 MS Project 行事曆讀取工作週（Java） Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}