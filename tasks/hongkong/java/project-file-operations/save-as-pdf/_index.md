---
date: 2025-12-20
description: 學習如何在 Aspose.Tasks for Java 中匯出 PDF，這是一個簡易指南，可將 MPP 轉換為 PDF，並有效地儲存您的專案檔案。
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中匯出 PDF – 另存為 PDF
url: /zh-hant/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中匯出 PDF – 另存為 PDF

## Introduction
在本教學中，我們將向您展示 **如何在 Aspose.Tasks for Java 中匯出 PDF**，指導您將專案儲存為 PDF 的過程。使用 Aspose.Tasks，您可以高效地 **convert MPP to PDF**，確保相容性並方便團隊與利害關係人之間的共享。讓我們深入步驟，快速從任何專案檔案取得可列印的 PDF。

## Quick Answers
- **在 Aspose.Tasks 中「匯出 PDF」是什麼意思？** 它指的是將專案檔案（例如 MPP）轉換為保留視覺佈局的 PDF 文件。  
- **需要哪個版本的函式庫？** 任何支援 `PdfSaveOptions` 的 Aspose.Tasks for Java 版本（建議使用最新發行版）。  
- **此轉換是否需要授權？** 免費試用版可用於開發；正式環境需購買商業授權。  
- **我可以自訂 PDF 的外觀嗎？** 可以——您可以設定時間尺度、圖例以及其他 `PdfSaveOptions`。  
- **大型專案的轉換速度快嗎？** 通常在數秒內完成；效能取決於專案大小與所選選項。

## What is “how to export pdf” in the context of Aspose.Tasks?
在 Aspose.Tasks 中匯出 PDF 意味著將專案檔案（如 `.mpp`、`.xml` 或 `.xlsx`）生成一個與甘特圖、任務使用情況視圖或您配置的任何其他呈現格式相同的 PDF。這對於報告、文件或向非技術利害關係人分享唯讀視圖非常有用。

## Why Export Project Files to PDF?
- **通用可讀性：** PDF 可在任何裝置上開啟，無需原始專案軟體。  
- **專業呈現：** 保留格式、顏色與版面，適用於面向客戶的報告。  
- **易於分發：** 可透過電郵、內聯網或雲端儲存分享，無需擔心版本控制。  
- **合規與存檔：** PDF 適合長期保存與符合法規要求。

## Prerequisites
在開始之前，請確保您具備以下條件：

1. **Java Development Kit (JDK)：** 已在您的機器上安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java 函式庫：** 從官方網站[此處](https://releases.aspose.com/tasks/java/)下載函式庫。  
3. **專案檔案：** 準備好現有的專案檔案（例如 `HomeMovePlan.mpp`）以供轉換。

## Import Packages
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Step‑by‑Step Guide

### Step 1: Read the Input Project File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
將 `"Your Data Directory"` 替換為 `.mpp` 檔案所在的絕對路徑。此操作會將專案載入記憶體，以便您進行操作或匯出。

### Step 2: Save the Project as PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
上述程式碼執行簡單的 **save project as PDF** 操作，於同一資料夾中產生 `Project5.pdf`。

### Step 3: Fit Contents to Cell Size (Advanced PDF Save Options)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
此處示範如何使用 **pdf save options** 來控制版面：
- `setFitContent(true)` 強制內容適應儲存格寬度。  
- `setTimescale(Timescale.Months)` 將時間尺度設定為月份。  
- `setPresentationFormat(PresentationFormat.TaskUsage)` 選擇任務使用視圖。

### Step 4: Hide Legends (Cleaner Output)
```java
o.setLegendOnEachPage(false);
```
停用圖例可使 PDF 更加緊湊，特別是大型專案。

### Step 5: Save the Project with Applied Options
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
最後一步使用上述自訂選項寫入 PDF，產生無每頁圖例、以月份為時間尺度的精簡文件。

## Common Issues & Tips
- **檔案未找到：** 確認 `dataDir` 以檔案分隔符（`/` 或 `\\`）結尾，且指向正確目錄。  
- **空白頁面：** 檢查所選的 `PresentationFormat` 是否與您預期的視圖相符（例如甘特圖、任務使用）。  
- **大型檔案耗時較長：** 對於非常大的專案，可考慮設定 `o.setFitContent(false)` 以縮短處理時間。  

## Frequently Asked Questions

**問：Aspose.Tasks 是否相容所有 Java 版本？**  
**答：** 是，Aspose.Tasks 支援自 JDK 6 起的所有 Java 版本。

**問：我可以自訂 PDF 輸出的外觀嗎？**  
**答：** 當然！Aspose.Tasks 提供多種 **pdf save options**（如時間尺度、圖例可見性與呈現格式），讓您依需求調整 PDF。

**問：Aspose.Tasks 是否支援其他檔案格式的轉換？**  
**答：** 是的，您可以在 MPP、XML、XLSX 等多種格式之間轉換，使其成為一個多功能的工具，適用於 **convert mpp to pdf** 以及其他轉換。

**問：是否有 Aspose.Tasks 的試用版？**  
**答：** 有，您可從[此處](https://releases.aspose.com/)取得 Aspose.Tasks 免費試用版。

**問：我可以從哪裡取得 Aspose.Tasks 的支援？**  
**答：** 請前往官方的 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 獲得協助。

## Conclusion
透過本指南，您現在了解如何使用 Aspose.Tasks 從任何 Java 專案 **匯出 PDF**，無論是簡單的一行儲存，或是使用 `PdfSaveOptions` 的進階自訂。運用這些技巧產出精緻、可分享的 PDF，供報告、客戶簡報或存檔之用。

---

**最後更新：** 2025-12-20  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}