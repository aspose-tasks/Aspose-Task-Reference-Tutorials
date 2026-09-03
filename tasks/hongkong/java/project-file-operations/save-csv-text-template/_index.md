---
date: 2026-05-26
description: 了解如何使用 Aspose.Tasks for Java 將 MPP 匯出為 CSV、將專案儲存為範本，以及將 MPP 轉換為文字。
keywords:
- export mpp to csv
- save project as template
- convert mpp to csv
linktitle: 使用 Aspose.Tasks Java 匯出 MPP 為 CSV、文字及範本
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  headline: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  name: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  steps:
  - name: Save as CSV
    text: '`SaveFileFormat.CSV` tells Aspose.Tasks to output the project in CSV format.'
  - name: Save as Text
    text: '`SaveFileFormat.TEXT` instructs the library to generate a plain‑text representation
      of the project.'
  - name: Set Template Options
    text: Use `Project.save` with `SaveFileFormat.MPT` (or `SaveFileFormat.TEMPLATE`)
      to create a template file that strips dates and baselines.
  type: HowTo
- questions:
  - answer: Yes, it fully supports tasks, resources, assignments, baselines, and custom
      fields across all Project versions up to 2024.
    question: Can Aspose.Tasks for Java handle complex, multi‑phase projects?
  - answer: Absolutely – download a free trial from [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The official support forum is at [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      where staff and community members answer questions.
    question: Where can I get help if I run into problems?
  - answer: Yes, purchase a temporary license at [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for short‑term evaluation?
  - answer: It is fully cross‑platform and works on Windows, macOS, and Linux with
      any Java 8+ runtime.
    question: Does Aspose.Tasks run on Linux and macOS?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks Java 匯出 MPP 為 CSV、文字及範本
url: /zh-hant/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 匯出 MPP 為 CSV、文字與範本（使用 Aspose.Tasks for Java）

## 介紹
在本教學中，您將了解 **如何將 MPP 匯出為 CSV**、建立可重複使用的專案範本，並使用 Aspose.Tasks for Java 函式庫產生純文字擷取。無論您是要建構報表管線、自動化專案建立，或與其他系統整合，這些步驟都能讓您從原始 MPP 檔案快速取得所需的輸出，而無需安裝 Microsoft Project。

## 快速解答
- **我可以將 MPP 匯出為 CSV 嗎？** 是 – 呼叫 `project.save("output.csv", SaveFileFormat.CSV)`。  
- **如何匯出為純文字？** 使用 `SaveFileFormat.TEXT` 搭配 `save` 方法。  
- **「將專案儲存為範本」的作用是什麼？** 它會建立一個 `.mpt` 檔案，移除日期與基線，只保留骨架結構。  
- **我需要授權嗎？** 試用版可用於評估；商業授權則會移除評估限制。  
- **需要哪個 Java 版本？** 支援 Java 8 或更新版本。

## 「將專案儲存為範本」是什麼？
將專案儲存為範本（`.mpt`）會保留結構、工作階層與資源指派，同時移除實際的開始/結束日期與基線資料。此範本非常適合在多個新專案中重複使用標準的專案版面。它會保留所有自訂欄位、成本費率與指派細節，確保範本可套用於任何新專案而不會失去關鍵設定。

## 為什麼使用 Aspose.Tasks for Java？
直接在 Java 中將 MPP 匯出為 CSV、文字或範本，無需 Microsoft Project。Aspose.Tasks 支援 **20 多個 Microsoft Project 版本**（2000‑2024），且可在記憶體效能模式下處理高達 **500 MB** 的檔案，非常適合伺服器端自動化、CI 管線與跨平台工具。

## 前置條件
- 已安裝 Java Development Kit 8 或更高版本。  
- 已將 Aspose.Tasks for Java 函式庫加入您的專案 – 從 [此處](https://releases.aspose.com/tasks/java/) 下載。  
- 您也可以在 [此處](https://releases.aspose.com/) 探索其他 Aspose 函式庫。  
- 具備 Java 及 Maven/Gradle 專案設定的基本知識。

## 匯入套件
`Project` 類別是 Aspose.Tasks 的核心物件，代表記憶體中的 Microsoft Project 檔案。將函式庫加入建置檔後，匯入所需的類別：

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## 將專案儲存為 CSV（匯出 MPP 為 CSV）
將 MPP 檔案匯出為 CSV 可讓您將工作資料匯入 Excel、Power BI 或任何分析平台。

### 步驟 1：載入專案
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 步驟 2：儲存為 CSV
`SaveFileFormat.CSV` 告訴 Aspose.Tasks 以 CSV 格式輸出專案。  
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## 將專案儲存為文字（如何匯出文字）
純文字檔案提供快速且易於閱讀的工作、資源與指派資料匯出。

### 步驟 1：載入專案
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 步驟 2：儲存為文字
`SaveFileFormat.TEXT` 指示函式庫產生專案的純文字表示。  
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## 將專案儲存為範本（建立 Java 專案範本）

### 步驟 1：載入專案
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 步驟 2：設定範本選項
使用 `Project.save` 搭配 `SaveFileFormat.MPT`（或 `SaveFileFormat.TEMPLATE`）建立會移除日期與基線的範本檔案。  
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### 步驟 3：儲存為範本
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## 常見問題與技巧
- **找不到檔案：** 請確認 `YourProject.mpp` 的路徑，或使用絕對路徑。  
- **授權例外：** 若未取得有效授權，函式庫會以評估模式執行，可能會加入浮水印。請盡早套用授權 (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`)。  
- **大型專案：** 若檔案大於 200 MB，請增加 JVM 堆積大小（`-Xmx2g`）以避免 `OutOfMemoryError`。  
- **效能：** 在轉換多個專案時，盡可能重複使用單一 `Project` 實例，以減少物件建立的開銷。

## 結論
我們示範了如何使用 Aspose.Tasks for Java **匯出 MPP 為 CSV**、**將 MPP 轉換為文字**，以及 **將專案儲存為範本**。這些功能讓您能自動化報表、建立標準化的專案骨架，並將專案資料整合至任何下游系統——無需安裝 Microsoft Project。

## 常見問答

**Q: Aspose.Tasks for Java 能處理複雜的多階段專案嗎？**  
A: 可以，它完整支援所有任務、資源、指派、基線與自訂欄位，涵蓋至 2024 年的所有 Project 版本。

**Q: 有提供試用版嗎？**  
A: 當然有 – 從 [此處](https://releases.aspose.com/) 下載免費試用版。

**Q: 若遇到問題，我該向何處尋求協助？**  
A: 官方支援論壇位於 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)，那裡有工作人員與社群成員回答問題。

**Q: 我可以取得臨時授權以進行短期評估嗎？**  
A: 可以，請在 [此處](https://purchase.aspose.com/temporary-license/) 購買臨時授權。

**Q: Aspose.Tasks 能在 Linux 與 macOS 上執行嗎？**  
A: 它是完全跨平台的，能在 Windows、macOS 與 Linux 上執行，支援任何 Java 8+ 執行環境。

---

**最後更新：** 2026-05-26  
**測試環境：** Aspose.Tasks for Java 24.12（最新）  
**作者：** Aspose

## 相關教學

- [如何建立 MPP 檔案 – 使用 Aspose.Tasks 建立與儲存空白 MPP 專案](/tasks/java/project-configuration/create-save-mpp/)
- [載入 MPP 檔案（Java）- 使用 Aspose.Tasks 管理專案屬性](/tasks/java/project-management/default-properties/)
- [如何使用 Aspose.Tasks for Java 匯出 MPP 為 Excel](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}