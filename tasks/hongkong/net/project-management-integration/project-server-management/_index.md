---
title: 使用 Aspose.Tasks 管理 MS Project Server
linktitle: 使用 Aspose.Tasks 管理 Project Server
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 解鎖無縫 MS Project Server 管理。輕鬆自動化專案任務。
weight: 23
url: /zh-hant/net/project-management-integration/project-server-management/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 管理 MS Project Server

## 介紹
在本教程中，我們將深入研究使用 Aspose.Tasks for .NET 管理 MS Project Server。 Aspose.Tasks 是一個功能強大的函式庫，使開發人員能夠以程式設計方式處理 Microsoft Project 文件，從而實現專案資料的無縫整合和操作。
## 先決條件
在我們深入使用 Aspose.Tasks 管理 MS Project Server 之前，請確保您已設定以下先決條件：
1. Microsoft Project Server：您需要存取 Microsoft Project Server 執行個體，在該執行個體中您具有管理權限或至少具有建立和管理專案的權限。
2.  Aspose.Tasks for .NET 函式庫：確保您已下載並安裝 Aspose.Tasks for .NET 函式庫。您可以從[網站](https://releases.aspose.com/tasks/net/).
3. 憑證：取得必要的憑證以透過 MS Project Server 執行個體進行驗證。這通常包括用戶名和密碼。
## 導入命名空間
在開始之前，請確保您已在 C# 程式碼中匯入了所需的命名空間：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## 第 1 步：設定身份驗證憑證
首先，您需要設定驗證憑證以連線到 MS Project Server 執行個體。這包括網域地址、使用者名稱和密碼。
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa"；
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## 第 2 步：載入項目
接下來，載入要使用 Aspose.Tasks 管理的 MS Project 檔案。
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## 步驟3：建立專案伺服器管理員
實例化一個`ProjectServerManager`使用先前定義的憑證的物件。
```csharp
var manager = new ProjectServerManager(credentials);
```
## 第 4 步：定義儲存選項
為您的專案定義任何特定的儲存選項。例如，您可以設定操作的逾時時間。
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## 第 5 步：建立或更新項目
最後，在 MS Project Server 上建立或更新專案。
```csharp
manager.CreateNewProject(project, options);
```
恭喜！您已使用 Aspose.Tasks for .NET 成功管理 MS Project Server。

## 結論
在本教程中，我們探討如何使用 Aspose.Tasks for .NET 以程式設計方式管理 MS Project Server。透過提供的步驟，您可以將 Aspose.Tasks 無縫整合到 .NET 應用程式中，以自動執行 MS Project Server 上的專案管理任務。
## 常見問題解答
### Q：Aspose.Tasks 是否與所有版本的 Microsoft Project Server 相容？
答：Aspose.Tasks 支援與各種版本的 Microsoft Project Server 集成，確保不同環境之間的相容性。
### Q：我可以使用 Aspose.Tasks 對專案執行批次操作嗎？
答：是的，Aspose.Tasks 可讓您執行批次操作，例如在 MS Project Server 上建立、更新和刪除項目。
### Q：Aspose.Tasks 是否提供專案排程和資源管理支援？
答：當然，Aspose.Tasks 為專案排程、資源分配和任務管理功能提供全面支援。
### Q：是否可以使用 Aspose.Tasks 自動執行報告任務？
答：是的，Aspose.Tasks 可讓您根據專案資料自動產生自訂報告，從而促進高效的專案監控和分析。
### Q：我可以在購買之前試用 Aspose.Tasks 嗎？
答：是的，您可以透過造訪免費試用版來探索 Aspose.Tasks 的功能[網站](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
