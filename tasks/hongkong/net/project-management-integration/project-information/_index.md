---
title: 在 Aspose.Tasks 中提取 MS 項目信息
linktitle: 在 Aspose.Tasks 中提取項目信息
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 輕鬆擷取 MS Project 資訊。深入了解我們的綜合教學。
weight: 20
url: /zh-hant/net/project-management-integration/project-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中提取 MS 項目信息

## 介紹
您是否希望使用 Aspose.Tasks for .NET 從 Microsoft Project 檔案中高效提取資訊？在本教程中，我們將逐步指導您完成流程。但在我們深入了解實作細節之前，我們首先確保您擁有所需的一切。
## 先決條件
在開始之前，請確保您具備以下條件：
### 1..NET 的 Aspose.Tasks
請確定您已安裝 Aspose.Tasks for .NET 程式庫。如果您還沒有這樣做，您可以從[.NET 網站的 Aspose.Tasks](https://releases.aspose.com/tasks/net/).
### 2. SharePoint 憑證
您需要憑證才能存取儲存 MS Project 檔案的 SharePoint。確保您擁有以下資訊：
- SharePoint 網域位址
- 使用者名稱
- 密碼
## 導入命名空間
解決了先決條件後，就可以將必要的命名空間匯入到您的專案中了。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
現在讓我們將提取 MS Project 資訊的過程分解為多個步驟。
## 第 1 步：提供憑證
首先，您需要提供 SharePoint 憑證才能存取 Project Server。
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa"；
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## 第 2 步：初始化專案伺服器管理員
接下來，初始化一個`ProjectServerManager`具有提供的憑證的實例。
```csharp
var reader = new ProjectServerManager(credentials);
```
## 步驟3：檢索項目列表
現在，您可以從 Project Server 檢索項目清單。
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## 第四步：列印項目訊息
最後，遍歷項目列表並列印其資訊。
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## 結論
恭喜！您已成功學習如何使用 Aspose.Tasks for .NET 擷取 MS Project 資訊。有了這些知識，您現在可以將此功能無縫整合到您的 .NET 應用程式中。
## 常見問題解答
### 問題 1：我可以將 Aspose.Tasks for .NET 與任何版本的 Microsoft Project 一起使用嗎？
答：是的，Aspose.Tasks for .NET 支援各種版本的 Microsoft Project，包括 2003、2007、2010、2013、2016 和 2019。
### Q2：Aspose.Tasks for .NET 與 Windows 和 Linux 平台相容嗎？
答：是的，Aspose.Tasks for .NET 與 Windows 和 Linux 平台相容，使其適用於不同的開發環境。
### Q3：我可以使用 Aspose.Tasks for .NET 來提取任務依賴項嗎？
答：當然！ Aspose.Tasks for .NET 提供了強大的功能，不僅可以提取基本的項目信息，還可以提取任務依賴關係和其他複雜的細節。
### Q4：Aspose.Tasks for .NET 有提供技術支援嗎？
答：是的，您可以透過 Aspose.Tasks for .NET 獲得技術支持[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)，您可以在這裡提出問題並尋求專家的協助。
### Q5：我可以在購買之前試用 Aspose.Tasks for .NET 嗎？
答：當然可以！您可以從以下網站免費試用 Aspose.Tasks for .NET[發布頁面](https://releases.aspose.com/)，讓您在做出購買決定之前探索其功能。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
