---
title: 使用 Aspose.Tasks 配置 MS Project 頁面設置
linktitle: 在 Aspose.Tasks 中配置頁面設置
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 設定 MS Project 頁面設定。透過簡單的步驟自訂方向、尺寸等。
type: docs
weight: 20
url: /zh-hant/net/outline-code-page-settings/page-settings/
---
## 介紹
在本教學中，我們將逐步介紹使用 Aspose.Tasks for .NET 設定 Microsoft Project 頁面設定的過程。 Aspose.Tasks 是一個功能強大的 API，允許開發人員以程式設計方式操作 Microsoft Project 檔案。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1.  Aspose.Tasks for .NET：請確定您已安裝 Aspose.Tasks for .NET。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).
2. 開發環境：使用 Visual Studio 或任何其他用於 .NET 開發的首選 IDE 設定開發環境。

## 導入命名空間
首先，您需要在專案中匯入必要的命名空間。這些命名空間提供對操作 MS Project 檔案所需的 Aspose.Tasks 類別和方法的存取。
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 第 1 步：載入專案文件
首先，您需要載入要設定頁面設定的 MS Project 檔案。
```csharp
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## 步驟2：造訪頁面設定
接下來，您將造訪專案文件的頁面設定。
```csharp
//取得設定
var settings = project.DefaultView.PageInfo.PageSettings;
```
## 步驟 3：設定頁面設定
現在，讓我們根據您的要求來配置頁面設定的各種屬性。
```csharp
//將頁面方向設定為縱向
settings.IsPortrait = true;
//設定要列印的寬度頁數
settings.PagesInWidth = 5;
//設定要列印的高度頁數
settings.PagesInHeight = 7;
//設定正常尺寸的百分比以調整列印
settings.PercentOfNormalSize = 200;
//設定紙張尺寸
settings.PaperSize = PrinterPaperSize.PaperB4;
//設定列印首頁頁碼
settings.FirstPageNumber = 3;
```
## 步驟 4：儲存專案文件
最後，使用更新的頁面設定儲存項目文件。
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## 結論
在本教學中，我們學習如何使用 Aspose.Tasks for .NET 設定 Microsoft Project 頁面設定。透過執行以下步驟，您可以根據您的要求輕鬆自訂頁面方向、尺寸和其他列印選項。

## 常見問題解答
### Q：我可以同時配置多個 MS Project 檔案的頁面設定嗎？
答：是的，您可以循環瀏覽多個專案文件並對每個文件套用相同的頁面設定。
### Q：是否可以將頁面設定恢復為預設值？
答：當然，您可以簡單地省略配置步驟或將設定重設為預設值。
### Q：支援的紙張尺寸有限制嗎？
答：Aspose.Tasks 支援多種紙張尺寸，包括標準尺寸和自訂尺寸。
### Q：我可以自動化頁面設定配置流程嗎？
答：當然，您可以將此功能整合到應用程式的工作流程中以自動執行頁面設定配置。
### Q：Aspose.Tasks 是否支援 .mpp 以外的其他檔案格式？
答：是的，Aspose.Tasks 支援各種檔案格式，例如 XML、MPT 和 HTML 等。