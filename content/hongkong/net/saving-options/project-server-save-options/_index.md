---
title: Aspose.Tasks 的伺服器保存 MS 項目選項
linktitle: Aspose.Tasks 的 Project Server 儲存選項
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Project Server 整合儲存 Aspose.Tasks 的 Microsoft Project 選項。增強您的專案管理工作流程。
type: docs
weight: 16
url: /zh-hant/net/saving-options/project-server-save-options/
---
## 介紹
在本教學中，我們將深入研究使用 Project Server 儲存 Aspose.Tasks 的 Microsoft Project 選項。 Aspose.Tasks 是一個功能強大的 .NET API，允許開發人員以程式設計方式處理 Microsoft Project 檔案。利用 Project Server 功能，我們可以將 Aspose.Tasks 無縫整合到我們的專案管理工作流程中。本教學將逐步指導您完成流程。
## 先決條件
在開始之前，請確保您具備以下先決條件：
1.  Aspose.Tasks for .NET：從下列位置安裝 Aspose.Tasks for .NET[下載連結](https://releases.aspose.com/tasks/net/).
   
2. 存取 Project Server：您將需要存取憑證和 Project Server 執行個體的 URL。如果您沒有，您可以從以下位置取得免費試用版：[這裡](https://releases.aspose.com/).
3. Microsoft Project 檔案：準備要使用 Aspose.Tasks 儲存的 Microsoft Project 檔案 (.mpp)。

## 導入命名空間
首先，您需要在專案中匯入必要的命名空間：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## 第 1 步：初始化項目和憑證
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
確保更換`"Your Document Directory"`, `URL`, `Domain`, `UserName`，和`Password`與你的實際價值觀。
## 步驟2：建立專案伺服器管理員
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## 第 3 步：定義儲存選項
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
調整`ProjectGuid`, `ProjectName`, `Timeout`，和`PollingInterval`根據您的要求。
## 第 4 步：將項目儲存到伺服器
```csharp
manager.CreateNewProject(project, options);
```
這將使用指定的選項將專案儲存到 Project Server。

## 結論
在本教學中，我們學習如何使用 Project Server 整合來儲存 Aspose.Tasks 的 Microsoft Project 選項。透過執行這些步驟，您可以將 Aspose.Tasks 無縫整合到您的專案管理工作流程中，從而提高效率和生產力。
## 常見問題解答
### Q：我可以將 Aspose.Tasks 與不同版本的 Microsoft Project 一起使用嗎？
答：是的，Aspose.Tasks 支援各種版本的 Microsoft Project，確保不同環境之間的相容性。
### Q：Aspose.Tasks 有試用版嗎？
答：是的，您可以從以下位置取得 Aspose.Tasks 的免費試用版：[這裡](https://releases.aspose.com/).
### Q：Aspose.Tasks 支援多執行緒嗎？
答：是的，Aspose.Tasks 被設計為線程安全的，允許並發存取項目資料。
### Q：使用 Project Server 整合時可以自訂儲存選項嗎？
答：是的，您可以自訂專案名稱、逾時和輪詢間隔等儲存選項來滿足您的要求。
### Q：在哪裡可以找到對 Aspose.Tasks 的支援？
答：您可以在以下網站上找到支援和協助：[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).