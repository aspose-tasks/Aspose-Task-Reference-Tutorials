---
title: 在 Aspose.Tasks 中處理影像保存
linktitle: 在 Aspose.Tasks 中處理影像保存
second_title: Aspose.Tasks .NET API
description: 了解如何使用逐步指南在 Aspose.Tasks for .NET 中處理影像保存。將圖像保存功能無縫整合到您的 .NET 應用程式中。
weight: 10
url: /zh-hant/net/advanced-concepts/image-saving/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中處理影像保存

## 介紹

在本教程中，我們將深入研究在 Aspose.Tasks for .NET 中處理影像保存的過程。 Aspose.Tasks 是一個功能強大的 API，使開發人員能夠以程式設計方式操作 Microsoft Project 檔案。使用專案文件時的常見任務是需要儲存圖像，其中可能包括圖表、圖形或其他視覺元素。我們將逐步分解該過程，確保整個過程的清晰度和理解性。

## 先決條件

在我們開始之前，請確保您符合以下先決條件：

1. Visual Studio：確保您的系統上安裝了 Visual Studio。
2.  Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET[這裡](https://releases.aspose.com/tasks/net/).
3. C# 的基本了解：熟悉 C# 程式語言基礎。

## 導入命名空間

首先，讓我們將必要的命名空間匯入到我們的專案中：

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 第 1 步：建立專案對象

首先從 Microsoft Project 檔案建立一個 Project 物件：

```csharp
var project = new Project("Project1.mpp");
```

## 第 2 步：定義儲存選項

定義項目的儲存選項，指定頁面和其他設定：

```csharp
var options = GetSaveOptions(1);
```

## 第 3 步：將項目另存為 HTML

使用指定選項將項目另存為 HTML：

```csharp
project.Save("document_out.html", options);
```

## 第四步：實現圖片保存回調

實作 ImageSavingCallback 介面來處理影像保存：

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        //圖像保存邏輯在這裡
    }
}
```

## 第五步：儲存圖片到指定目錄

在 ImageSave 方法中，指定將影像儲存到所需目錄的邏輯：

```csharp
if (args.FileName.EndsWith("png"))
{
    //保存嵌套資源
}
else
{
    //節省常規資源
}
```

## 步驟 6：指定儲存選項

指定儲存選項，包括 CSS、字型和圖片的回呼：

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //在此指定保存選項
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 結論

總之，在 Aspose.Tasks for .NET 中處理影像保存涉及定義保存選項和實作回呼以有效管理保存過程。透過遵循本教學中概述的步驟，您可以將圖像保存功能無縫整合到您的 .NET 應用程式中。

## 常見問題解答

### Q1：我可以使用Aspose.Tasks來操作除HTML之外的其他格式的專案檔案嗎？

A1：是的，Aspose.Tasks 支援多種格式，例如 PDF、XLSX 和 MPP。

### Q2：Aspose.Tasks 是否提供雲端儲存整合支援？

A2：是的，Aspose.Tasks 提供了與 Amazon S3 和 Google Drive 等流行雲端儲存服務搭配使用的 API。

### Q3：Aspose.Tasks 與.NET Core 相容嗎？

A3：是的，Aspose.Tasks 與 .NET Core 相容，可讓您開發跨平台應用程式。

### Q4：我可以自訂儲存影像的外觀嗎？

A4：是的，您可以透過修改回呼方法中的影像來儲存邏輯來自訂來儲存影像的外觀。

### Q5：Aspose.Tasks 是否提供評估目的的試用版？

 A5：是的，您可以從以下位置取得 Aspose.Tasks 的免費試用版：[這裡](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
