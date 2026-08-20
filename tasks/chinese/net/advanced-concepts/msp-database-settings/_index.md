---
date: 2026-03-14
description: 了解如何使用 Aspose.Tasks 为 Microsoft Project 数据库指定数据库模式，以及如何将项目数据导入 .NET 应用程序。
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks 为项目数据库指定数据库模式
url: /zh/net/advanced-concepts/msp-database-settings/
weight: 19
---

 need to keep code block placeholders unchanged.

Let's produce final translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的 Microsoft Project 数据库设置

## 介绍

如果您在 .NET 应用程序中使用 Aspose.Tasks 处理 Microsoft Project 数据库，则需要 **指定数据库模式** 并配置必要的设置，以便 **导入项目** 数据。本文将一步步指导您 **如何配置连接** 详细信息、**创建 .NET 连接字符串**，以及最终 **将项目保存为 MPP**。

## 快速答案
- **主要目标是什么？** 指定数据库模式并将 Project 数据库导入 .NET 应用。  
- **需要哪个库？** Aspose.Tasks for .NET。  
- **如何连接到 Project Server？** 构建正确的 SQL 连接字符串并使用 `MspDbSettings`。  
- **生成的文件格式是什么？** 使用 `SaveFileFormat.Mpp` 保存的 MPP 文件。  
- **可以更改模式名称吗？** 可以，设置 `MspDbSettings` 的 `Schema` 属性即可。

## 如何为 Project 数据库指定数据库模式

了解为何需要 **指定数据库模式** 非常重要。在许多企业环境中，Project Server 数据库位于自定义模式下（例如 `dbo`、`psdata`）。显式设置模式后，Aspose.Tasks 将查询正确的表，避免运行时错误并确保数据导入准确。

## 前置条件

在开始之前，请确保具备以下条件：

1. Aspose.Tasks for .NET：从 [here](https://releases.aspose.com/tasks/net/) 下载并安装 Aspose.Tasks 库。  
2. 访问 Microsoft Project 数据库的权限：您应 **拥有** 对 Microsoft Project 数据库的 **访问权限** 以便 **导入数据**。

## 导入命名空间

首先，确保在项目中导入所需的命名空间：

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## 步骤 1：创建连接字符串

构建指向 Microsoft Project 数据库的连接字符串。在这里您 **创建 .NET 连接字符串**，并定义 **如何连接到 Project Server**。

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

> **专业提示：** 仔细检查 `DataSource` 和 `InitialCatalog` 的取值；它们必须与 **服务器地址** 和 **已发布的数据库名称** 相匹配。

## 步骤 2：配置 MspDbSettings

实例化 `MspDbSettings`，传入连接字符串，并通过设置 `Schema` 属性 **指定数据库模式**。这告诉 Aspose.Tasks 使用哪个 **模式** 进行查询。

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

这里我们还 **提供了项目 GUID**，用于 **标识要加载的特定项目**。

## 步骤 3：加载项目数据

使用已配置的设置实例化 `Project` 对象。此步骤 **实际演示了如何** **导入项目** 数据，从数据库加载到 .NET 对象中。

```csharp
var project = new Project(settings);
```

## 步骤 4：保存项目数据

最后，将已加载的项目 **持久化为磁盘上的 MPP 文件**。此示例展示了使用 Aspose.Tasks API **将项目保存为 MPP** 的方法。

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

运行代码后，您将在输出目录中找到 `ImportProjectDataFromDatabase_out.mpp` 文件，可直接在 Microsoft Project 中打开。

## 结论

通过本教程，您已经学会了如何 **指定数据库模式**、**配置连接**、**导入项目** 数据以及 **将项目保存为 MPP**，全部使用 Aspose.Tasks for .NET。这些步骤帮助您将 Project Server 数据无缝集成到自定义应用中，构建强大的项目管理解决方案。

## 常见问题

### Q1：是否可以在不同版本的 Microsoft Project 数据库中使用 Aspose.Tasks？
A1：可以，Aspose.Tasks 支持多种版本的 Microsoft Project 数据库，具备灵活的集成能力。

### Q2：如何排查数据库连接问题？
A2：确保连接字符串已正确配置了相应的凭据和数据库信息。您也可以参考文档或在 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 寻求帮助。

### Q3：是否提供 Aspose.Tasks 的试用版？
A3：可以，从 [here](https://releases.aspose.com/) 获取免费试用版本。

### Q4：可以自定义数据库交互的模式吗？
A4：可以，根据您的数据库结构为 `MspDbSettings` 对象指定相应的模式。

### Q5：在哪里可以找到关于 Aspose.Tasks 的更详细文档？
A5：请访问 [here](https://reference.aspose.com/tasks/net/) 查看完整文档，获取 Aspose.Tasks 功能的深入说明。

**问：此方法能在 Azure SQL 数据库上使用吗？**  
答：完全可以。只需将 `DataSource` 调整为 Azure 服务器名称，并确保启用 TLS/SSL 设置。

**问：如何处理大型 Project 数据库而不超时？**  
答：在连接字符串中增加 `ConnectTimeout` 的值，必要时考虑分批加载项目。

---

**最后更新：** 2026-03-14  
**测试环境：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}