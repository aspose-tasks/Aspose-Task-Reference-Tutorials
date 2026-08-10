---
date: 2026-06-15
description: 了解如何使用 Aspose.Tasks for Java 將 MPP 轉換為 PDF，並呈現資源使用與工作表檢視。依循我們的逐步指南設定時間尺度，輕鬆產生詳細的
  PDF 報告。
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: 將 MPP 轉換為 PDF 並呈現資源使用檢視 – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 將 MPP 轉換為 PDF 並呈現資源使用檢視 – Aspose.Tasks
url: /zh-hant/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將 MPP 轉換為 PDF 並呈現資源使用檢視 – Aspose.Tasks

在本教學中，您將學習 **如何將 mpp 轉換為 pdf**，同時呈現 Microsoft Project 檔案的資源使用與工作表檢視。使用 Aspose.Tasks for Java 可免除伺服器上安裝 Microsoft Project，為您提供快速且可靠的方式，從 MPP 檔案產生 PDF 報告。我們亦會示範 **如何設定時間尺度**，使輸出符合您的報告需求。

## 快速解答
- **Aspose.Tasks 的功能是什麼？** 它可以讀取、修改並轉換 Microsoft Project (MPP) 檔案，無需安裝 MS Project。  
- **我可以用一行程式碼將 MPP 轉換為 PDF 嗎？** 可以 – 載入 Project、設定 SaveOptions，然後呼叫 `save`。  
- **支援哪些時間尺度？** Days、ThirdsOfMonths 與 Months。  
- **生產環境需要授權嗎？** 非試用部署必須使用商業授權。  
- **此函式庫相容於 Java 8+ 嗎？** 當然相容 – 支援 Java 8 及更高版本。

## 什麼是 convert mpp to pdf？
*Convert mpp to pdf* 指的是將 Microsoft Project (.mpp) 檔案轉換為可攜式文件格式 (PDF) 的過程，該 PDF 能忠實再現專案的表格、排程、圖表與資源分配。產生的 PDF 可輕鬆分享、列印與保存，且不需在接收者的電腦上安裝 Microsoft Project。

## 為何使用 Aspose.Tasks 將 Project 轉換為 PDF？
Aspose.Tasks 支援 **超過 50 種輸入與輸出格式**，且能在不將整個檔案載入記憶體的情況下呈現數百頁的專案，將 RAM 使用量降低至最高約 70 %。PDF 輸出保留表格、圖表與資源分配，非常適合給予利害關係人分發與存檔。

## 前置條件
1. **Java Development Kit (JDK)** – 在您的機器上安裝 Java 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 [download page](https://releases.aspose.com/tasks/java/) 下載最新的 JAR。

## 如何使用 Aspose.Tasks for Java 進行 convert mpp to pdf？
載入來源 MPP 檔案，設定所需的時間尺度，將呈現格式設為 **ResourceUsage**，並將結果儲存為 PDF。此端對端流程僅需少量 API 呼叫，對於一般專案規模可在一秒內完成。

### 步驟 1：讀取來源專案
`Project` 類別代表已載入記憶體的 Microsoft Project 檔案，提供對其資料與結構的存取。  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### 步驟 2：使用所需的 TimeScale 設定定義 SaveOptions
`SaveOptions` 用於設定專案的儲存方式，允許您指定如時間尺度等格式特定設定。  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### 步驟 3：將呈現格式設定為 ResourceUsage
`PresentationFormat` 決定在輸出文件中呈現哪一種 Project 檢視（例如 ResourceUsage）。  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### 步驟 4：將專案儲存為 PDF
`project.save` 使用提供的 `SaveOptions` 將專案寫入檔案，產生最終的 PDF。  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### 步驟 5：為其他 TimeScale 設定呈現檢視
重複前述步驟，變更 `TimeScale` 值以呈現其他時間尺度的檢視。  
```java
// Save the Project
project.save(dataDir + days, options);
```

### 步驟 6：選用 – 批次轉換多個專案
如果您需要為多個檔案 **convert project to pdf**，可將上述邏輯放入迴圈，遍歷 *.mpp* 檔案目錄。此方法可批量 **saves ms project pdf** 檔案，僅需最少的程式碼變更。以下程式碼示範完整的將 MPP 檔案依設定轉換為 PDF 的範例。  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## 常見問題與解決方案
- **PDF 中缺少字型** – 確保伺服器已安裝所需字型，或透過 `PdfSaveOptions` 內嵌字型。  
- **大型專案檔導致 OutOfMemoryError** – 使用 `LoadOptions.setLoadAllResources(false)` 以按需載入資源。  
- **時間尺度呈現不正確** – 確認 `options.setTimeScale(TimeScale.Days)`（或其他列舉）符合所需的粒度。

## 常見問答

**Q: Aspose.Tasks 能否呈現除資源使用與工作表之外的其他檢視？**  
A: 可以，它亦支援甘特圖、任務使用、行事曆以及許多其他檢視。

**Q: Aspose.Tasks 是否相容於不同版本的 Microsoft Project 檔案？**  
A: 絕對相容 – 它能處理從 Project 2000 到 Project 2021 的 MPP、MPT 與 XML 格式。

**Q: 我可以自訂呈現檢視的外觀嗎？**  
A: 可以，您可透過 `PdfSaveOptions` 與 `PresentationOptions` 修改顏色、字型與欄位佈局。

**Q: Aspose.Tasks 是否需要安裝 Microsoft Project？**  
A: 不需要，它是一個獨立的函式庫，可在任何相容 Java 的環境中運作。

**Q: 我可以在哪裡取得技術支援？**  
A: 可透過 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/) 獲得支援。

---

**最後更新：** 2026-06-15  
**測試環境：** Aspose.Tasks 24.12 for Java  
**作者：** Aspose

## 相關教學

- [在 Aspose.Tasks 中呈現資源使用與工作表檢視](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [如何在 Aspose.Tasks 中匯出 PDF – 另存為 PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [如何使用 Aspose.Tasks for Java 建立 MPP 檔案](/tasks/java/project-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}