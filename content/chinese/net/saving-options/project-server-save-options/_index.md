---
title: Aspose.Tasks 的服务器保存 MS 项目选项
linktitle: Aspose.Tasks 的 Project Server 保存选项
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Project Server 集成保存 Aspose.Tasks 的 Microsoft Project 选项。增强您的项目管理工作流程。
type: docs
weight: 16
url: /zh/net/saving-options/project-server-save-options/
---
## 介绍
在本教程中，我们将深入研究使用 Project Server 保存 Aspose.Tasks 的 Microsoft Project 选项。 Aspose.Tasks 是一个功能强大的 .NET API，允许开发人员以编程方式处理 Microsoft Project 文件。利用 Project Server 功能，我们可以将 Aspose.Tasks 无缝集成到我们的项目管理工作流程中。本教程将逐步指导您完成该过程。
## 先决条件
在开始之前，请确保您具备以下先决条件：
1.  Aspose.Tasks for .NET：从以下位置安装 Aspose.Tasks for .NET[下载链接](https://releases.aspose.com/tasks/net/).
   
2. 访问 Project Server：您将需要访问凭据和 Project Server 实例的 URL。如果您没有，您可以从以下位置获取免费试用版：[这里](https://releases.aspose.com/).
3. Microsoft Project 文件：准备要使用 Aspose.Tasks 保存的 Microsoft Project 文件 (.mpp)。

## 导入命名空间
首先，您需要在项目中导入必要的命名空间：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## 第 1 步：初始化项目和凭证
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
确保更换`"Your Document Directory"`, `URL`, `Domain`, `UserName`，和`Password`与你的实际价值观。
## 第2步：创建项目服务器管理器
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## 第 3 步：定义保存选项
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
调整`ProjectGuid`, `ProjectName`, `Timeout`，和`PollingInterval`根据您的要求。
## 第 4 步：将项目保存到服务器
```csharp
manager.CreateNewProject(project, options);
```
这将使用指定的选项将项目保存到 Project Server。

## 结论
在本教程中，我们学习了如何使用 Project Server 集成保存 Aspose.Tasks 的 Microsoft Project 选项。通过执行这些步骤，您可以将 Aspose.Tasks 无缝整合到您的项目管理工作流程中，从而提高效率和生产力。
## 常见问题解答
### 问：我可以将 Aspose.Tasks 与不同版本的 Microsoft Project 一起使用吗？
答：是的，Aspose.Tasks 支持各种版本的 Microsoft Project，确保不同环境之间的兼容性。
### 问：Aspose.Tasks 有试用版吗？
答：是的，您可以从以下位置获取 Aspose.Tasks 的免费试用版：[这里](https://releases.aspose.com/).
### 问：Aspose.Tasks 支持多线程吗？
答：是的，Aspose.Tasks 被设计为线程安全的，允许并发访问项目数据。
### 问：使用 Project Server 集成时可以自定义保存选项吗？
答：是的，您可以定制项目名称、超时和轮询间隔等保存选项来满足您的要求。
### 问：在哪里可以找到对 Aspose.Tasks 的支持？
答：您可以在以下网站上找到支持和帮助：[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).