---
title: Aspose.Tasks 中 Microsoft Project 資料庫的設置
linktitle: Aspose.Tasks 中 Microsoft Project 資料庫的設置
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks 配置 Microsoft Project 資料庫設置，以便無縫整合到 .NET 應用程式中。
weight: 19
url: /zh-hant/net/advanced-concepts/msp-database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中 Microsoft Project 資料庫的設置

## 介紹

如果您使用 Aspose.Tasks 在 .NET 應用程式中使用 Microsoft Project 資料庫，則需要配置必要的設定以無縫匯入專案資料。本教學將逐步指導您完成流程。

## 先決條件

在開始之前，請確保您具備以下條件：

1.  Aspose.Tasks for .NET：下載並安裝 Aspose.Tasks 函式庫[這裡](https://releases.aspose.com/tasks/net/).
2. 存取 Microsoft Project 資料庫：您應該有權存取 Microsoft Project 資料庫以從中匯入資料。

## 導入命名空間

首先，確保將必要的命名空間匯入到您的專案中：

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## 第 1 步：建立連接字串

建構 Microsoft Project 資料庫的連接字串。這是一個例子：

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

確保將佔位符值替換為您的實際資料庫憑證。

## 步驟 2：設定 MspDbSettings

建立一個實例`MspDbSettings`並指定連接字串和項目 GUID：

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## 第 3 步：載入項目數據

實例化一個`Project`使用配置的設定的物件：

```csharp
var project = new Project(settings);
```

## 第 4 步：儲存項目數據

將載入的項目資料儲存到文件中：

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## 結論

在本教學中，您學習如何使用 Aspose.Tasks for .NET 設定存取 Microsoft Project 資料庫的設定。透過執行以下步驟，您可以將專案資料無縫匯入到您的應用程式中，從而促進高效的專案管理。

## 常見問題解答

### Q1：我可以將 Aspose.Tasks 與不同版本的 Microsoft Project 資料庫一起使用嗎？

A1：是的，Aspose.Tasks 支援各種版本的 Microsoft Project 資料庫，允許靈活整合。

### Q2：如何解決資料庫連線問題？

 A2：確保使用適當的憑證和資料庫詳細資訊正確配置連接字串。您也可以參考文件或尋求支持[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).

### Q3：Aspose.Tasks 有試用版嗎？

 A3：是的，您可以從以下位置存取免費試用版：[這裡](https://releases.aspose.com/).

### Q4：我可以自訂資料庫互動的架構嗎？

 A4：是的，您可以指定架構`MspDbSettings`根據您的資料庫結構的對象。

### Q5：在哪裡可以找到有關使用 Aspose.Tasks 的更詳細文件？

 A5：您可以探索全面的文檔[這裡](https://reference.aspose.com/tasks/net/)了解 Aspose.Tasks 功能的詳細見解。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
