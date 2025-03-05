---
title: 在 Aspose.Tasks 中另存為 PDF
linktitle: 在 Aspose.Tasks 中另存為 PDF
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 將專案檔轉換為 PDF。簡單的步驟即可實現高效率轉換。
type: docs
weight: 17
url: /zh-hant/java/project-file-operations/save-as-pdf/
---
## 介紹
在本教學中，我們將引導您完成使用 Aspose.Tasks for Java 將專案儲存為 PDF 的過程。使用Aspose.Tasks，您可以有效地將專案檔案轉換為PDF格式，確保相容性和易於共用。讓我們深入了解步驟：
## 先決條件
在開始之前，請確保您具備以下條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
2.  Aspose.Tasks for Java Library：下載並安裝 Aspose.Tasks 函式庫。你可以找到下載鏈接[這裡](https://releases.aspose.com/tasks/java/).
3. 專案文件：準備好要轉換為 PDF 的專案文件（例如 HomeMovePlan.mpp）。

## 導入包
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## 第 1 步：讀取輸入項目文件
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
確保更換`"Your Data Directory"`包含專案檔案的資料目錄的路徑。
## 步驟 2：將項目另存為 PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
此程式碼片段將項目另存為 PDF 文件，名稱為「Project5.pdf」。
## 步驟 3： 使內容適合單元格大小
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
在這裡，我們設定保存 PDF 的選項，包括適合的內容、時間刻度和簡報格式。
## 第 4 步：隱藏圖例
```java
o.setLegendOnEachPage(false);
```
此步驟隱藏 PDF 每頁上的圖例。
## 第 5 步：使用應用程式的選項儲存項目
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
最後，此程式碼將套用了選項的項目儲存到 PDF 檔案中。

## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 將專案另存為 PDF。透過執行這些簡單的步驟，您可以有效地轉換專案文件，以便於共用和分發。
## 常見問題解答
### Q：Aspose.Tasks 是否與所有版本的 Java 相容？
答：是的，Aspose.Tasks 支援從 JDK 6 及更高版本開始的 Java 版本。
### Q：我可以自訂 PDF 輸出的外觀嗎？
答：當然！ Aspose.Tasks 提供了各種選項來根據您的要求自訂 PDF 輸出。
### Q：Aspose.Tasks 是否支援其他檔案格式轉換？
答：是的，Aspose.Tasks 支援多種檔案格式，包括 MPP、XML、XLSX 等。
### Q：Aspose.Tasks 有試用版嗎？
答：是的，您可以從以下位置獲得 Aspose.Tasks 的免費試用版：[這裡](https://releases.aspose.com/).
### Q：我可以在哪裡獲得 Aspose.Tasks 的支援？
答： 如需支援和協助，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).