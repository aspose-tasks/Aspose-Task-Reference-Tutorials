---
title: 在 Aspose.Tasks 中配置 MS Project Primavera 資料庫
linktitle: 在 Aspose.Tasks 中配置 Primavera 資料庫設置
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中輕鬆配置 MS Project Primavera 資料庫設定。簡化您的專案管理任務。
weight: 11
url: /zh-hant/net/project-management-integration/primavera-database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中配置 MS Project Primavera 資料庫

## 介紹
您準備好利用 Aspose.Tasks for .NET 的強大功能來無縫配置 MS Project Primavera 資料庫設定了嗎？在本教程中，我們將逐步指導您完成流程。但在我們深入之前，讓我們確保您擁有所需的一切。
## 先決條件
在開始之前，請確保您具備以下先決條件：
### 1.安裝Aspose.Tasks for .NET
前往[下載適用於 .NET 的 Aspose.Tasks](https://releases.aspose.com/tasks/net/)並取得最新版本的 Aspose.Tasks 庫。請依照提供的安裝說明在您的 .NET 環境中進行設定。
### 2. 存取 MS Project Primavera 資料庫
確保您有權存取 MS Project Primavera 資料庫。您將需要必要的憑證和連接詳細資訊才能繼續。
### 3. C#和.NET Framework基礎知識
本教學假設您對 C# 程式語言和 .NET Framework 有基本了解。

## 導入命名空間
首先，我們將必要的命名空間匯入到您的 C# 專案中。

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

```
該行導入`System.Data.SqlClient`命名空間，其中包含用於在 .NET 應用程式中使用 SQL Server 資料庫的類別。

現在您已經設定了先決條件並匯入了所需的命名空間，讓我們詳細介紹一下使用 Aspose.Tasks for .NET 設定 MS Project Primavera 資料庫設定所提供的範例程式碼。
## 步驟1：建立SqlConnectionStringBuilder對象
```csharp
var sb = new SqlConnectionStringBuilder();
sb.DataSource = "192.168.56.3,1433";
sb.Encrypt = true;
sb.TrustServerCertificate = true;
sb.InitialCatalog = "PrimaveraEDB";
sb.NetworkLibrary = "DBMSSOCN";
sb.UserID = "privuser";
sb.Password = "***";
sb.ConnectTimeout = 2; //跳過
```
這段程式碼創建了一個`SqlConnectionStringBuilder`物件並設定各種屬性，例如`DataSource`, `Encrypt`, `InitialCatalog`, `UserID`, `Password`等，配置Primavera資料庫的連接字串。
## 步驟 2：初始化 PrimaveraDbSettings 對象
```csharp
var settings = new PrimaveraDbSettings(sb.ConnectionString, 4502);
```
在這裡，我們初始化一個新的實例`PrimaveraDbSettings`透過傳遞連接字串和項目 ID 來類別（在本例中，`4502`) 作為參數。
## 第 3 步：從資料庫讀取項目
```csharp
var project = new Project(settings);
```
該行創建了一個新的`Project`對象透過傳遞`settings`我們之前創建的物件。它建立與 Primavera 資料庫的連接並讀取具有指定 UID 的項目（`4502`）。
## 第4步：顯示項目UID
```csharp
Console.WriteLine("Project UID to read: " + settings.ProjectId);
```
最後，此程式碼將正在讀取的項目的 UID 列印到控制台。

## 結論
恭喜！您已了解如何使用 Aspose.Tasks for .NET 設定 MS Project Primavera 資料庫設定。有了這些知識，您就可以有效地將 Aspose.Tasks 整合到您的 .NET 應用程式中並簡化專案管理任務。
## 常見問題解答
### Q：我可以將 Aspose.Tasks for .NET 與其他專案管理軟體一起使用嗎？
答：是的，Aspose.Tasks for .NET 支援與各種專案管理軟體集成，包括 MS Project、Primavera 等。
### Q：Aspose.Tasks for .NET 是否與最新的 .NET Core 版本相容？
答：是的，Aspose.Tasks for .NET 與 .NET Core 和 .NET Framework 環境相容。
### Q：Aspose.Tasks for .NET 是否提供對雲端為基礎的專案管理解決方案的支援？
答：Aspose.Tasks for .NET 主要專注於本機專案管理解決方案，但它可以透過適當的配置來適應某些雲端環境。
### Q：我可以使用 Aspose.Tasks for .NET 以程式設計方式操作專案資料嗎？
答：當然！ Aspose.Tasks for .NET 提供了一組豐富的 API，用於讀取、寫入和操作各種格式的項目資料。
### Q：是否有適用於 .NET 使用者的 Aspose.Tasks 的社群論壇或支援管道？
答： 是的，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)對於您可能遇到的任何問題或疑問，尋求社群支援和協助。## 完整原始碼
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
