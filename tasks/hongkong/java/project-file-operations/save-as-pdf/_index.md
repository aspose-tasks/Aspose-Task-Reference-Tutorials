---
date: 2026-03-27
description: 學習如何使用 Aspose.Tasks for Java 將專案儲存為 PDF，簡單指南教您將 MPP 轉換為 PDF，並高效匯出專案檔案。
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 將專案另存為 PDF – 匯出指南
url: /zh-hant/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 將專案另存為 PDF – 匯出指南

## 簡介
在本教學中，您將了解 **how to save project as pdf** 使用 Aspose.Tasks for Java 的方法。我們會從單行轉換說明到進階 PDF 客製化，帶您一步步將任何 MPP（或其他支援格式）轉換成精緻、可分享的 PDF 文件。無論您需要快速列印的報告，或是完整樣式的甘特圖，這些步驟都能讓您迅速完成。

## 快速解答
- **What does “export PDF” mean in Aspose.Tasks?** 這表示將專案檔案（例如 MPP）轉換為 PDF 文件，並保留視覺版面配置。  
- **Which library version is required?** 任何支援 `PdfSaveOptions` 的 Aspose.Tasks for Java 版本皆可（建議使用最新發行版）。  
- **Do I need a license for this conversion?** 開發階段可使用免費試用版；正式上線則需購買商業授權。  
- **Can I customize the PDF appearance?** 可以——您可以設定時間尺度、圖例以及其他 `PdfSaveOptions`。  
- **Is the conversion fast for large projects?** 通常只需數秒，效能取決於專案大小與所選選項。

## 在 Aspose.Tasks 中，「save project as pdf」是什麼？
使用 Aspose.Tasks 將專案另存為 PDF，意指將專案檔（如 `.mpp`、`.xml` 或 `.xlsx`）產生一份 PDF，內容會映射甘特圖、工作使用情況或您自行設定的任何呈現格式。此功能適合用於報告、文件化或向非技術利害關係人分享唯讀視圖。

## 為什麼要將甘特圖匯出為 PDF？
- **通用可讀性：** PDF 可在任何裝置上開啟，無需原始專案軟體。  
- **專業呈現：** 保留顏色、字型與版面，適合客戶報告。  
- **易於分發：** 透過電郵、內部網路或雲端儲存分享，無需版本控制。  
- **合規與存檔：** PDF 是長期保存與符合法規要求的理想格式。

## 先決條件
在開始之前，請確保您已具備以下項目：

1. **Java Development Kit (JDK)：** 已在電腦上安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java Library：** 從官方網站[此處](https://releases.aspose.com/tasks/java/)下載程式庫。  
3. **專案檔案：** 準備好現有的專案檔（例如 `HomeMovePlan.mpp`）以供轉換。

## 匯入套件
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## 逐步指南

### 步驟 1：讀取輸入專案檔案
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
將 `"Your Data Directory"` 替換為 `.mpp` 檔案所在的絕對路徑。此步驟會將專案載入記憶體，以便後續操作或匯出。

### 步驟 2：將專案另存為 PDF（基本轉換）
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
上述程式碼執行簡單的 **save project as pdf** 操作，於同一資料夾產生 `Project5.pdf`。

### 步驟 3：將內容調整至儲存格大小（進階 PDF 儲存選項）
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
此範例示範如何使用 **pdf save options** 來控制版面：
- `setFitContent(true)` 強制內容符合儲存格寬度。  
- `setTimescale(Timescale.Months)` 將時間尺度設定為月份。  
- `setPresentationFormat(PresentationFormat.TaskUsage)` 選擇「工作使用情況」視圖。

### 步驟 4：隱藏圖例（更乾淨的輸出）
```java
o.setLegendOnEachPage(false);
```
停用圖例可讓 PDF 更為緊湊，特別是大型專案時。

### 步驟 5：使用套用的選項儲存專案
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
最後一步使用先前自訂的選項寫入 PDF，產生不含每頁圖例、以月份為尺度的乾淨文件。

## 匯出甘特圖至 PDF – 自訂樣式
若只想匯出甘特圖並套用特定外觀，將 `PresentationFormat` 設為 `GanttChart`，並調整如 `setBarColor` 或 `setShowCriticalTasks` 等額外選項。此方式讓您 **export gantt chart to pdf** 時，能完整掌控視覺元素。

## 常見問題與技巧
- **找不到檔案：** 確認 `dataDir` 以檔案分隔符（`/` 或 `\\`）結尾，且指向正確目錄。  
- **空白頁面：** 檢查所選 `PresentationFormat` 是否與您預期的視圖相符（例如 Gantt、Task Usage）。  
- **大型檔案耗時較長：** 對於極大專案，可考慮設定 `o.setFitContent(false)` 以縮短處理時間。

## 常見問答

**Q: Aspose.Tasks 是否相容所有 Java 版本？**  
A: 是，Aspose.Tasks 支援從 JDK 6 起的所有 Java 版本。

**Q: 我可以客製化 PDF 輸出的外觀嗎？**  
A: 當然！Aspose.Tasks 提供多種 **pdf save options**，如時間尺度、圖例可見性與呈現格式，讓您依需求調整 PDF。

**Q: Aspose.Tasks 支援其他檔案格式的轉換嗎？**  
A: 支援。您可在 MPP、XML、XLSX 等多種格式間互相轉換，方便執行 **convert mpp to pdf** 及其他轉換作業。

**Q: 是否有 Aspose.Tasks 的試用版？**  
A: 有，您可從[此處](https://releases.aspose.com/)取得免費試用。

**Q: 我可以在哪裡取得 Aspose.Tasks 的支援？**  
A: 請前往官方 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 取得協助。

## 結論
依照本指南，您現在已掌握如何使用 Aspose.Tasks for Java 從任意 Java 專案 **how to save project as pdf**，無論是單行儲存或透過 `PdfSaveOptions` 進行進階客製化。利用這些技巧，您可以產出精緻、可分享的 PDF，供報告、客戶簡報或長期存檔使用。

---

**最後更新：** 2026-03-27  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}