---
title: Aspose.Tasks 的圖片保存 MS 項目選項
linktitle: Aspose.Tasks 的圖片保存選項
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 將 MS Project 選項儲存為映像。請按照我們的逐步指南進行無縫整合。
weight: 11
url: /zh-hant/net/saving-options/image-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 的圖片保存 MS 項目選項


## 介紹
在軟體開發領域，有效地處理專案任務對於成功的專案管理至關重要。 Aspose.Tasks for .NET 為使用 Microsoft Project 檔案的開發人員提供了強大的解決方案，使他們能夠在 .NET 應用程式中無縫地操作、轉換和管理專案任務。
## 先決條件
在深入使用 Aspose.Tasks for .NET 將 MS Project 選項儲存為影像之前，請確保滿足以下先決條件：
### 1.安裝Aspose.Tasks for .NET
首先，您需要在開發環境中安裝 Aspose.Tasks for .NET。您可以從以下位置下載該程式庫[網站](https://releases.aspose.com/tasks/net/)並按照提供的安裝說明進行操作。
### 2. 取得許可證（可選）
雖然 Aspose.Tasks for .NET 無需許可證即可在評估模式下使用，但建議取得許可證以獲得完整功能並消除評估限制。您可以從以下機構取得許可證[購買頁面](https://purchase.aspose.com/buy)或選擇一個[臨時執照](https://purchase.aspose.com/temporary-license/)用於測試目的。
### 3. C#和.NET開發基礎知識
必須對 C# 程式語言和 .NET 框架有基本的了解，才能遵循範例並將 Aspose.Tasks 功能有效地整合到您的應用程式中。
## 導入命名空間
在我們開始使用 Aspose.Tasks for .NET 將 MS Project 選項儲存為映像之前，讓我們確保將必要的命名空間匯入到我們的 C# 專案中：
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 步驟1：設定文檔目錄路徑
確保您有一個指定的文檔目錄並相應地設定路徑：
```csharp
String DataDir = "Your Document Directory";
```
## 第 2 步：載入 MS 專案文件
初始化一個新的`Project`透過載入 MS Project 檔案來物件：
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## 第 3 步：定義圖像保存選項
建立一個實例`ImageSaveOptions`並指定所需的設定：
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## 步驟 4：指定要儲存的頁面
如果需要，指定要儲存的頁面。在此範例中，我們新增第 2 頁：
```csharp
options.Pages.Add(2);
```
## 第 5 步：儲存影像
最後，使用指定的選項將選定的頁面儲存為圖像：
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## 結論
Aspose.Tasks for .NET 簡化了使用 MS Project 檔案的過程，使開發人員能夠輕鬆地操作專案任務。透過遵循本教程中概述的步驟，您可以在 .NET 應用程式中有效地將 MS Project 選項儲存為映像。
## 常見問題解答
### Q1：我可以在沒有許可證的情況下使用 Aspose.Tasks for .NET 嗎？
答：是的，您可以在評估模式下使用 Aspose.Tasks for .NET，無需許可證。但是，建議取得完整功能的許可證並消除評估限制。
### Q2：如何取得臨時測試許可證？
答：您可以從以下機構獲得用於測試目的的臨時許可證：[臨時許可證頁面](https://purchase.aspose.com/temporary-license/).
### Q3：Aspose.Tasks for .NET 與其他 .NET 框架相容嗎？
答：是的，Aspose.Tasks for .NET 與各種 .NET 框架相容，包括 .NET Core 和 .NET Standard。
### Q4：我可以進一步自訂圖像儲存選項嗎？
答：是的，您可以根據您的特定要求自訂圖像儲存選項，例如調整頁面大小、解析度或輸出格式。
### Q5：在哪裡可以找到對 Aspose.Tasks for .NET 的支援？
答：您可以在 Aspose.Tasks for .NET 上找到支援和協助[論壇](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
