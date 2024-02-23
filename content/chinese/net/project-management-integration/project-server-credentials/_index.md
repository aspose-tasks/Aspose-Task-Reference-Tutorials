---
title: 在 Aspose.Tasks 中管理 MS Project Server 凭据
linktitle: 在 Aspose.Tasks 中管理 Project Server 凭据
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 无缝管理 MS Project Server 凭据。提高项目管理效率。
type: docs
weight: 22
url: /zh/net/project-management-integration/project-server-credentials/
---
## 介绍
在项目管理领域，有效的协调和无缝沟通对于项目成功执行至关重要。 Aspose.Tasks for .NET 提供了一个用于管理 Microsoft Project Server 凭据的全面解决方案，使用户能够安全地访问和操作项目数据。本教程深入探讨使用 Aspose.Tasks for .NET 管理 MS Project Server 凭据的过程，指导用户完成每个步骤以确保流畅的体验。
## 先决条件
在开始使用 Aspose.Tasks for .NET 管理 MS Project Server 凭据之前，请确保满足以下先决条件：
### 1.安装Aspose.Tasks for .NET
首先，从提供的下载并安装 Aspose.Tasks for .NET[下载链接](https://releases.aspose.com/tasks/net/),按照安装说明将该库无缝集成到您的 .NET 环境中。
### 2. 访问凭证
收集访问 MS Project Server 所需的必要凭据。这包括与 Project Server 关联的 SharePoint 域地址、用户名和密码。

## 导入命名空间
在您的 .NET 项目中，导入所需的命名空间以有效利用 Aspose.Tasks for .NET 提供的功能。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## 第1步：定义文档目录路径
```csharp
String DataDir = "Your Document Directory";
```
## 步骤 2：设置 SharePoint 域地址、用户名和密码
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa"；
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## 步骤 3：创建 Project Server 凭据
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## 第 4 步：加载项目文件
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## 第 5 步：初始化项目服务器管理器
```csharp
var manager = new ProjectServerManager(credentials);
```
## 第6步：创建新项目
```csharp
manager.CreateNewProject(newProject);
```
## 第7步：检索项目列表
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## 第 8 步：遍历项目列表
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## 结论
有效管理 MS Project Server 凭据对于简化项目管理至关重要。 Aspose.Tasks for .NET 通过提供一组强大的功能来简化此过程。通过遵循本教程中概述的分步指南，用户可以将 Aspose.Tasks for .NET 无缝集成到其项目中，确保安全访问和操作项目数据。
## 常见问题解答
### 问：Aspose.Tasks for .NET 是否与所有版本的 Microsoft Project Server 兼容？
答：Aspose.Tasks for .NET 旨在与 Microsoft Project Server 的各个版本兼容，确保用户的多功能性和灵活性。
### 问：我可以将 Aspose.Tasks for .NET 集成到我现有的 .NET 项目中吗？
答：是的，Aspose.Tasks for .NET 可以无缝集成到现有的 .NET 项目中，从而促进高效的项目管理功能。
### 问：Aspose.Tasks for .NET 是否提供对访问项目资源的支持？
答：当然可以，Aspose.Tasks for .NET 为访问和操作项目资源提供全面的支持，从而提高项目管理效率。
### 问：Aspose.Tasks for .NET 是否有可用的许可选项？
答：是的，Aspose.Tasks for .NET 提供灵活的许可选项，包括用于试用目的的临时许可证和用于商业用途的完整许可证。
### 问：我可以在哪里寻求 Aspose.Tasks for .NET 的帮助或支持？
答：有关 Aspose.Tasks for .NET 的任何疑问或帮助，您可以访问支持论坛：[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).## 完整源代码