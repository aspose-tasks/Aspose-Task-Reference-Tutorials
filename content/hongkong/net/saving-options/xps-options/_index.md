---
title: 使用 Aspose.Tasks 將 MSP 轉換為 XPS 選項
linktitle: Aspose.Tasks 的 XPS 選項
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 將 Microsoft Project 檔案轉換為 XPS 格式。易於集成，功能強大。
type: docs
weight: 21
url: /zh-hant/net/saving-options/xps-options/
---
## 介紹
Microsoft Project (MSP) 是一種廣泛使用的專案管理工具，可促進專案活動的規劃、追蹤和報告。 Aspose.Tasks for .NET 提供了以程式設計方式操作 MSP 檔案的強大功能，使開發人員能夠自動執行與專案管理相關的各種任務。在本教程中，我們將深入研究如何利用 Aspose.Tasks for .NET 從 MSP 文件產生 XPS 文件，以探索必要的步驟和注意事項。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1. 安裝 Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET[網站](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 文件：準備要轉換為 XPS 格式的 Microsoft Project 文件 (.mpp)。

## 導入命名空間
若要啟動流程，請在 .NET 專案中匯入所需的命名空間：
```csharp

using Aspose.Tasks.Saving;
```

## 步驟1：設定文檔目錄路徑
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
```
代替`"Your Document Directory"`與您的 MSP 文件所在的路徑。
## 步驟2：載入MSP文檔
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
在這裡，我們初始化一個新的`Project`透過傳遞 MSP 文件的路徑來取得物件。
## 第 3 步：建立 XPS 儲存選項
```csharp
//建立 XPS 儲存選項並調整參數
var options = new XpsOptions
{
    RenderMetafileAsBitmap = true
};
```
在這一步驟中，我們實例化`XpsOptions`並配置參數。環境`RenderMetafileAsBitmap`到`true`確保圖元檔案的正確呈現。
## 步驟 4：將文件另存為 XPS
```csharp
project.Save(DataDir + "UseSvgOptions_out.xps", options);
```
最後，我們調用`Save`方法上的`Project`對象，指定輸出檔案路徑和先前配置的`XpsOptions`.

## 結論
總之，Aspose.Tasks for .NET 簡化了以程式設計方式將 Microsoft Project 文件轉換為 XPS 格式的過程。透過遵循本教程中概述的步驟，開發人員可以將此功能無縫整合到他們的 .NET 應用程式中，從而輕鬆增強專案管理工作流程。
## 常見問題解答
### Q：Aspose.Tasks for .NET 可以處理複雜的 MSP 檔案嗎？
答：是的，Aspose.Tasks for .NET 可以有效地處理複雜的 Microsoft Project 文件，確保準確轉換為各種格式。
### Q：Aspose.Tasks for .NET 有試用版嗎？
答：是的，您可以從以下位置取得免費試用版：[這裡](https://releases.aspose.com/).
### Q：Aspose.Tasks for .NET 是否支援 XPS 以外的其他輸出格式？
答：是的，Aspose.Tasks for .NET 支援各種輸出格式，如 PDF、HTML、PNG 和 JPEG 等。
### Q：我可以自訂輸出檔案的渲染選項嗎？
答：當然，Aspose.Tasks for .NET 提供了廣泛的選項來根據您的要求自訂渲染參數。
### Q：在哪裡可以找到 Aspose.Tasks for .NET 的其他支援或協助？
答：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)有關 Aspose.Tasks for .NET 的任何問題或協助。