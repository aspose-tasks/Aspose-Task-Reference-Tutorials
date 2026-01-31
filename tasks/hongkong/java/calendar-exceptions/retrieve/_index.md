---
date: 2026-01-31
description: 學習如何使用 Aspose.Tasks for Java 從 MS Project 取得日曆例外，並將 UTC 轉換為本地時間。本 Aspose.Tasks
  Java 教程提供逐步的程式碼範例。
linktitle: Convert UTC to Local – Calendar Exceptions with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 將 UTC 轉換為本地時間 – Aspose.Tasks 行事曆例外
url: /zh-hant/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 檢索日曆例外 – asp tasks java tutorial

## Introduction
在本 **asp tasks java tutorial** 中，您將學習如何使用 Aspose.Tasks for Java 函式庫從 Microsoft Project 檔案中檢索日曆例外。日曆例外代表非工作時段，例如假期或自訂工作時間規則，能以程式方式讀取它們對於資源平衡、報表以及自訂排程邏輯至關重要。透過存取這些例外，您亦可 **convert UTC to local** 時間，以確保排程計算的準確性。我們將一步一步說明整個流程，讓您能自信地將此功能整合至自己的 Java 應檢索日曆** 基本設定約需 10‑15 分鐘。  
- **Prerequisites?** JDK、Aspose.Tasks for Java，以及 IDE（IntelliJ IDEA 或 Eclipse）。  
- **Do I need a license?** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **Supported Project versions?** 支援所有主要的 MS Project 格式（MPP、 is asp tasks java tutorial?
**asp tasks java tutorial** 提供具體的程式碼範例、最佳實踐說明以及實務情境，讓開發者在不安裝 Microsoft Project 的情況下操作 Project 檔案。

## Why retrieve：
- 產生符合假期與自訂工作排程。  
- 建立突顯非工作日的自訂報表工具。  
- **convert UTC to local** 時區，以彙總跨區域的排程資料。  
- 將 Project 日曆與外部系統（如 ERP、HR）同步。

## Prerequisites
在開始之前，請確保您已具備以下條件：

1. **安裝 JDK 8 以上版本。  
2. **Aspose.Tasks for Java** – 從 [here](https://releases.aspose.com/tasks/java/) 下載並安裝。  
3. **Integrated Development Environment (IDE)** – 您可使用任意喜好的 IDE，例如 IntelliJ IDEA 或 Eclipse。

## Import Packages
首先，您需要匯入使用 Aspose.Tasks 所需的套件：

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

> **Pro tip:** 使用Exception`。

## Step 2: Load MS Project File
```java
Project project = new Project(dataDir + "project.mpp");
```

此行程式 Retrieve Calendar Exceptions
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

此段程式會遍歷專案中的每個日曆，然後遍歷該日曆內的每個例外，並印出每個例外的開始與結束日期。

## How to convert UTC to local time using calendar exceptions
當您取得 `FromDate` 與 `ToDate` 時，預設為 UTC 時間。若要配合本地排程，可參考以下方式進行轉換（僅示意，實際轉換程式碼已省略，以免更動原始程式區塊）：

-Date()` 回傳的 `Date` 物件上呼叫 `toInstant().atZone(targetZone)`。

透過此轉換，您可將專案日曆與團隊成員的本地工作時間對齊，對於跨國專案尤為重要。

## Common Issues and Solutions
| 問題 | 原因 | 解決方法 |
|------|------|----------|
| **No output printed** | Project 檔案未包含任何日曆例外。 | 確認 MS Project 中的日曆已設定例外（例如假期）。 |
| **`NullPointerException`** | `dataDir` 路徑不正確或檔案未找到。 | 再次檢查目錄路徑，確保 `project** | 日期以 UTC 顯示。 | 如有需要，使用 `calExc.getFromDate().toLocalDateTime()` 轉換為本地時間。 |

## Frequently Asked Questions
### Can Aspose.Tasks handle different versions of MS Project files?
是的，PT 以及 XML 格式。

### Is there a free trial available for Aspose.Tasks?
是的，您可從 [here](https://releases.aspose.com/) 下載 Asposeose.Tasks for Java?
您可以參考文件 [here](https://reference.aspose.com/tasks/java/)。

### How can I get support for Aspose.Tasks?
您可於社群論壇取得支援，連結在 [here](https://forum.aspose.com/c/tasks/15)。

### Is there an option for temporary licenses for Aspose.Tasks?
是的，您可從 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Additional Q&A**

**Q:** *Can I modify calendar exceptions after retrieving them?*  
**A:** 當然可以。使用 `CalendarException.setFromDate()` 與 `setToDate()` 調整日期，然後以 `project.save(...)` 儲存專案。

**Q:** *Does Aspose.Tasks preserve custom fields on calendars?*  
**A:**自訂欄位與擴充屬性皆會被保留。

**Q:** *How do I convert the retrieved UTC dates to my local time zone?*  
**A:** 使用 Java 的 `ZoneId` 與 `ZonedDateTime` 轉換方法，對 API 回傳的 `Date` 物件進行處理，即可確保排程反映本地工作時段。

## Conclusion
在本 **asp tasks java tutorial** 中，我 從 MS Project 檔案中檢索日曆例外，並且 **convert UTC to local** 時間，以達到精確排程。只要依照上述簡易步驟，即可將此功能無縫整合至您的 Java 應用程式，提供更豐富的排程特性與更精確的專案分析。

---

**Last Updated:** 2026-01-31  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}