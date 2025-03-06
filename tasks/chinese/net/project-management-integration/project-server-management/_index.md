---
title: 使用 Aspose.Tasks 管理 MS Project Server
linktitle: 使用 Aspose.Tasks 管理 Project Server
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 解锁无缝 MS Project Server 管理。轻松自动化项目任务。
weight: 23
url: /zh/net/project-management-integration/project-server-management/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 管理 MS Project Server

## 介绍
在本教程中，我们将深入研究使用 Aspose.Tasks for .NET 管理 MS Project Server。 Aspose.Tasks 是一个功能强大的库，使开发人员能够以编程方式处理 Microsoft Project 文件，从而实现项目数据的无缝集成和操作。
## 先决条件
在我们深入使用 Aspose.Tasks 管理 MS Project Server 之前，请确保您已设置以下先决条件：
1. Microsoft Project Server：您需要访问 Microsoft Project Server 实例，在该实例中您具有管理权限或至少具有创建和管理项目的权限。
2.  Aspose.Tasks for .NET 库：确保您已下载并安装 Aspose.Tasks for .NET 库。您可以从[网站](https://releases.aspose.com/tasks/net/).
3. 凭据：获取必要的凭据以通过 MS Project Server 实例进行身份验证。这通常包括用户名和密码。
## 导入命名空间
在开始之前，请确保您已在 C# 代码中导入了所需的命名空间：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## 第 1 步：设置身份验证凭据
首先，您需要设置身份验证凭据以连接到 MS Project Server 实例。这包括域地址、用户名和密码。
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa"；
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## 第 2 步：加载项目
接下来，加载要使用 Aspose.Tasks 管理的 MS Project 文件。
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## 第3步：创建项目服务器管理器
实例化一个`ProjectServerManager`使用先前定义的凭据的对象。
```csharp
var manager = new ProjectServerManager(credentials);
```
## 第 4 步：定义保存选项
为您的项目定义任何特定的保存选项。例如，您可以设置操作的超时时间。
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## 第 5 步：创建或更新项目
最后，在 MS Project Server 上创建或更新项目。
```csharp
manager.CreateNewProject(project, options);
```
恭喜！您已使用 Aspose.Tasks for .NET 成功管理 MS Project Server。

## 结论
在本教程中，我们探讨了如何使用 Aspose.Tasks for .NET 以编程方式管理 MS Project Server。通过提供的步骤，您可以将 Aspose.Tasks 无缝集成到 .NET 应用程序中，以自动执行 MS Project Server 上的项目管理任务。
## 常见问题解答
### 问：Aspose.Tasks 是否与所有版本的 Microsoft Project Server 兼容？
答：Aspose.Tasks 支持与各种版本的 Microsoft Project Server 集成，确保不同环境之间的兼容性。
### 问：我可以使用 Aspose.Tasks 对项目执行批量操作吗？
答：是的，Aspose.Tasks 允许您执行批量操作，例如在 MS Project Server 上创建、更新和删除项目。
### 问：Aspose.Tasks 是否提供项目调度和资源管理支持？
答：当然，Aspose.Tasks 为项目调度、资源分配和任务管理功能提供全面支持。
### 问：是否可以使用 Aspose.Tasks 自动执行报告任务？
答：是的，Aspose.Tasks 使您能够根据项目数据自动生成自定义报告，从而促进高效的项目监控和分析。
### 问：我可以在购买之前试用 Aspose.Tasks 吗？
答：是的，您可以通过访问免费试用版来探索 Aspose.Tasks 的功能[网站](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
