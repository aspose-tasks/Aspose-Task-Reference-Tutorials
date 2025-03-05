---
title: 處理 Aspose.Tasks 中位圖的無效大小異常
linktitle: 處理 Aspose.Tasks 中位圖的無效大小異常
second_title: Aspose.Tasks .NET API
description: 了解將專案儲存為映像時如何處理 Aspose.Tasks for .NET 中的 BitmapInvalidSizeException。具有逐步指導的綜合教程。
type: docs
weight: 22
url: /zh-hant/net/advanced-features/bitmap-invalid-size-exception/
---
## 介紹

在本教程中，我們將深入研究如何處理`BitmapInvalidSizeException`使用 Aspose.Tasks for .NET 時。 Aspose.Tasks 是一個功能強大的函式庫，可讓開發人員以程式設計方式操作 Microsoft Project 文件，從而實現將專案儲存為映像等任務。然而，有時，當嘗試將項目另存為圖像時，我們可能會遇到`Invalid Size Exception`與點陣圖相關。本教程旨在指導您有效地捕獲和處理此異常。

## 先決條件

在繼續本教學之前，請確保您具備以下先決條件：
1. 對 C# 程式語言有基本了解。
2. 安裝了 .NET 的 Aspose.Tasks。
3. 熟悉使用 Microsoft Project 文件。

## 導入命名空間

開始之前，請確保導入必要的命名空間：
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 第 1 步：初始化項目並定義視圖

首先，初始化一個`Project`物件並定義一個視圖，例如`GanttChartView`.

```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

## 步驟 2：指定影像儲存選項

接下來，指定儲存影像的選項，包括格式和時間刻度。

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

## 步驟 3：設定時間刻度單位和計數

根據您的要求調整時間刻度單位和計數。在此範例中，我們將時間刻度設定為分鐘。

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

## 第 4 步：將項目另存為圖像

嘗試使用指定選項將項目另存為映像。

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

## 第 5 步：捕獲並處理異常

實施異常處理以捕獲`BitmapInvalidSizeException`如果它發生在圖像保存過程中。

```csharp
try
{
    //嘗試將項目另存為圖像
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    //處理例外
    Console.WriteLine(ex.Message);
}
```

## 結論

總之，處理`BitmapInvalidSizeException`在 Aspose.Tasks for .NET 中將專案儲存為映像時，對於確保應用程式的順利執行至關重要。透過遵循本教程中概述的步驟，您可以有效地捕獲並處理此異常，從而增強專案管理解決方案的穩健性。

## 常見問題解答

### Q1：Aspose.Tasks 中出現 BitmapInvalidSizeException 的原因是什麼？

A1：當嘗試將項目另存為具有無效點陣圖大小參數的影像時，會出現此異常。

### Q2：將專案儲存為映像時，我可以自訂時間刻度嗎？

A2：是的，您可以根據您的要求調整時間刻度單位和計數，如教程中所示。

### 問題 3：在哪裡可以找到更多使用 Aspose.Tasks for .NET 的資源？

A3：您可以瀏覽 Aspose.Tasks 提供的文件和支援論壇以獲得全面的指導和協助。

### Q4：Aspose.Tasks 是否相容於不同版本的 Microsoft Project 檔案？

A4：是的，Aspose.Tasks 支援各種版本的 Microsoft Project 文件，從而實現無縫的互通性。

### Q5：如何取得Aspose.Tasks的臨時授權？

A5：您可以透過文章中提供的連結取得用於評估目的的臨時許可證。