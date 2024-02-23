---
title: Aspose.Tasks 中的 CSS 保存參數
linktitle: Aspose.Tasks 中的 CSS 保存參數
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中儲存 CSS 參數以自訂 HTML 輸出。透過客製化 CSS 設定增強演示效果。
type: docs
weight: 20
url: /zh-hant/net/calendar-scheduling/css-saving-arguments/
---
## 介紹

在本教學中，我們將深入研究使用 Aspose.Tasks for .NET 儲存 CSS 參數的過程。層疊樣式表 (CSS) 對於定義 HTML 元素的表示至關重要。 Aspose.Tasks允許我們有效地操作和保存這些CSS屬性。

## 先決條件

在我們開始之前，請確保您具備以下先決條件：

1. 安裝：確保您已經安裝了 Aspose.Tasks for .NET。您可以從[網站](https://releases.aspose.com/tasks/net/).

2. 基礎：建議熟悉C#和.NET開發環境。

## 導入命名空間

首先，導入必要的命名空間：

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## 步驟 1：定義 CSS 儲存回調

首先，我們定義 CSS 保存回呼方法來處理 CSS 檔案的保存：

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        //在這裡實現你的 CSS 保存邏輯
    }
}
```

## 第 2 步：實現字體和圖像儲存回調

接下來同樣實作字體和圖片儲存回呼方法：

```csharp
public void FontSaving(FontSavingArgs args)
{
    //在這裡實現你的字體保存邏輯
}

public void ImageSaving(ImageSavingArgs args)
{
    //在這裡實現您的圖像保存邏輯
}
```

## 步驟 3：配置儲存選項

現在，配置 HTML 儲存選項以利用已實現的回呼：

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //配置 HTML 儲存選項
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 步驟 4： 使用自訂 CSS 儲存項目

最後，使用自訂的 CSS 設定儲存您的專案：

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## 結論

在本教學中，我們探討如何使用 Aspose.Tasks for .NET 來儲存 CSS 參數。透過定義CSS保存回調和設定HTML保存選項，我們可以根據我們的要求有效地操作CSS屬性。

## 常見問題解答

### Q1：什麼是 Aspose.Tasks for .NET？

A1：Aspose.Tasks for .NET 是一個功能強大的 .NET API，使開發人員能夠以程式設計方式使用 Microsoft Project 檔案。

### Q2：使用Aspose.Tasks儲存HTML檔案時可以自訂CSS屬性嗎？

A2：是的，您可以根據需要定義 CSS 儲存回呼來自訂 CSS 屬性。

### Q3：Aspose.Tasks for .NET 是否與所有版本的 Microsoft Project 檔案相容？

A3：Aspose.Tasks for .NET支援各種版本的Microsoft Project文件，確保不同環境下的相容性。

### 問題 4：在哪裡可以找到 Aspose.Tasks for .NET 的綜合文件？

 A4：您可以參考[文件](https://reference.aspose.com/tasks/net/)取得詳細資訊和範例。

### Q5：Aspose.Tasks for .NET 是否為開發人員提供支援？

 A5：是的，您可以透過 Aspose.Tasks 社群獲得支持[論壇](https://forum.aspose.com/c/tasks/15).