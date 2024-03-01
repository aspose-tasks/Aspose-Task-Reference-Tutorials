---
title: 掌握 Aspose.Tasks for .NET 中的任務使用視圖
linktitle: 在 Aspose.Tasks 中配置任務使用視圖
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 並了解如何設定任務使用視圖。自訂時間刻度設定並增強您的專案管理視覺效果。
type: docs
weight: 24
url: /zh-hant/net/task-table-management/task-usage-views/
---
## 介紹
在專案管理領域，視覺化任務使用對於有效規劃和執行至關重要。 Aspose.Tasks for .NET 提供了一個強大的解決方案來渲染任務使用視圖，讓您可以自訂時間刻度設定和示範格式。在本教學中，我們將逐步完成使用 Aspose.Tasks 配置任務使用視圖的步驟。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1.  Aspose.Tasks for .NET：確保您已將 Aspose.Tasks 庫整合到您的 .NET 專案中。你可以下載它[這裡](https://releases.aspose.com/tasks/net/).
2. .NET 環境：在您的電腦上設定有效的 .NET 環境。
## 導入命名空間
在您的 .NET 專案中，匯入必要的命名空間以存取 Aspose.Tasks 功能。將以下行加入您的程式碼：
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 步驟1：設定文檔目錄路徑
在使用 Aspose.Tasks 功能之前，請設定文件目錄的路徑。代替`"Your Document Directory"`與實際路徑。
```csharp
String DataDir = "Your Document Directory";
```
## 第 2 步：載入項目
初始化 Aspose.Tasks`Project`透過載入專案檔案（例如，TaskUsageView.mpp）來取得物件。
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## 第 3 步：定義儲存選項
創建一個`SaveOptions`物件來指定渲染選項。將時間刻度設定為“天”，將示範格式設定為“TaskUsage”。
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## 第 4 步：使用天時間刻度保存
使用預先定義的時間刻度設定“天”儲存項目。
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## 第 5 步：使用 ThirdsOfMonths 時間刻度保存
將時間刻度設定更改為“ThirdsOfMonths”並儲存項目。
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## 步驟 6：以月為單位進行保存
將時間刻度設定為“月”並使用更新的設定儲存項目。
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## 結論
使用 Aspose.Tasks for .NET 設定任務使用視圖是一個簡單的過程。透過自訂時間刻度設置，您可以根據您的特定需求自訂專案任務的視覺化。
歡迎探索更多特性與功能[文件](https://reference.aspose.com/tasks/net/).
## 經常問的問題
### 我可以自訂超出預訂設定的時間範圍嗎？
是的，您可以透過指定間隔和單位來設定自訂時間刻度。
### 還有其他可用的演示格式嗎？
Aspose.Tasks 支援各種示範格式，包括甘特圖、ResourceUsage 等。
### Aspose.Tasks 是否與不同的專案檔案格式相容？
是的，Aspose.Tasks 支援流行的專案檔案格式，例如 MPP、XML 和 CSV。
### 我可以對特定任務套用不同的時間刻度設定嗎？
當然，您可以為專案中的各個任務自訂時間刻度設定。
### 我如何獲得 Aspose.Tasks 的支持或尋求協助？
參觀[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以獲得社區的支持和指導。