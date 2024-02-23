---
title: Aspose.Tasks 中的資料庫設置
linktitle: Aspose.Tasks 中的資料庫設置
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 從 Primavera 資料庫匯入專案。在此綜合教程中取得逐步指導。
type: docs
weight: 29
url: /zh-hant/net/calendar-scheduling/database-settings/
---
## 介紹

Aspose.Tasks for .NET 是一個功能強大的程式庫，可讓開發人員在其 .NET 應用程式中使用 Microsoft Project 檔案。在本教程中，我們將重點介紹使用 Aspose.Tasks 從 Primavera 資料庫匯入專案。

## 先決條件

在我們開始之前，請確保您具備以下條件：

- C# 程式語言的基礎知識。
- Visual Studio 安裝在您的系統上。
- 安裝了 .NET 函式庫的 Aspose.Tasks。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).
- 存取 Primavera 資料庫以及必要的權限。

## 導入命名空間

首先，您需要將必要的命名空間匯入到您的 C# 專案中。這些命名空間提供對使用 Aspose.Tasks for .NET 所需的類別和方法的存取。

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

現在，讓我們將提供的範例程式碼分解為多個步驟：

## 第 1 步：定義連接字串

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

在此步驟中，我們定義連接字串以連接到 Primavera 資料庫。確保您更換`DataDir`與資料庫檔案所在的目錄。

## 第 2 步：建立資料庫設置

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

在這裡，我們建立一個實例`PrimaveraDbSettings`類，將連接字串和項目 ID 作為參數傳遞。根據您的要求調整項目 ID。

## 第 3 步：設定提供者不變名稱

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

指定提供者不變名稱。在此範例中，我們使用 SQLite，但您可以根據您的資料庫提供者變更它。

## 第 4 步：載入項目

```csharp
var project = new Project(settings);
```

創建一個新的`Project`對象，將資料庫設定作為參數傳遞。

## 第 5 步：儲存項目

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

最後，以指定的文件格式將項目儲存到所需位置。

## 結論

在本教程中，我們學習如何使用 Aspose.Tasks for .NET 從 Primavera 資料庫匯入專案。透過遵循提供的步驟，您可以將專案匯入功能無縫整合到您的 .NET 應用程式中。

## 常見問題解答

### Q1：我可以使用 Aspose.Tasks for .NET 從不同的資料庫提供者匯入專案嗎？

A1：是的，您可以透過相應地調整連接字串和提供者不變名稱來從各種資料庫提供者匯入專案。

### 問題 2：Aspose.Tasks for .NET 有沒有免費試用版？

 A2：是的，您可以從以下位置獲得 Aspose.Tasks for .NET 的免費試用版：[這裡](https://releases.aspose.com/).

### Q3：在哪裡可以找到 Aspose.Tasks for .NET 的文件？

A3：你可以找到文檔[這裡](https://reference.aspose.com/tasks/net/).

### Q4：如何獲得 Aspose.Tasks for .NET 支援？

 A4：您可以從 Aspose.Tasks 社群論壇獲得支持[這裡](https://forum.aspose.com/c/tasks/15).

### Q5：我需要臨時授權才能使用 Aspose.Tasks for .NET 嗎？

 A5：如果您想評估該庫的全部功能，您可以從以下地址取得臨時許可證：[這裡](https://purchase.aspose.com/temporary-license/).