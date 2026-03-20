---
date: 2025-12-17
description: 學習如何使用 Aspose.Tasks for Java 將專案儲存為影像並變更影像解析度。此逐步指南展示以 24bppRgb 格式呈現
  MS Project 資料。
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 將專案儲存為圖像 – 24bppRgb 格式
url: /zh-hant/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將專案另存為影像 – 24bppRgb 格式與 Aspose.Tasks

## 簡介
在本教學中，您將學習如何使用 Aspose.Tasks for Java 以 24bppRgb 像素格式 **將專案另存為影像**。將 MS Project 資料渲染為影像在需要分享排程的視覺快照、在報告中嵌入時間軸，或為專案入口網站產生縮圖時非常方便。我們亦會示範如何 **變更影像解析度 java** 以符合您的品質需求。

## 快速答覆
- **我可以將專案渲染為影像嗎？** 是的，Aspose.Tasks 允許您將專案另存為 TIFF、PNG、JPEG 等格式。  
- **哪種像素格式提供最佳的色彩深度？** `Format24bppRgb` 提供真彩色（24 位元）影像。  
- **如何調整影像解析度？** 在 `ImageSaveOptions` 上使用 `setHorizontalResolution` 和 `setVerticalResolution`。  
- **生產環境是否需要授權？** 非評估用途必須購買商業授權。  
- **此功能是否相容所有 Java 版本？** 可在 Java 8 及更新版本上運作。

## 什麼是「將專案另存為影像」？
將專案另存為影像會將 Microsoft Project 檔案（`.mpp`）的視覺呈現轉換為點陣格式（例如 TIFF）。產生的檔案可在瀏覽器中顯示、插入文件，或直接列印，無需原始的 Project 應用程式。

## 為什麼使用 24bppRgb 格式？
24bppRgb 像素格式為每個像素分配 8 位元的紅、綠、藍，提供無透明通道的真彩色品質。這對於色彩還原度重要的高解析度報告非常理想，同時相較於 32 位元格式能保持檔案大小在合理範圍。

## 先決條件
在開始之前，請確保您具備以下條件：

1. **Java Development Kit (JDK)** – 已在您的機器上安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 [here](https://releases.aspose.com/tasks/java/) 下載並安裝。  
3. **Basic Java knowledge** – 熟悉 Java 語法與專案設定將有助於您理解程式碼片段。

## 匯入套件
首先，將所需的 Aspose.Tasks 類別匯入您的 Java 專案：

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 逐步指南

### 步驟 1：定義資料目錄
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
將 `"Your Data Directory"` 替換為 `.mpp` 檔案所在的絕對路徑。

### 步驟 2：載入專案檔案
```java
Project project = new Project(dataDir + "project.mpp");
```
此行程式碼讀取 Microsoft Project 檔案（`project.mpp`），並建立 Aspose.Tasks 可操作的 `Project` 物件。

### 步驟 3：設定影像儲存選項
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
在此我們將輸出格式設定為 TIFF，指定 **72 dpi** 解析度（您可以依需求變更這些數值——這就是 **變更影像解析度 java** 的地方），並選擇 24bppRgb 像素格式以產生真彩色輸出。

### 步驟 4：將專案資料另存為影像
```java
project.save(dataDir + "resFile.tif", options);
```
`save` 方法會使用上述選項將渲染的影像寫入 `resFile.tif`。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **影像空白** | 專案檢視可能為空。 | 在儲存前呼叫 `project.setDefaultView(ViewType.Gantt);`。 |
| **影像品質低** | 解析度設定過低。 | 提高 `setHorizontalResolution` 和 `setVerticalResolution`（例如 150 dpi）。 |
| **不支援的像素格式** | 使用較舊的 Aspose.Tasks 版本。 | 升級至最新的 Aspose.Tasks for Java 版本。 |

## 結論
您現在已了解如何使用 24bppRgb 格式 **將專案另存為影像**，並透過 Aspose.Tasks for Java 調整解析度。此方法可讓您產生清晰、色彩精確的專案排程視覺呈現，以供分享、報告或存檔之用。

## 常見問答
### Q: 我可以將專案資料渲染為其他影像格式嗎？
A: 可以，Aspose.Tasks 支援將專案資料渲染為多種影像格式，例如 PNG、JPEG、BMP 等。

### Q: Aspose.Tasks 是否相容不同版本的 MS Project？
A: 可以，Aspose.Tasks 支援多個版本的 MS Project，包括 2003、2007、2010、2013 及 2016。

### Q: 我可以自訂渲染影像的解析度與像素格式嗎？
A: 可以，您可使用 Aspose.Tasks 依需求自訂解析度與像素格式。

### Q: Aspose.Tasks 商業使用是否需要授權？
A: 是的，商業使用 Aspose.Tasks 必須購買授權。您可從 [here](https://purchase.aspose.com/temporary-license/) 取得測試用的臨時授權。

### Q: 我可以從哪裡取得 Aspose.Tasks 的支援？
A: 您可於 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 獲得支援。

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}