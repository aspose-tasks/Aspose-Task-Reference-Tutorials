---
title: 減少 Aspose.Tasks 中任務清單和頁腳之間的間隙
linktitle: 減少 Aspose.Tasks 中任務清單和頁腳之間的間隙
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 縮小 MS Project 任務清單和頁尾之間的間隙。輕鬆優化專案文檔佈局。
weight: 10
url: /zh-hant/java/project-file-operations/reduce-gap-tasks-list-footer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 減少 Aspose.Tasks 中任務清單和頁腳之間的間隙

## 介紹
在本教程中，我們將深入研究如何使用 Aspose.Tasks for Java 縮小 Microsoft Project 檔案中任務清單和頁腳之間的間隙。透過執行這些步驟，您將能夠輕鬆優化專案文件的佈局。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
2.  Aspose.Tasks for Java 函式庫：下載 Aspose.Tasks for Java 函式庫並將其包含在您的專案中。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/java/).

## 導入包
在深入編碼部分之前，讓我們先導入必要的套件：
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
## 第 1 步：提供資料目錄的路徑
```java
String dataDir = "Your Data Directory";
```
確保更換`"Your Data Directory"`與您的 Microsoft Project 檔案所在的實際資料目錄的路徑 (`HomeMovePlan.mpp`在此範例中）位於。
## 步驟2：讀取MPP文件
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
這行程式碼讀取名為的 Microsoft Project 文件`HomeMovePlan.mpp`.
## 步驟 3： 設定 ImageSaveOptions
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
配置影像儲存選項，設定`ReduceFooterGap`到`true`減少任務清單和頁腳之間的間隙。
## 第 4 步：另存為影像
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
使用配置的選項將項目另存為映像。
## 步驟5：設定PdfSaveOptions
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
定義 PDF 儲存選項，確保設定`ReduceFooterGap`到`true`.
## 第 6 步：另存為 PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
使用配置的選項將項目另存為 PDF。
## 步驟7：設定HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); //設定為真
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
指定 HTML 儲存選項、設定`ReduceFooterGap`到`true`.
## 第 8 步：另存為 HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
使用配置的選項將項目儲存為 HTML 檔案。

## 結論
總之，使用 Aspose.Tasks for Java 縮小 Microsoft Project 檔案中的任務清單和頁尾之間的間隙是一個簡單的過程。透過遵循本教學中概述的步驟，您可以有效地優化專案文件的佈局。

## 常見問題解答

### Q：Aspose.Tasks 是否與所有版本的 Microsoft Project 相容？

答：Aspose.Tasks 支援 Microsoft Project 2003-2019 格式，確保各個版本之間的相容性。

### Q：我可以自訂專案文件中頁腳的外觀嗎？

答：是的，Aspose.Tasks 提供了廣泛的選項來自訂頁腳的外觀，包括減少間隙和調整內容放置。

### Q：Aspose.Tasks 是否支援以 PNG、PDF 和 HTML 以外的格式儲存項目？

答：是的，Aspose.Tasks 支援多種格式，包括 XLSX、XML 和 MPP 等。

### Q：Aspose.Tasks 有試用版嗎？

答：是的，您可以從以下位置下載 Aspose.Tasks 的免費試用版：[這裡](https://releases.aspose.com/).

### Q：如果在使用 Aspose.Tasks 時遇到任何問題，我可以在哪裡獲得支援？

答：您可以從 Aspose.Tasks 社群論壇獲得協助[這裡](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
