---
date: 2026-03-14
description: 了解如何使用 Aspose.Tasks 為 Microsoft Project 資料庫指定資料庫結構，以及如何將專案資料匯入 .NET 應用程式。
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks 為 Project DB 指定資料庫結構
url: /zh-hant/net/advanced-concepts/msp-database-settings/
weight: 19
---

  
**Author:** Aspose  

Translate labels.

"**最後更新：** 2026-03-14  
**測試環境：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose"

Then closing shortcodes.

We must keep the shortcodes exactly as they are.

Now produce final content with translations, preserving everything.

Check for any missed items: The initial three shortcodes, then content, then closing shortcodes, then backtop button shortcode, then final.

Make sure to keep code block placeholders unchanged.

Also ensure markdown formatting preserved.

Proceed to final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的 Microsoft Project 資料庫設定

## 介紹

如果您在 .NET 應用程式中使用 Aspose.Tasks 處理 Microsoft Project 資料庫，您需要 **指定資料庫綱要** 並設定必要的參數，以 **匯入專案** 資料。 本教學將逐步指導您完成整個流程，說明 **如何設定連線** 詳情、**建立 .NET 連線字串**，最後 **將專案儲存為 MPP**。

## 快速解答
- **主要目標是什麼？** 指定資料庫綱要並將 Project 資料庫匯入 .NET 應用程式。  
- **需要哪個函式庫？** Aspose.Tasks for .NET。  
- **如何連接至 Project Server？** 透過建立正確的 SQL 連線字串並使用 `MspDbSettings`。  
- **產生的檔案格式是什麼？** 使用 `SaveFileFormat.Mpp` 儲存的 MPP 檔案。  
- **可以變更綱要名稱嗎？** 可以，設定 `MspDbSettings` 的 `Schema` 屬性。

## 如何為 Project DB 指定資料庫綱要

了解為何需要 **指定資料庫綱要** 非常重要。在許多企業環境中，Project Server 資料庫位於自訂綱要下（例如 `dbo`、`psdata`）。透過明確設定綱要，可確保 Aspose.Tasks 查詢正確的資料表，避免執行時錯誤，並保證資料匯入的正確性。

## 前置條件

在開始之前，請確保您具備以下項目：

1. Aspose.Tasks for .NET：從 [here](https://releases.aspose.com/tasks/net/) 下載並安裝 Aspose.Tasks 函式庫。  
2. Microsoft Project 資料庫的存取權限：您需要能夠存取 Microsoft Project 資料庫以匯入資料。  

## 匯入命名空間

首先，確保在專案中匯入必要的命名空間：

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## 步驟 1：建立連線字串

建立連接至 Microsoft Project 資料庫的連線字串。在此您會 **建立 .NET 連線字串**，同時定義 **如何連接至 Project Server**。

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **專業提示：** 請再次確認 `DataSource` 與 `InitialCatalog` 的值；它們必須與您的伺服器位址及已發佈的資料庫名稱相符。

## 步驟 2：設定 MspDbSettings

建立 `MspDbSettings` 的實例，傳入連線字串，並透過設定 `Schema` 屬性 **指定資料庫綱要**。這告訴 Aspose.Tasks 要查詢哪個綱要。

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

此處同時提供專案的 GUID，以識別您想要載入的特定專案。

## 步驟 3：載入專案資料

使用已設定好的參數建立 `Project` 物件。此步驟實際上 **如何從資料庫匯入專案** 資料至 .NET 物件。

```csharp
var project = new Project(settings);
```

## 步驟 4：儲存專案資料

最後，將載入的專案持久化為磁碟上的 MPP 檔案。此示範了使用 Aspose.Tasks API **將專案儲存為 MPP**。

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

執行程式碼後，您會在輸出目錄中看到 `ImportProjectDataFromDatabase_out.mpp` 檔案，可直接於 Microsoft Project 開啟。

## 結論

透過本教學，您已學會如何為 Microsoft Project 資料庫 **指定資料庫綱要**、**設定連線**、**匯入專案** 資料，以及使用 Aspose.Tasks for .NET **將專案儲存為 MPP**。這些步驟可讓 Project Server 資料無縫整合至您的自訂應用程式，協助您打造穩健的專案管理解決方案。

## 常見問題

### Q1：我可以在不同版本的 Microsoft Project 資料庫上使用 Aspose.Tasks 嗎？
A1：可以，Aspose.Tasks 支援多種版本的 Microsoft Project 資料庫，提供彈性的整合方式。

### Q2：我該如何排除與資料庫的連線問題？
A2：請確認連線字串已正確設定，包括適當的認證與資料庫資訊。您亦可參考文件或在 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 尋求支援。

### Q3：是否提供 Aspose.Tasks 的試用版？
A3：有，您可從 [here](https://releases.aspose.com/) 取得免費試用版。

### Q4：我可以自訂資料庫互動的綱要嗎？
A4：可以，您可依據資料庫結構為 `MspDbSettings` 物件指定綱要。

### Q5：在哪裡可以找到更詳細的 Aspose.Tasks 使用文件？
A5：您可在 [here](https://reference.aspose.com/tasks/net/) 瀏覽完整文件，深入了解 Aspose.Tasks 功能。

**Q：此方法能在 Azure SQL 資料庫上使用嗎？**  
A：絕對可以。只需將 `DataSource` 調整為您的 Azure 伺服器名稱，並確保已啟用 TLS/SSL 設定。

**Q：如何處理大型 Project 資料庫而不會逾時？**  
A：可在連線字串中提升 `ConnectTimeout` 的數值，必要時考慮分批載入專案。

**最後更新：** 2026-03-14  
**測試環境：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}