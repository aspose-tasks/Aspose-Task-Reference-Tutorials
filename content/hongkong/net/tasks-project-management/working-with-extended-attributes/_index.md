---
title: 使用 Aspose.Tasks 操作 MS Project 擴充屬性
linktitle: 在 Aspose.Tasks 中使用擴充屬性
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 來處理 MS Project 擴充屬性。以程式設計方式輕鬆操作任務資料。
type: docs
weight: 11
url: /zh-hant/net/tasks-project-management/working-with-extended-attributes/
---
## 介紹
Aspose.Tasks for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式操作 Microsoft Project 檔案。該庫的主要功能之一是它能夠使用 MS Project 擴充屬性。擴充屬性為專案中的任務提供額外的自訂和元數據，使用戶能夠儲存和管理標準任務屬性以外的特定資訊。
在本教程中，我們將探索如何使用 Aspose.Tasks for .NET 來處理 MS Project 擴充屬性。我們將介紹先決條件、匯入命名空間，並以逐步指南的形式將每個範例分解為多個步驟。學完本教學後，您將深入了解如何在 .NET 應用程式中利用擴充屬性。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
### 1.安裝Visual Studio
確保您的系統上安裝了 Visual Studio。如果您還沒有下載，可以從網站下載。
### 2..NET 函式庫的 Aspose.Tasks
從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫[網站](https://releases.aspose.com/tasks/net/).

## 導入命名空間
要開始使用 Aspose.Tasks for .NET，您需要將必要的命名空間匯入到您的專案中。按著這些次序：
### 第 1 步：開啟 Visual Studio
在您的系統上啟動 Visual Studio。
### 步驟2：建立一個新項目
建立一個新專案或開啟一個要使用 Aspose.Tasks 的現有專案。
### 第 3 步：導入命名空間
在 C# 檔案的開頭新增以下命名空間：
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

現在我們已經設定了環境，讓我們深入使用 Aspose.Tasks for .NET 來處理 MS Project 擴充屬性。
## 第 1 步：定義資料目錄
定義 MS Project 檔案所在目錄的路徑：
```csharp
String DataDir = "Your Document Directory";
```
代替`"Your Document Directory"`與文檔目錄的實際路徑。
## 第 2 步：載入專案文件
使用以下命令載入 MS Project 文件`Project`班級：
```csharp
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
這段程式碼初始化了一個新的實例`Project`類，載入指定的 MS Project 檔案。
## 步驟 3：讀取任務的擴充屬性
迭代任務及其擴展屬性來讀取資訊：
```csharp
foreach (var task in project.RootTask.Children)
{
    foreach (var attribute in task.ExtendedAttributes)
    {
        //閱讀有關擴展屬性的常見信息
        Console.WriteLine("Extended Attribute: " + attribute.ToString());
    }
}
```
此程式碼片段循環遍歷每個任務及其擴展屬性，將其資訊列印到控制台。

## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for .NET 來處理 MS Project 擴充屬性。透過執行上述步驟，您可以有效地管理和操作 .NET 應用程式中的擴充屬性資料。
## 常見問題解答
### Aspose.Tasks for .NET 是否與所有版本的 Microsoft Project 相容？
是的，Aspose.Tasks for .NET 支援各種版本的 Microsoft Project，包括 2003、2007、2010、2013、2016 和 2019。
### 我可以使用 Aspose.Tasks for .NET 建立新的 MS Project 檔案嗎？
絕對地！ Aspose.Tasks for .NET 可讓您以程式設計方式建立、修改和操作 MS Project 檔案。
### Aspose.Tasks for .NET 是否需要商業用途授權？
是的，您需要購買 Aspose.Tasks for .NET 的商業使用授權。但是，您也可以利用免費試用來評估其功能。
### 我可以根據專案需求自訂擴充屬性嗎？
是的，Aspose.Tasks for .NET 提供了廣泛的功能來自訂擴充屬性以滿足您專案的特定需求。
### 如果在使用 Aspose.Tasks for .NET 時遇到任何問題，我可以在哪裡獲得支援？
您可以從 Aspose.Tasks 社群論壇獲得支持[這裡](https://forum.aspose.com/c/tasks/15).