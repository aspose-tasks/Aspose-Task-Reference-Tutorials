---
title: Aspose.Tasks 中 Microsoft Project 数据库的设置
linktitle: Aspose.Tasks 中 Microsoft Project 数据库的设置
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks 配置 Microsoft Project 数据库设置，以便无缝集成到 .NET 应用程序中。
type: docs
weight: 19
url: /zh/net/advanced-concepts/msp-database-settings/
---
## 介绍

如果您使用 Aspose.Tasks 在 .NET 应用程序中使用 Microsoft Project 数据库，则需要配置必要的设置以无缝导入项目数据。本教程将逐步指导您完成该过程。

## 先决条件

在开始之前，请确保您具备以下条件：

1.  Aspose.Tasks for .NET：下载并安装 Aspose.Tasks 库[这里](https://releases.aspose.com/tasks/net/).
2. 访问 Microsoft Project 数据库：您应该有权访问 Microsoft Project 数据库以从中导入数据。

## 导入命名空间

首先，确保将必要的命名空间导入到您的项目中：

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## 第 1 步：创建连接字符串

构建 Microsoft Project 数据库的连接字符串。这是一个例子：

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

确保将占位符值替换为您的实际数据库凭据。

## 步骤 2：配置 MspDbSettings

创建一个实例`MspDbSettings`并指定连接字符串和项目 GUID：

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## 第 3 步：加载项目数据

实例化一个`Project`使用配置的设置的对象：

```csharp
var project = new Project(settings);
```

## 第 4 步：保存项目数据

将加载的项目数据保存到文件中：

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## 结论

在本教程中，您学习了如何使用 Aspose.Tasks for .NET 配置访问 Microsoft Project 数据库的设置。通过执行以下步骤，您可以将项目数据无缝导入到您的应用程序中，从而促进高效的项目管理。

## 常见问题解答

### Q1：我可以将 Aspose.Tasks 与不同版本的 Microsoft Project 数据库一起使用吗？

A1：是的，Aspose.Tasks 支持各种版本的 Microsoft Project 数据库，允许灵活集成。

### Q2：如何解决数据库连接问题？

 A2：确保使用适当的凭据和数据库详细信息正确配置连接字符串。您也可以参考文档或寻求支持[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).

### Q3：Aspose.Tasks 有试用版吗？

 A3：是的，您可以从以下位置访问免费试用版：[这里](https://releases.aspose.com/).

### Q4：我可以自定义数据库交互的架构吗？

 A4：是的，您可以指定架构`MspDbSettings`根据您的数据库结构的对象。

### Q5：在哪里可以找到有关使用 Aspose.Tasks 的更详细文档？

 A5：您可以探索全面的文档[这里](https://reference.aspose.com/tasks/net/)了解 Aspose.Tasks 功能的详细见解。