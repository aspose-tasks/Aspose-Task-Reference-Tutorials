---
date: 2026-01-15
description: 學習如何將專案儲存為 PDF，並使用 Aspose.Tasks for Java 產生 MS Project 的資源使用與工作表檢視。跟隨我們的逐步指南，輕鬆將專案匯出為
  PDF。
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 將專案另存為 PDF – 在 Aspose.Tasks 中呈現資源使用情況與工作表檢視
url: /zh-hant/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將專案另存為 PDF – 在 Aspose.Tasks 中呈現資源使用與工作表檢視

## 簡介
在本教學中，您將學會如何 **將專案另存為 PDF**，同時呈現 Microsoft Project 檔案的資源使用與工作表檢視。無論是需要為利害關係人產生可列印的報告，或是將 MPP 檔案轉換為通用的可檢視格式，Aspose.Tasks for Java 都能讓此流程變得簡單——不需要安裝 Microsoft Project。

## 快速解答
- **「將專案另存為 PDF」的功能是什麼？** 它會將 Project 檔案 (MPP) 轉換為 PDF 文件，並保留所選的檢視。  
- **可以匯出哪種檢視？** 資源使用、工作表、甘特圖、任務使用等。  
- **我可以在 PDF 中變更時間尺度嗎？** 可以——選項包括「天 (Days)」、「月的三分之一 (ThirdsOfMonths)」以及「月 (Months)」。  
- **需要安裝 Microsoft Project 嗎？** 不需要，Aspose.Tasks 可獨立運作。  
- **正式環境是否需要授權？** 需要，非試用版必須購買商業授權。

## 什麼是「將專案另存為 PDF」？
將專案另存為 PDF 會產生所選 Project 檢視的靜態高解析度圖像。此方式非常適合與客戶分享、歸檔或列印，而不會洩漏底層的專案檔案。

## 為什麼使用 Aspose.Tasks 匯出專案為 PDF？
- **無外部相依性** – 可在任何支援 Java 的平台上運行。  
- **細緻的控制** – 您可以選擇檢視、時間尺度與版面配置。  
- **高保真度** – PDF 會忠實呈現原始 Project 檢視的外觀。  
- **自動化就緒** – 可整合至 CI 流程、報告服務或批次轉換器。

## 先決條件
在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 建議使用最新版本。  
2. **Aspose.Tasks for Java** – 從[下載頁面](https://releases.aspose.com/tasks/java/)下載。  

## 匯入套件
首先，將必要的類別匯入您的 Java 專案：

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## 逐步指南

### 步驟 1：讀取來源專案
載入您想要轉換的 MPP 檔案。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### 步驟 2：定義 SaveOptions 並設定所需時間尺度（匯出專案為 PDF）
設定 PDF 匯出選項並指定欲使用的時間尺度。  
*此處以 **Days** 為範例。*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### 步驟 3：將呈現格式設定為 ResourceUsage
選擇要呈現的檢視。本例使用 **Resource Usage** 檢視。

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### 步驟 4：儲存專案（將 MPP 轉換為 PDF）
執行轉換並產生 PDF 檔案。

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### 步驟 5：為其他時間尺度設定呈現檢視（變更時間尺度 PDF）
重複前述步驟，以產生使用 **ThirdsOfMonths** 或 **Months** 等不同時間尺度的 PDF。

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## 常見問題與解決方案
- **File not found errors** – Verify that `dataDir` points to the correct folder and that the MPP file name matches exactly.  
- **Blank PDF output** – Ensure the `PresentationFormat` matches a view that contains data (e.g., ResourceUsage).  
- **Incorrect timescale** – Double‑check that `options.setTimescale()` is called before each `project.save()`.

## 常見問答

### Aspose.Tasks 能否呈現除資源使用與工作表之外的其他檢視？
Aspose.Tasks 支援呈現多種檢視，例如甘特圖、任務使用與行事曆檢視等。

### Aspose.Tasks 是否相容於不同版本的 Microsoft Project 檔案？
是的，Aspose.Tasks 支援廣泛的 Microsoft Project 檔案格式，包括 MPP、MPT 以及 XML 格式。

### 我可以使用 Aspose.Tasks 自訂呈現檢視的外觀嗎？
當然可以！Aspose.Tasks 提供豐富的選項，讓您依需求自訂呈現檢視的外觀與版面配置。

### Aspose.Tasks 是否需要在系統上安裝 Microsoft Project？
不需要，Aspose.Tasks 為獨立函式庫，無需安裝 Microsoft Project 即可運作。

### Aspose.Tasks 使用者是否可取得技術支援？
是的，Aspose.Tasks 使用者可透過 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 獲得技術支援。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-15  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose