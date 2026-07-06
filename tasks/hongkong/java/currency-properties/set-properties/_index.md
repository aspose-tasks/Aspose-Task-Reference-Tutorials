---
date: 2026-02-07
description: 了解如何在 Aspose.Tasks 專案中設定 Java 貨幣代碼、變更貨幣符號，並為 Microsoft Project 檔案套用自訂貨幣格式。
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: 貨幣代碼 Java – 如何在 Aspose.Tasks 專案中設定
url: /zh-hant/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks – Java 中設定貨幣代碼指南

## Introduction
在本教學中，您將學習 **如何在 Java 中設定貨幣代碼**，以使用 Aspose.Tasks Java API 針對 Microsoft Project 檔案設定貨幣代碼。無論您需要為國際團隊 **變更貨幣**、調整 **貨幣符號**，或套用 **自訂貨幣格式**，以下步驟將以清晰說明與可直接執行的程式碼帶您完成整個流程。

## Quick Answers
- **需要的函式庫是什麼？** Aspose.Tasks for Java。  
- **我可以變更貨幣符號嗎？** 可以 – 使用 `CurrencySymbolPositionType` 與 `Prj.CURRENCY_SYMBOL`。  
- **支援哪些檔案格式？** XML、MPP，以及透過 `SaveFileFormat` 支援的其他多種格式。  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式環境需購買授權。  
- **實作大約需要多久？** 基本設定約 5‑10 分鐘即可完成。

## How to Set Currency Code Java in Aspose.Tasks
專案的貨幣定義了成本值的顯示方式——代碼（例如 `AUD`）、小數位數、符號（`$`）以及符號的位置。設定這些屬性可確保所有與成本相關的欄位（資源費率、工作任務預算等）皆以正確的貨幣格式呈現給您的使用者。

## Why Use Aspose.Tasks to Change Currency?
- **不需安裝 Microsoft Project** – 可在任何伺服器上操作檔案。  
- **完整 API 覆蓋** – 所有與貨幣相關的欄位皆透過 `Prj` 常數公開。  
- **跨平台** – 可在 Windows、Linux、macOS 上執行，支援任何相容 Java 的 IDE。  
- **高效能** – 快速且可靠地處理大型專案檔案。  
- **支援自訂貨幣格式** – 您可以自行定義符號、小數位數與位置，以符合區域標準。

## Prerequisites
在開始之前，請確保您已具備以下項目：

1. **Java Development Kit (JDK)** – 8 版或以上。  
2. **Aspose.Tasks for Java** – 從 [Aspose.Tasks 下載頁面](https://releases.aspose.com/tasks/java/) 下載最新 JAR。  
3. **IDE** – Eclipse、IntelliJ IDEA，或您偏好的任何編輯器。  
4. **可寫入的資料夾** – 用於儲存產生的專案檔案。

## Import Packages
First, import the classes that provide access to project properties and file handling.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define the Data Directory
Specify the folder that contains your source files and where the output will be written.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Create a New Project Instance
Instantiate a fresh `Project` object. This object represents an in‑memory Microsoft Project file.

```java
Project project = new Project();
```

### Step 3: Set Currency Properties
Here’s where we **how to set currency** details such as code, digits, symbol, and symbol position.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Pro tip:** If you need to **change project currency** for an existing file, simply load it with `new Project("file.mpp")` before applying the above settings.

### Step 4: Save the Updated Project
Write the project back to disk in the desired format. In this example we use the XML format, but you can also choose `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 5: Confirm Success
Print a friendly message so you know the operation completed without errors.

```java
System.out.println("Process completed Successfully");
```

## Common Issues & Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `project.save`** | `dataDir` is not a valid path or lacks write permission. | Ensure the directory exists and your Java process has write access. |
| **Currency symbol not showing** | The symbol position is set incorrectly for your locale. | Use `CurrencySymbolPositionType.Before` if the symbol should precede the amount. |
| **Project file does not open in MS Project** | Saving in an older format with incompatible settings. | Save using `SaveFileFormat.MPP` for full compatibility with recent MS Project versions. |

## Frequently Asked Questions

**Q: Can I set multiple currencies in a single project using Aspose.Tasks?**  
A: Yes, Aspose.Tasks allows you to handle multiple currencies within a single project file by setting currency properties on a per‑resource or per‑task basis.

**Q: Is Aspose.Tasks compatible with different versions of Microsoft Project files?**  
A: Absolutely. The library supports MPP files from Project 2000 up to the latest releases, as well as XML and other formats.

**Q: Does Aspose.Tasks provide support for custom currency formats?**  
A: Yes, you can define custom symbols, decimal digits, and positioning to meet any regional requirement.

**Q: Can I integrate Aspose.Tasks with other Java libraries or frameworks?**  
A: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate, Maven, Gradle, and other ecosystems.

**Q: Where can I find additional support or assistance for Aspose.Tasks?**  
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community help, or consult the official documentation for detailed API references.

## Conclusion
You now know **how to set currency code java**, how to **change currency** values, and how to **change currency symbol** using Aspose.Tasks for Java. These capabilities let you tailor cost data for global teams, generate locale‑specific reports, and keep your project files consistent across borders.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}