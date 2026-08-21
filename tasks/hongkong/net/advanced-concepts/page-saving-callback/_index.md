---
date: 2026-03-16
description: 學習如何在 Aspose.Tasks for .NET 中實作頁面儲存回呼，以自訂多頁文件輸出串流的處理方式。
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 在 Aspose.Tasks 中實作頁面儲存回調
url: /zh-hant/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中實作頁面保存回呼

## 簡介

在本教學中，您將學習如何在 Aspose.Tasks for .NET 中 **實作頁面保存回呼**。此強大功能允許您將多頁文件的每一頁導向自訂的串流，讓您完整掌控輸出如何儲存或進一步處理。

## 快速解答
- **頁面保存回呼的功能是什麼？** 它會將每個已渲染的頁面捕獲到獨立的串流，讓您可以個別處理。  
- **我可以匯出成哪種格式？** 任何 `ImageSaveOptions` 支援的格式，例如 PNG、JPEG、PDF。  
- **需要授權嗎？** 生產環境必須使用有效的 Aspose.Tasks 授權。  
- **可以在 .NET Core 中使用嗎？** 可以，Aspose.Tasks 完全支援 .NET Core 以及 .NET 5/6 以上版本。  
- **回呼是執行緒安全的嗎？** 回呼在執行渲染的同一執行緒上執行，遵循一般的執行緒安全規則。

## 什麼是 **實作頁面保存回呼**？
**實作頁面保存回呼** 模式讓您在 Aspose.Tasks 的保存流程中插入自訂邏輯。與直接寫入檔案不同，您會收到每一頁的 `Stream` 物件，從而可以將其儲存於記憶體、上傳至雲端，或進行其他後續處理。

## 為什麼要使用回呼將專案匯出為 PNG？
將專案匯出為 PNG 可取得每個甘特圖頁面的點陣圖，適合用於報告、電子郵件或嵌入網頁。使用回呼可讓您將每頁保存在獨立的 `MemoryStream` 中，避免在磁碟上產生暫存檔。

## 先決條件

1. **C# 知識** – 基本了解類別、介面與串流。  
2. **Aspose.Tasks for .NET** – 從 [此處](https://releases.aspose.com/tasks/net/) 下載並安裝。  
3. **IDE** – Visual Studio、Rider 或任何相容 .NET 的編輯器。

## 匯入命名空間

開始之前，匯入所需的命名空間：

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## 步驟 1：建立 Project 物件

將現有的 MPP 檔案載入 `Project` 實例：

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## 步驟 2：設定 Image Save Options

設定 `ImageSaveOptions` 以 PNG 輸出，並掛接自訂回呼：

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **專業提示：** 設定 `RenderToSinglePage = false` 可確保每個甘特圖頁面分別渲染，這對於回呼取得獨立串流至關重要。

## 步驟 3：使用回呼儲存專案

呼叫 `Save` 方法，傳入 `Stream.Null`，因為實際的串流由回呼提供：

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## 步驟 4：處理已儲存的頁面串流

儲存作業完成後，回呼會持有一組 `MemoryStream` 物件——每頁一個。您現在可以遍歷它們：

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## 步驟 5：實作自訂頁面保存回呼

建立一個 sealed 類別實作 `IPageSavingCallback`。此類別會捕獲每頁的串流，並將其存入清單以供稍後使用。

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## 常見問題與疑難排解

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| **未返回任何頁面** | `RenderToSinglePage` 保持為 `true`。 | 將 `RenderToSinglePage = false`，以產生分頁。 |
| **串流為空** | `KeepStreamOpen` 設為 `true`，但未在之後釋放。 | 保持為 `false`（預設），讓回呼自動關閉串流。 |
| **記憶體不足錯誤** | 大型專案會產生大量高解析度 PNG。 | 逐一處理串流或提升 VM 記憶體上限。 |

## 常見問與答

**Q1: 什麼是 Aspose.Tasks 中的頁面保存回呼？**  
A: 頁面保存回呼讓您在多頁文件的每一頁保存過程中截取，為該頁提供自訂的 `Stream`。

**Q2: 可以使用不同格式來保存頁面嗎？**  
A: 可以。變更 `SaveFileFormat` 後即可匯出為 PNG、JPEG、PDF、SVG 等格式。

**Q3: Aspose.Tasks 是否相容 .NET Core？**  
A: 完全相容。Aspose.Tasks 支援 .NET Core、.NET 5 以及 .NET 6。

**Q4: 如何處理頁面保存過程中的錯誤？**  
A: 將回呼邏輯包在 try/catch 區塊中，並記錄例外。`OnFinish` 方法是執行最終清理的好位置。

**Q5: 哪裡可以取得更多 Aspose.Tasks 的資源與支援？**  
A: 您可前往 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 尋求協助，於 [此處](https://reference.aspose.com/tasks/net/) 取得文件，或在 [Aspose.Tasks 官方網站](https://purchase.aspose.com/buy) 探索更多功能與授權方案。

**最後更新：** 2026-03-16  
**測試環境：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}