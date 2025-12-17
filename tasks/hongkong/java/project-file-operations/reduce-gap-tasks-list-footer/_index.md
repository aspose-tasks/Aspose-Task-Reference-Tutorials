---
date: 2025-12-17
description: 學習如何使用 Aspose.Tasks for Java 將專案匯出為 PDF、減少頁腳間距，並將專案另存為圖像。輕鬆優化您的 MS Project
  版面配置。
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 將專案匯出為 PDF 並縮小任務清單與頁腳之間的間距（Aspose.Tasks）
url: /zh-hant/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 匯出專案為 PDF 並縮減 Aspose.Tasks 中任務清單與頁腳之間的間距

## 介紹  
在本教學中，您將了解 **如何將專案匯出為 PDF**，同時減少 Microsoft Project 檔案中任務清單與頁腳之間的不必要空白。完成本指南後，您將能使用 Aspose.Tasks for Java 產生版面緊湊的乾淨 PDF、PNG 圖片以及 HTML 頁面。讓我們一步一步來說明整個流程。

## 快速回答  
- **「匯出專案為 PDF」是什麼意思？** 它會將 MPP 檔案轉換為 PDF 文件，保留任務、時間軸與格式。  
- **為什麼要縮減頁腳間距？** 較小的間距可產生更緊密、更加專業的報告，特別是列印或在網頁上檢視的文件。  
- **我可以將專案另存為圖片嗎？** 可以 — Aspose.Tasks 支援 PNG、JPEG 以及其他圖片格式。  
- **我需要特別的授權嗎？** 有提供免費試用版；正式使用時需購買商業授權。  
- **需要哪個版本的 Java？** Java 8 或更高版本即可與目前的 Aspose.Tasks 函式庫相容。  

## 什麼是「匯出專案為 PDF」？  
將專案匯出為 PDF 會將內部的 MPP 結構轉換為可在任何裝置上開啟的可攜式文件，無需安裝 Microsoft Project。這非常適合用於分享狀態報告、利害關係人更新或歸檔專案計畫。

## 為什麼要縮減頁腳間距？  
預設的頁腳間距會產生不必要的空白，導致分頁問題與版面不平衡。縮減間距可確保內容有效利用頁面，使最終的 PDF 或圖片更易閱讀。

## 如何縮減任務清單與頁腳之間的間距？  
Aspose.Tasks 為影像、PDF 與 HTML 的儲存操作提供 `setReduceFooterGap(true)` 選項。啟用此旗標即告訴引擎壓縮最後一列任務與頁腳之間的空間。

## 使用 Aspose.Tasks 將專案另存為圖片  
如果您需要排程的視覺快照，可在套用相同縮減間距設定的同時 **將專案另存為圖片**（PNG）。

## Java 專案匯出為 PDF  
以下章節將說明完整的 **java 專案匯出** 工作流程，從載入 MPP 檔案到以三種不同格式儲存。

## 前置條件
在開始之前，請確保您具備以下前置條件：
1. Java Development Kit (JDK) – 版本 8 或以上。  
2. Aspose.Tasks for Java 函式庫 – 可從 [here](https://releases.aspose.com/tasks/java/) 下載。

## 匯入套件
在進入程式碼部分之前，先匯入必要的套件：

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
請將 `"Your Data Directory"` 替換為實際資料目錄的路徑，該目錄中放置了您的 Microsoft Project 檔案（本例中的 `HomeMovePlan.mpp`）。

```java
String dataDir = "Your Data Directory";
```

## 步驟 2：讀取 MPP 檔案
此行程式碼會讀取名為 `HomeMovePlan.mpp` 的 Microsoft Project 檔案。

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## 步驟 3：設定 ImageSaveOptions（將專案另存為圖片）
設定影像儲存選項，將 `ReduceFooterGap` 設為 `true` 以縮減任務清單與頁腳之間的間距。

```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```

## 步驟 4：另存為圖片
使用已設定的選項將專案另存為圖片。

```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```

## 步驟 5：設定 PdfSaveOptions（匯出專案為 PDF）
定義 PDF 儲存選項，確保將 `ReduceFooterGap` 設為 `true`。

```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```

## 步驟 6：另存為 PDF
使用已設定的選項將專案另存為 PDF。

```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```

## 步驟 7： HtmlSaveOptions
指定 HTML 儲存選項，將 `ReduceFooterGap` 設為 `true`。

```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```

## 步驟 8：另存為 HTML
使用已設定的選項將專案另存為 HTML 檔案。

```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```

## 結論  
總結來說，使用 Aspose.Tasks for Java 縮減 Microsoft Project 檔案中任務清單與頁腳之間的間距是一個簡單的流程。依照本教學所列步驟，您即可有效 **匯出專案為 PDF**、將其另存為圖片，或產生 HTML，同時保持版面緊湊且專業。

## 常見問題

### Q: Aspose.Tasks 是否相容所有版本的 Microsoft Project？
A: Aspose.Tasks 支援 Microsoft Project 2003-2019 格式，確保在各版本之間的相容性。

### Q: 我可以自訂專案文件中頁腳的外觀嗎？
A: 可以，Aspose.Tasks 提供廣泛的選項來自訂頁腳外觀，包括縮減間距與調整內容位置。

### Q: Aspose.Tasks 是否支援除 PNG、PDF、HTML 之外的其他格式儲存專案？
A: 可以，Aspose.Tasks 支援多種格式，包括 XLSX、XML、MPP 等等。

### Q: 是否有 Aspose.Tasks 的試用版？
A: 可以，您可從 [here](https://releases.aspose.com/) 下載 Aspose.Tasks 的免費試用版。

### Q: 使用 Aspose.Tasks 時若遇到問題，該向何處尋求支援？
A: 您可在 Aspose.Tasks 社群論壇取得協助，請前往 [here](https://forum.aspose.com/c/tasks/15)。

## 常見問答（補充）

**Q: 縮減頁腳間距會如何影響分頁？**  
A: 它會減少每頁底部的空白，使更多任務能容納於單一頁面，從而降低總頁數。

**Q: 我可以只對單一頁面套用相同的縮減間距設定嗎？**  
A: 可以，透過在 `ImageSaveOptions` 中設定 `setRenderToSinglePage(true)`，即可在仍縮減間距的同時控制分頁。

**Q: `setReduceFooterGap` 選項是否支援其他輸出格式？**  
A: 目前僅支援 PNG、PDF 與 HTML 匯出。其他格式可能需要手動調整版面。

**Q: 若我的專案包含自訂欄位，是否會被保留？**  
A: 所有自訂欄位在匯出時皆會保留；版面調整僅影響間距，不會影響資料。

**Q: 此函式庫能有效處理大型專案嗎？**  
A: Aspose.Tasks 以串流方式處理資料，能處理大型 MPP 檔案；但在匯出高解析度圖片時，請確保有足夠的記憶體。

---

**最後更新：** 2025-12-17  
**測試環境：** Aspose.Tasks 24.11 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}