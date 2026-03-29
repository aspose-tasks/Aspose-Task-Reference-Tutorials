---
date: 2026-03-05
description: 學習如何儲存圖像、產生含圖像的 HTML，並使用 Aspose.Tasks for .NET 自訂圖像匯出。一步一步的指南，將專案儲存為
  HTML。
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: 如何使用 Aspose.Tasks for .NET 保存圖片
url: /zh-hant/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks for .NET 儲存圖像

## 介紹

在本教學中，您將會學會 **如何儲存圖像**，從 Microsoft Project 檔案中使用 Aspose.Tasks API for .NET 取得圖像。無論您是需要在報告中嵌入圖表、產生包含專案視覺的 HTML 頁面，或只是匯出圖形資源，以下步驟都會引導您完成整個流程——從設定 Project 物件到自訂圖像匯出回呼。

## 快速解答
- **“how to save images” 在 Aspose.Tasks 中是什麼意思？**  
  它指的是使用 `IImageSavingCallback` 介面來控制視覺資源寫入磁碟的位置與方式。
- **我可以將專案儲存為內嵌圖像的 HTML 嗎？**  
  可以，透過使用 `HtmlSaveOptions` 搭配圖像儲存回呼，您可以 **save project as HTML**（將專案儲存為 HTML），其中包含所有產生的圖像。
- **圖像匯出需要授權嗎？**  
  暫時的評估授權可用於測試；正式使用則需要完整授權。
- **支援哪些 .NET 版本？**  
  Aspose.Tasks for .NET 支援 .NET Framework 4.5 以上、.NET Core 3.1 以上，以及 .NET 5/6 以上。
- **可以自訂圖像匯出（格式、資料夾、命名）嗎？**  
  當然可以——回呼讓您完全掌控檔名、格式與儲存位置。

## 在 Aspose.Tasks 中「如何儲存圖像」是什麼意思？

儲存圖像指的是從 Project 檔案中擷取視覺元素（圖表、甘特條、資源圖形），並寫入圖像檔案（PNG、JPEG 等）。Aspose.Tasks 提供彈性的回呼機制，讓您自行決定儲存位置、命名慣例，甚至圖像格式。

## 為什麼使用 Aspose.Tasks 來儲存圖像？

- **完整程式化控制** – 無需手動 UI 操作。  
- **跨平台** – 透過 .NET Core 可在 Windows、Linux 與 macOS 上執行。  
- **高保真渲染** – 圖像保留與原始 Project 觀景相同的品質。  
- **簡易 HTML 產生** – 結合 `HtmlSaveOptions` 與圖像回呼即可自動 **generate HTML with images**（產生含圖像的 HTML）。

## 前置條件

1. 開發機器上已安裝 Visual Studio。  
2. 從 [here](https://releases.aspose.com/tasks/net/) 下載 Aspose.Tasks for .NET。  
3. 具備 C# 及 .NET 專案結構的基本認識。

## 匯入命名空間

首先，將所需的命名空間加入您的原始檔案中：

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 步驟 1：建立 Project 物件

載入您要處理的 Microsoft Project 檔案：

```csharp
var project = new Project("Project1.mpp");
```

## 步驟 2：定義儲存選項

建立同時保存我們圖像儲存回呼的 HTML 儲存選項：

```csharp
var options = GetSaveOptions(1);
```

## 步驟 3：將專案儲存為 HTML（save project as html）

現在將專案匯出為 HTML 檔案。HTML 中參考的圖像將由接下來定義的回呼產生：

```csharp
project.Save("document_out.html", options);
```

## 步驟 4：實作圖像儲存回呼（customize image export）

實作 `IImageSavingCallback` 介面。這裡是您 **自訂圖像匯出** 行為的地方：

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## 步驟 5：將圖像儲存至指定目錄

在 `ImageSaving` 方法內，決定每張圖像的儲存位置。以下範例會將 PNG 資源與其他格式區分開來：

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## 步驟 6：指定儲存選項（包含回呼）

為字型、CSS 與圖像掛接回呼。這確保每個視覺元素都能一致處理：

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|-------|-------|-----|
| 生成的 HTML 中未顯示圖像 | 回呼未指派有效的檔案路徑 | 確保 `args.Path` 指向可寫入的資料夾，並正確設定 `args.ImageStream`。 |
| PNG 檔案儲存為錯誤的副檔名 | 條件邏輯僅檢查 “png” 後綴 | 使用 `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` 以進行更健全的偵測。 |
| 移動檔案後 HTML 參考失效 | 移動輸出資料夾後相對路徑變更 | 保持 HTML 與圖像資料夾在同一位置，或相應更新 `options.ImageFolder`。 |

## 結論

依照上述步驟，您現在已掌握 **如何儲存圖像**、**save project as HTML**，以及 **自訂圖像匯出** 以符合應用程式的資料夾結構。此方法讓您能 **generate HTML with images**，輕鬆嵌入報告、文件入口網站或 Web 儀表板中。

## 常見問答

**Q1：我可以使用 Aspose.Tasks 操作除 HTML 之外的其他格式的專案檔案嗎？**  
A1：可以，Aspose.Tasks 支援多種格式，例如 PDF、XLSX 與 MPP。

**Q2：Aspose.Tasks 是否提供雲端儲存整合的支援？**  
A2：提供，Aspose.Tasks 提供用於操作如 Amazon S3 與 Google Drive 等熱門雲端儲存服務的 API。

**Q3：Aspose.Tasks 相容於 .NET Core 嗎？**  
A3：相容，Aspose.Tasks 支援 .NET Core，讓您能開發跨平台應用程式。

**Q4：我可以自訂已儲存圖像的外觀嗎？**  
A4：可以，您可透過在回呼方法中修改圖像儲存邏輯來自訂圖像的外觀。

**Q5：Aspose.Tasks 是否提供評估用的試用版？**  
A5：提供，您可從 [here](https://releases.aspose.com/) 取得 Aspose.Tasks 的免費試用版。

---

**最後更新：** 2026-03-05  
**測試環境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}