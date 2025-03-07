---
title: 在 Aspose.Tasks 中提取 MS 项目信息
linktitle: 在 Aspose.Tasks 中提取项目信息
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 轻松提取 MS Project 信息。深入了解我们的综合教程。
weight: 20
url: /zh/net/project-management-integration/project-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中提取 MS 项目信息

## 介绍
您是否希望使用 Aspose.Tasks for .NET 从 Microsoft Project 文件中高效提取信息？在本教程中，我们将逐步指导您完成该过程。但在我们深入了解实施细节之前，我们首先确保您拥有所需的一切。
## 先决条件
在开始之前，请确保您具备以下条件：
### 1..NET 的 Aspose.Tasks
确保您已安装 Aspose.Tasks for .NET 库。如果您还没有这样做，您可以从[.NET 网站的 Aspose.Tasks](https://releases.aspose.com/tasks/net/).
### 2. SharePoint 凭据
您需要凭据才能访问存储 MS Project 文件的 SharePoint。确保您拥有以下信息：
- SharePoint 域地址
- 用户名
- 密码
## 导入命名空间
解决了先决条件后，就可以将必要的命名空间导入到您的项目中了。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
现在让我们将提取 MS Project 信息的过程分解为多个步骤。
## 第 1 步：提供凭据
首先，您需要提供 SharePoint 凭据才能访问 Project Server。
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa"；
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## 第 2 步：初始化项目服务器管理器
接下来，初始化一个`ProjectServerManager`具有提供的凭据的实例。
```csharp
var reader = new ProjectServerManager(credentials);
```
## 第3步：检索项目列表
现在，您可以从 Project Server 检索项目列表。
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## 第四步：打印项目信息
最后，遍历项目列表并打印其信息。
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
## 结论
恭喜！您已成功学习如何使用 Aspose.Tasks for .NET 提取 MS Project 信息。有了这些知识，您现在可以将此功能无缝集成到您的 .NET 应用程序中。
## 常见问题解答
### 问题 1：我可以将 Aspose.Tasks for .NET 与任何版本的 Microsoft Project 一起使用吗？
答：是的，Aspose.Tasks for .NET 支持各种版本的 Microsoft Project，包括 2003、2007、2010、2013、2016 和 2019。
### Q2：Aspose.Tasks for .NET 与 Windows 和 Linux 平台兼容吗？
答：是的，Aspose.Tasks for .NET 与 Windows 和 Linux 平台兼容，使其适用于不同的开发环境。
### Q3：我可以使用 Aspose.Tasks for .NET 提取任务依赖项吗？
答：当然！ Aspose.Tasks for .NET 提供了强大的功能，不仅可以提取基本的项目信息，还可以提取任务依赖关系和其他复杂的细节。
### Q4：Aspose.Tasks for .NET 提供技术支持吗？
答：是的，您可以通过 Aspose.Tasks for .NET 获得技术支持[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)，您可以在这里提出问题并寻求专家的帮助。
### Q5：我可以在购买之前试用 Aspose.Tasks for .NET 吗？
答：当然可以！您可以从以下网站免费试用 Aspose.Tasks for .NET[发布页面](https://releases.aspose.com/)，让您在做出购买决定之前探索其功能。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
