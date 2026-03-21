---
date: 2026-03-21
description: 學習如何在 Aspose.Tasks for .NET 中將專案另存為圖像時匯出圖像並處理 BitmapInvalidSizeException。包括將專案另存為圖像以及匯出專案為
  PNG 的步驟。
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 如何匯出圖像並處理無效尺寸例外
url: /zh-hant/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何匯出圖像 – 處理 Aspose.Tasks 中 Bitmap 的無效尺寸例外

在本教學中，您將學習如何使用 Aspose.Tasks for .NET 從 Microsoft Project 檔案 **匯出圖像**，以及更重要的，如何捕捉在此過程中可能拋出的 `BitmapInvalidSizeException`。將專案匯出為圖像是報表儀表板、文件或僅僅分享排程視覺快照的常見需求。完成本指南後，您將能夠可靠地 **將專案儲存為圖像**，甚至 **將專案匯出為 PNG** 格式，而不會發生意外崩潰。

## 快速解答
- **匯出圖像時可能拋出的例外是什麼？** `BitmapInvalidSizeException`  
- **範例使用的格式是什麼？** PNG (`SaveFileFormat.Png`)  
- **是否需要特別的授權？** 生產環境必須使用有效的 Aspose.Tasks 授權。  
- **我可以變更時間尺度嗎？** 可以 – 您可以設定時間尺度單位（分鐘、時、天等）。  
- **程式碼是否相容 .NET Core？** 完全相容 – 相同的 API 可在 .NET Framework 與 .NET Core 上執行。

## 什麼是 BitmapInvalidSizeException？
當計算出的圖像位圖尺寸超出支援範圍（例如寬度或高度為零，或超過內部限制）時，會拋出 `BitmapInvalidSizeException`。這通常發生在時間尺度或檢視設定導致產生過大或過小的圖像時。

## 為什麼要將專案匯出為圖像？
- **視覺化報表** – 可將甘特圖嵌入 PDF、Word 文件或網頁。  
- **跨平台分享** – PNG 檔案可在任何裝置上檢視，無需 Microsoft Project。  
- **效能** – 相較於完整的專案檔，圖像檔案更輕量，適合快速預覽。

## 前置條件
1. 具備 C# 與 .NET 開發的基本知識。  
2. 已安裝 Aspose.Tasks for .NET（NuGet 套件 `Aspose.Tasks`）。  
3. 準備好範例 Microsoft Project 檔案（例如 `Blank2010.mpp`）。  

## 匯入命名空間
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 步驟說明

### Step 1: Initialize the Project and Choose a View
首先，建立 `Project` 實例，並選取要呈現的檢視（此處使用第一個甘特圖檢視）。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Step 2: Configure Image Save Options (Export Project to PNG)
設定所需的圖像格式，並告訴 Aspose.Tasks 使用檢視中定義的時間尺度。

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Step 3: Adjust the Timescale Unit (Control Image Size)
變更時間尺度會影響位圖尺寸。在本範例中，我們使用 **分鐘** 以保持圖像大小在可接受範圍內。

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Step 4: Attempt to Save the Project as an Image
此行程式碼執行實際的 **將專案儲存為圖像** 操作。

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Step 5: Catch and Handle the BitmapInvalidSizeException
將儲存呼叫包在 `try / catch` 區塊中，讓您的應用程式在位圖尺寸無效時能優雅地回應。

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|-------|-------|----------|
| 調整時間尺度後仍拋出例外 | 時間尺度仍導致位圖過大 | 減少 `view.MiddleTimescaleTier.Count` 或改用較粗的 `TimescaleUnit`（例如 Hours）。 |
| 輸出檔案為空 | 檔案路徑不正確或缺少寫入權限 | 確認 `DataDir` 指向可寫入的資料夾，且若變更格式，檔名必須以 `.png` 結尾。 |
| 圖像品質差 | 預設 DPI 較低 | 將 `options.DpiX` 與 `options.DpiY` 設為較高值（例如 300）。 |

## 常見問答

**Q: 什麼情況會在 Aspose.Tasks 中拋出 BitmapInvalidSizeException？**  
A: 當計算出的位圖尺寸無效時——通常是因為時間尺度產生的圖像過大或寬度/高度為零。

**Q: 匯出圖像時可以自訂時間尺度嗎？**  
A: 可以。您可以依需求調整 `view.MiddleTimescaleTier.Unit` 與 `Count`，如本教學所示。

**Q: 除了 PNG，Aspose.Tasks 是否支援其他圖像格式？**  
A: 當然支援。`SaveFileFormat` 亦包含 JPEG、BMP、GIF 與 TIFF。只需在 `ImageSaveOptions` 中更改列舉值即可。

**Q: 在正式環境匯出圖像是否需要授權？**  
A: 必須。雖然評估模式下仍可使用，但商業授權會移除評估限制並提供完整支援。

**Q: 如何提升匯出 PNG 的品質？**  
A: 提高 DPI 設定（`options.DpiX` 與 `options.DpiY`）或調整檢視的時間尺度，以產生較大的位圖。

## 結論
依照上述步驟，您現在已掌握 **如何匯出圖像**、**如何將專案儲存為圖像**，以及如何優雅地處理 `BitmapInvalidSizeException`。這些技巧能讓您的報表流程更健全，確保在不同專案規模與時間尺度下，視覺匯出皆能可靠執行。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-03-21  
**測試環境：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose