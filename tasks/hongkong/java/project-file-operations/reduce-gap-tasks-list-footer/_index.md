---
date: 2026-05-20
description: 了解如何使用 Aspose.Tasks for Java 將專案匯出為 PDF、減少頁腳間距，並將專案另存為影像。輕鬆優化您的 MS Project
  版面配置。
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: 在 Aspose.Tasks 中將專案匯出為 PDF 並減少任務清單與頁腳之間的間距
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks 中將專案匯出為 PDF 並減少任務清單與頁腳之間的間距
url: /zh-hant/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 匯出專案為 PDF 並減少 Aspose.Tasks 中任務清單與頁腳之間的間距

## 簡介  
在本教學中，您將了解 **如何將專案匯出為 PDF**，同時減少 Microsoft Project 檔案中任務清單與頁腳之間的不必要空白。完成本指南後，您將能使用 Aspose.Tasks for Java 產生版面緊湊的乾淨 PDF、PNG 圖片以及 HTML 頁面。讓我們一步一步地走過整個流程，您將明白這對專業報告的重要性。

## 快速解答  
- **「export project to PDF」是什麼意思？** 它會將 MPP 檔案轉換為 PDF 文件，保留任務、時間軸與格式設定。  
- **為什麼要減少頁腳間距？** 較小的間距可產生更緊湊、外觀更專業的報告，特別是列印或網頁檢視的文件。  
- **我也可以將專案儲存為圖片嗎？** 可以 — Aspose.Tasks 支援 PNG、JPEG 以及其他影像格式。  
- **我需要特別的授權嗎？** 可使用免費試用版；商業授權則是正式環境的必要條件。  
- **需要哪個版本的 Java？** Java 8 或更高版本即可與目前的 Aspose.Tasks 函式庫相容。  

## 什麼是「export project to PDF」？  
將專案匯出為 PDF 會將內部的 MPP 結構轉換為可在任何裝置上開啟的可攜式文件，無需 Microsoft Project。這非常適合用於分享狀態報告、利害關係人更新或歸檔專案計畫。它會保留原始的版面配置、顏色與任務層級，確保 PDF 與來源檔案外觀完全相同。

## 為什麼要減少頁腳間距？  
預設的頁腳間距會產生不必要的空白，導致分頁問題與版面不平衡。減少間距可確保內容更有效率地利用頁面，使最終的 PDF 或圖片更易閱讀。更緊湊的版面亦能減少總頁數，從而降低列印成本並提升螢幕瀏覽的便利性。

## 如何減少任務清單與頁腳之間的間距？  
`setReduceFooterGap` 是一個布林屬性，用於控制匯出時的頁腳間距。  
Aspose.Tasks 為影像、PDF 與 HTML 儲存操作提供 `setReduceFooterGap(true)` 選項。啟用此旗標會指示引擎壓縮最後一列任務與頁腳之間的空間。設定為 true 時，渲染器會自動裁減邊距而不會截斷任何任務資料，從而產生更整潔的頁面版面。

## 使用 Aspose.Tasks 將專案儲存為圖片  
`ImageSaveOptions` 用於設定專案渲染為影像檔案的方式。  
`ImageSaveOptions` 類別允許您將排程快照匯出為 PNG、JPEG 或 BMP。當您同時啟用 `setReduceFooterGap(true)` 時，產生的影像會映射緊湊的 PDF 版面，為簡報或儀表板提供乾淨的視覺效果。

## Java 專案匯出為 PDF  
以下各節將逐步說明完整的 **java project export** 工作流程，從載入 MPP 檔案到以三種不同格式儲存。

## 先決條件
在開始之前，請確保您已具備以下先決條件：
1. Java Development Kit (JDK) – 版本 8 或更新。  
2. Aspose.Tasks for Java Library – 從 [here](https://releases.aspose.com/tasks/java/) 下載。  

## 匯入套件  
在深入程式碼部分之前，先匯入必要的套件：

```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## 步驟 1：提供資料目錄的路徑  
```java
String dataDir = "Your Data Directory";
```  
確保將 `"Your Data Directory"` 替換為實際資料目錄的路徑，該目錄中放置了您的 Microsoft Project 檔案（本例中的 `HomeMovePlan.mpp`）。

## 步驟 2：讀取 MPP 檔案  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
此程式碼行會讀取名為 `HomeMovePlan.mpp` 的 Microsoft Project 檔案。

## 步驟 3：設定 ImageSaveOptions（將專案儲存為圖片）  
`ImageSaveOptions` 用於設定專案渲染為影像檔案的方式。  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
設定影像儲存選項，將 `ReduceFooterGap` 設為 `true` 以減少任務清單與頁腳之間的間距。

## 步驟 4：儲存為圖片  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
使用先前設定的選項將專案儲存為圖片。

## 步驟 5：設定 PdfSaveOptions（匯出專案為 PDF）  
`PdfSaveOptions` 指定將專案匯出為 PDF 格式的設定。  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
定義 PDF 儲存選項，確保將 `ReduceFooterGap` 設為 `true`。

## 步驟 6：儲存為 PDF  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
使用先前設定的選項將專案儲存為 PDF。

## 步驟 7：設定 HtmlSaveOptions  
`HtmlSaveOptions` 控制將專案轉換為 HTML 的行為，包含樣式與版面配置選項。  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
指定 HTML 儲存選項，將 `ReduceFooterGap` 設為 `true`。

## 步驟 8：儲存為 HTML  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
使用先前設定的選項將專案儲存為 HTML 檔案。

## 常見使用情境與技巧  
- **利害關係人報告：** 匯出為 PDF 並減少頁腳間距，以保持報告簡潔且適合列印。  
- **儀表板快照：** 當需要為 Power BI 或 Confluence 提供快速視覺時，使用影像匯出。  
- **網頁發布：** HTML 匯出保留互動性，且可直接嵌入內部入口網站。  
- **專業提示：** 對於非常大型的專案，可將 `ImageSaveOptions` 中的 `Resolution` 提升至 300 dpi，以保持清晰度，同時仍受益於減少的間距。

## 常見問題 (其他)

**Q: 減少頁腳間距如何影響分頁？**  
A: 它會減少每頁底部的空白，使更多任務能容納於單一頁面，從而降低總頁數。

**Q: 我可以只對單一頁面套用相同的間距縮減設定嗎？**  
A: 可以，透過在 `ImageSaveOptions` 中設定 `setRenderToSinglePage(true)`，即可在仍減少間距的同時控制分頁。

**Q: `setReduceFooterGap` 選項是否支援其他輸出格式？**  
A: 目前僅支援 PNG、PDF 與 HTML 匯出。對於其他格式，可能需要手動調整版面。

**Q: 如果我的專案包含自訂欄位，會被保留嗎？**  
A: 所有自訂欄位在匯出時皆會保留；版面調整僅影響間距，不會影響資料。

**Q: 此函式庫能有效處理大型專案嗎？**  
A: Aspose.Tasks 以串流方式處理資料，能在不將整個檔案載入記憶體的情況下處理數百頁的 MPP 檔案；但在匯出高解析度影像時，請確保分配足夠的堆積空間。

---

**最後更新：** 2026-05-20  
**測試環境：** Aspose.Tasks 24.11 for Java  
**作者：** Aspose

## 相關教學

- [將專案儲存為圖片 – 24bppRgb 格式與 Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [將專案儲存為範本、CSV 與文字與 Aspose.Tasks for Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [如何建立 MPP 檔案 – 使用 Aspose.Tasks 建立與儲存空白專案為 MPP 格式](/tasks/java/project-configuration/create-save-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}