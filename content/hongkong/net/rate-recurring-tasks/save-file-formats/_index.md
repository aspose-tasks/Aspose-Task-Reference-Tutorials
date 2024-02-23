---
title: 在 Aspose.Tasks 中以各種格式儲存 MS 專案文件
linktitle: 在Aspose.Tasks中以各種格式儲存文件
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 以各種格式儲存 MS Project 檔案。簡單的步驟即可實現高效率的專案管理。
type: docs
weight: 17
url: /zh-hant/net/rate-recurring-tasks/save-file-formats/
---
## 介紹
在本教學中，我們將探討如何使用 Aspose.Tasks for .NET 以各種格式儲存 Microsoft Project 檔案。 Aspose.Tasks 是一個功能強大的 API，可讓開發人員以程式設計方式操作和管理專案文件。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1.  Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET[這裡](https://releases.aspose.com/tasks/net/).
2. 開發環境：建置.NET開發環境，例如Visual Studio。
3. 對 C# 的基本了解：熟悉 C# 程式語言將會很有幫助。

## 導入命名空間
確保在 C# 檔案的開頭導入必要的命名空間：
```csharp

using Aspose.Tasks.Saving;
```
## 第 1 步：建立專案對象
首先，建立一個 Project 物件並載入 Microsoft Project 檔案。
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## 步驟 2：將項目儲存為 CSV 格式
現在，讓我們將項目儲存為 CSV 格式。 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## 第 3 步：探索其他格式
Aspose.Tasks支援保存專案檔案的各種格式，例如XML、PDF、XLSX等。您只需更改以下內容即可探索這些格式`SaveFileFormat`中的參數`Save`方法。
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
透過執行下列步驟，您可以使用 Aspose.Tasks for .NET 輕鬆地將 Microsoft Project 檔案儲存為各種格式。

## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for .NET 以不同格式儲存 MS Project 檔案。 Aspose.Tasks 簡化了以程式設計方式操作專案文件的過程，為開發人員提供了靈活性和效率。
## 常見問題解答
### Q：Aspose.Tasks 是否與所有版本的 Microsoft Project 相容？
答：Aspose.Tasks 支援 Microsoft Project 2003 XML、Microsoft Project 2007 MPP 和 Microsoft Project 2010 MPP 格式。
### Q：我可以在購買前試用 Aspose.Tasks 嗎？
答：是的，您可以從以下位置下載免費試用版：[這裡](https://releases.aspose.com/).
### Q：如何獲得 Aspose.Tasks 的支援？
答：您可以從 Aspose.Tasks 社群論壇獲得支援。[這裡](https://forum.aspose.com/c/tasks/15).
### Q：Aspose.Tasks 是否可以獲得臨時許可證？
答：是的，臨時許可證可用於評估目的。你可以獲得一個[這裡](https://purchase.aspose.com/temporary-license/).
### Q：Aspose.Tasks 的定價是多少？
答：定價資訊可以在 Aspose.Tasks 購買頁面找到[這裡](https://purchase.aspose.com/buy).