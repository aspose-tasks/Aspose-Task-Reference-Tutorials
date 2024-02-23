---
title: 在 Aspose.Tasks 中管理 MS Project Server 憑證
linktitle: 在 Aspose.Tasks 中管理 Project Server 憑證
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 無縫管理 MS Project Server 憑證。提高專案管理效率。
type: docs
weight: 22
url: /zh-hant/net/project-management-integration/project-server-credentials/
---
## 介紹
在專案管理領域，有效的協調和無縫溝通對於專案成功執行至關重要。 Aspose.Tasks for .NET 提供了一個管理 Microsoft Project Server 憑證的全面解決方案，使用戶能夠安全地存取和操作專案資料。本教學深入探討使用 Aspose.Tasks for .NET 管理 MS Project Server 憑證的流程，引導使用者完成每個步驟以確保流暢的體驗。
## 先決條件
在開始使用 Aspose.Tasks for .NET 管理 MS Project Server 憑證之前，請確保符合下列先決條件：
### 1.安裝Aspose.Tasks for .NET
首先，從提供的下載並安裝 Aspose.Tasks for .NET[下載連結](https://releases.aspose.com/tasks/net/),請按照安裝說明將該程式庫無縫整合到您的 .NET 環境中。
### 2. 存取憑證
收集存取 MS Project Server 所需的必要憑證。這包括與 Project Server 關聯的 SharePoint 網域位址、使用者名稱和密碼。

## 導入命名空間
在您的 .NET 專案中，匯入所需的命名空間以有效利用 Aspose.Tasks for .NET 提供的功能。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## 步驟1：定義文檔目錄路徑
```csharp
String DataDir = "Your Document Directory";
```
## 步驟 2：設定 SharePoint 網域位址、使用者名稱和密碼
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa"；
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## 步驟 3：建立 Project Server 憑證
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## 第 4 步：載入專案文件
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## 第 5 步：初始化專案伺服器管理員
```csharp
var manager = new ProjectServerManager(credentials);
```
## 步驟6：建立新項目
```csharp
manager.CreateNewProject(newProject);
```
## 步驟7：檢索項目列表
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## 第 8 步：遍歷項目列表
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## 結論
有效管理 MS Project Server 憑證對於簡化專案管理至關重要。 Aspose.Tasks for .NET 透過提供一組強大的功能來簡化此過程。透過遵循本教程中概述的逐步指南，使用者可以將 Aspose.Tasks for .NET 無縫整合到其專案中，確保安全存取和操作專案資料。
## 常見問題解答
### Q：Aspose.Tasks for .NET 是否與所有版本的 Microsoft Project Server 相容？
答：Aspose.Tasks for .NET 旨在與 Microsoft Project Server 的各個版本相容，確保使用者的多功能性和靈活性。
### Q：我可以將 Aspose.Tasks for .NET 整合到我現有的 .NET 專案中嗎？
答：是的，Aspose.Tasks for .NET 可以無縫整合到現有的 .NET 專案中，從而促進高效的專案管理功能。
### Q：Aspose.Tasks for .NET 是否提供存取專案資源的支援？
答：當然可以，Aspose.Tasks for .NET 為存取和操作專案資源提供全面的支持，從而提高專案管理效率。
### Q：Aspose.Tasks for .NET 是否有可用的授權選項？
答：是的，Aspose.Tasks for .NET 提供靈活的許可選項，包括用於試用目的的臨時許可證和用於商業用途的完整許可證。
### Q：我可以在哪裡尋求 Aspose.Tasks for .NET 的協助或支援？
答：有關 Aspose.Tasks for .NET 的任何問題或協助，您可以造訪支援論壇：[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).## 完整原始碼