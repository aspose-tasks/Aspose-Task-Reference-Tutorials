---
title: 在 Aspose.Tasks 中自訂 MS Project 頁面視圖設定
linktitle: 在 Aspose.Tasks 中配置頁面視圖設置
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中設定頁面視圖設定以自訂 Microsoft Project 文件的列印格式。
type: docs
weight: 21
url: /zh-hant/net/outline-code-page-settings/page-view-settings/
---
## 介紹
Microsoft Project 是一個功能強大的專案管理工具，但有時您需要自訂專案的檢視和列印方式。使用 Aspose.Tasks for .NET，您可以輕鬆配置頁面視圖設定以滿足您的特定要求。在本教程中，我們將逐步指導您完成流程。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1.  Aspose.Tasks for .NET：請確定您已下載並安裝 Aspose.Tasks for .NET 函式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 檔案：準備好要設定頁面檢視設定的 Microsoft Project 檔案。

## 導入命名空間
首先，您需要匯入必要的命名空間以在 .NET 專案中使用 Aspose.Tasks。
```csharp
    
    using Aspose.Tasks.Saving;
```
## 第 1 步：載入專案文件
首先將 Microsoft Project 檔案載入到`Project`班級。
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## 第 2 步：設定第一列數
指定要在所有頁面上列印的第一列的數量。
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## 第三步：列印筆記
選擇是否隨項目一起列印註解。
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## 第 4 步：將時間刻度調整到頁尾
決定列印時是否使時間刻度適合頁面末端。
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## 第 5 步：列印所有工作表列
指定是否列印檢視的所有工作表列。
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## 步驟 6：列印空白頁
選擇是否列印視圖的空白頁。
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## 步驟 7：在所有頁面上列印第一列
設定是否在所有頁面上列印指定數量的第一列。
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## 步驟 8：使用設定的設定儲存項目
最後，使用配置的頁面視圖設定儲存項目，並指定輸出格式，例如 PDF。
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## 結論
在 Aspose.Tasks for .NET 中設定 Microsoft Project 頁面視圖設定非常簡單，並且允許您根據您的特定需求自訂列印格式。透過遵循本教學中概述的步驟，您可以確保您的專案文件完全按照要求呈現。
## 常見問題解答
### Q：我可以為 PDF 以外的其他文件格式設定頁面視圖設定嗎？
答：是的，Aspose.Tasks 支援保存專案的各種檔案格式，包括 XLSX、MPP 和 HTML。
### Q：我可以列印的列數有限制嗎？
答：Aspose.Tasks 可讓您根據您的要求自訂要列印的列數。
### Q：我可以為不同的項目套用不同的頁面視圖設定嗎？
答：是的，您可以為您使用的每個專案文件單獨調整頁面視圖設定。
### Q：Aspose.Tasks 是否與所有版本的 Microsoft Project 相容？
答：Aspose.Tasks 提供與 Microsoft Project 2003 及更高版本的兼容性。
### Q：我可以在哪裡找到有關 Aspose.Tasks 的進一步幫助或支援？
答：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)對於您在使用過程中遇到的任何疑問或問題。