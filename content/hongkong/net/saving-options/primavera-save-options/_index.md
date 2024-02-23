---
title: 使用 Aspose.Tasks 儲存 MS 專案選項 Primavera
linktitle: Aspose.Tasks 的 Primavera 保存選項
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 無縫儲存 Primavera 的 MS Project 選項。請按照我們的逐步教學進行操作。
type: docs
weight: 14
url: /zh-hant/net/saving-options/primavera-save-options/
---
## 介紹
Aspose.Tasks for .NET 是一個功能強大的程式庫，可讓開發人員在其 .NET 應用程式中無縫地使用 Microsoft Project 檔案。它提供的關鍵功能之一是能夠為流行的專案管理軟體 Primavera 保存 MS Project 選項。在本教程中，我們將深入研究如何使用 Aspose.Tasks 來實現這一目標。
## 先決條件
在我們開始之前，請確保您具備以下條件：
- 對 C# 和 .NET 架構有基本了解。
-  Aspose.Tasks for .NET 安裝在您的開發環境中。如果沒有的話可以下載[這裡](https://releases.aspose.com/tasks/net/).
- 用於實驗的範例 MS Project 檔案。

## 導入命名空間
首先，讓我們將必要的命名空間匯入到我們的 C# 程式碼中：
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## 第 1 步：載入 MS 專案文件
首先將要使用的 MS Project 檔案載入到 C# 應用程式中。您可以使用`Project`由Aspose.Tasks提供的類別。
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## 步驟 2： 定義 Primavera 儲存選項
接下來，建立 Primavera 儲存選項並根據您的要求進行自訂。此步驟涉及指定活動 ID 前綴、後綴、增量以及是否對活動 ID 重新編號等參數。
```csharp
var options = new PrimaveraSaveOptions
{
    ActivityIdPrefix = "TEST",
    ActivityIdSuffix = 10000,
    ActivityIdIncrement = 5,
    RenumberActivityIds = true
};
```
## 步驟 3：儲存 Primavera 的 MS 專案選項
現在您已經載入了專案檔案並定義了 Primavera 儲存選項，是時候儲存 Primavera 的選項了。使用`Save`提供的方法`Project`類，傳遞所需的輸出檔案路徑和 Primavera 儲存選項。
```csharp
project.Save(DataDir + "WorkWithPrimaveraSaveOptions_out.xer", options);
```

## 結論
總之，利用 Aspose.Tasks for .NET 允許開發人員無縫操作 MS Project 文件，包括 Primavera 的保存選項。透過遵循本教學中概述的步驟，您可以將此功能有效地整合到您的 .NET 應用程式中。
## 常見問題解答
### Q：在儲存 Primavera 的 MS Project 選項時，除了活動 ID 之外，我還可以自訂其他參數嗎？
答：是的，Aspose.Tasks 提供了廣泛的客製化選項，包括資源分配和任務調度。
### Q：Aspose.Tasks 是否支援 Primavera 以外的其他專案管理軟體？
答：是的，Aspose.Tasks 支援與流行的專案管理工具（例如 Oracle Primavera、Microsoft Project Server 等）相容的各種格式。
### Q：Aspose.Tasks 適合小型和企業級專案嗎？
答：當然，Aspose.Tasks 旨在滿足開發各種規模專案的開發人員的需求，提供可擴展性和強大的效能。
### Q：我可以在購買前免費試用 Aspose.Tasks 嗎？
答：是的，您可以從以下位置下載 Aspose.Tasks 的免費試用版：[這裡](https://releases.aspose.com/)探索其特性和功能。
### Q：如果在使用 Aspose.Tasks 時遇到問題或有疑問，我可以在哪裡獲得支援？
答：您可以向 Aspose.Tasks 社群和支援團隊尋求協助[論壇](https://forum.aspose.com/c/tasks/15).