---
date: 2026-03-24
description: 學習記憶體不足的處理方式以及如何使用 Aspose.Tasks Layout Builder 在 .NET 中儲存專案圖像。一步一步的指南，附有程式碼範例。
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks Layout Builder 處理記憶體不足 (C#)
url: /zh-hant/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks Layout Builder 處理記憶體不足

## 簡介

記憶體不足的處理是建立可靠 .NET 應用程式（處理大型專案檔）時的關鍵部分。當您使用 Aspose.Tasks Layout Builder 產生視覺化圖表時，特別是在複雜的甘特圖上，容易快速遇到記憶體相關的例外。在本教學中，我們將逐步說明如何 **處理記憶體例外**、**自訂甘特圖檢視**，以及 **安全儲存專案影像**，讓您的應用程式即使面對龐大排程也能保持回應。

## 快速解答
- **什麼是記憶體不足處理？** 在處理大量資料時管理記憶體使用量並捕獲 `OutOfMemoryException` 類型的錯誤。  
- **哪個 API 能協助？** Aspose.Tasks Layout Builder for .NET。  
- **典型情境？** 將高解析度的甘特圖渲染為 PNG。  
- **主要前提條件？** 已安裝 Aspose.Tasks 的 .NET（Framework 4.5+ 或 .NET 6）。  
- **如何捕獲錯誤？** 使用 `try…catch` 區塊捕獲 `ApsLayoutBuilderOutOfMemoryException` 及相關例外。  

## 先決條件

在深入程式碼之前，請確保您已具備以下條件：

1. **C# 基礎** – 您應該熟悉標準的 C# 語法。  
2. 已安裝 **Aspose.Tasks for .NET**。如果尚未加入，請從 [here](https://releases.aspose.com/tasks/net/) 下載。  
3. **開發環境 (IDE)**，例如 Visual Studio（或安裝 C# 擴充功能的 VS Code），用於編譯與執行範例。  

## 匯入命名空間

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 逐步指南

### 步驟 1：載入專案

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

此行程式碼將 **Blank2010.mpp** 載入 `Project` 實例，為視覺化做準備。

### 步驟 2：自訂甘特圖檢視

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

在此我們透過調整中間與底部時間刻度層級來 **自訂甘特圖檢視**。變更這些層級可減少一次渲染的資料量，從而緩解記憶體壓力。

### 步驟 3：設定影像儲存選項

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` 告訴 Aspose.Tasks 如何渲染圖表。我們選擇 PNG 作為輸出格式，並將時間刻度綁定至剛剛自訂的檢視。

### 步驟 4：將專案儲存為影像

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

`Save` 呼叫 **使用上述選項儲存專案影像**。若專案非常龐大，這裡最容易出現記憶體不足的情況。

### 步驟 5：處理例外

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

透過捕獲 `ApsLayoutBuilderOutOfMemoryException`，您可以優雅地 **處理記憶體例外**，提供清晰的訊息而非讓應用程式當機。第二個 catch 處理在渲染大型圖表時可能出現的位圖尺寸問題。

## 常見問題與解決方案

| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| **OutOfMemoryException** | 渲染極高解析度的影像會消耗超過程序可分配的記憶體。 | 降低影像尺寸、簡化時間刻度層級，或將圖表分割為多個影像。 |
| **BitmapInvalidSizeException** | 請求的位圖尺寸超過平台的最大限制。 | 在 `ImageSaveOptions` 中限制寬度/高度，或分段渲染。 |
| **Slow performance** | 大型專案檔需要大量處理。 | 在渲染前啟用 `project.Set(Prj.SaveToCache, true)`，或使用背景執行緒。 |

## 常見問答

### Q1：什麼是 Aspose.Tasks for .NET？

A1：Aspose.Tasks for .NET 是一套功能強大的 API，允許開發人員在 .NET 應用程式中以程式方式操作 Microsoft Project 檔案。

### Q2：如何取得 Aspose.Tasks 的臨時授權？

A2：您可前往 [this link](https://purchase.aspose.com/temporary-license/) 取得 Aspose.Tasks 的臨時授權。

### Q3：Aspose.Tasks 是否適合處理大型專案檔？

A3：是的，Aspose.Tasks 提供功能與最佳化，可有效處理大型專案檔，但開發人員仍需考慮記憶體管理策略。

### Q4：我能使用 Aspose.Tasks 自訂甘特圖的外觀嗎？

A4：當然可以！Aspose.Tasks 提供廣泛的功能，讓您依需求自訂甘特圖的外觀與版面配置。

### Q5：在哪裡可以找到更多 Aspose.Tasks 的協助與支援？

A5：您可於 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 獲得更多協助與支援，並與社群互動。

## 常見問題

**Q：如何在儲存專案影像時降低記憶體使用量？**  
A：降低影像解析度、限制時間刻度範圍，或將圖表分割為多個較小的區段儲存。

**Q：是否可以直接將影像串流至 Web 回應？**  
A：可以，您可使用 `project.Save(stream, options)`，並將串流寫入 HTTP 回應。

**Q：Aspose.Tasks 是否支援 .NET Core 與 .NET 5/6？**  
A：此函式庫完全相容於 .NET Core、.NET 5 與 .NET 6。

**Q：若優化後仍遇到記憶體不足錯誤，該怎麼辦？**  
A：考慮在具備更多 RAM 的機器上處理專案，或將渲染工作外移至背景服務。

**Q：我可以將甘特圖匯出為除 PNG 之外的格式嗎？**  
A：可以，`ImageSaveOptions` 除 PNG 外亦支援 JPEG、BMP 與 TIFF。

---

**最後更新：** 2026-03-24  
**測試環境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}