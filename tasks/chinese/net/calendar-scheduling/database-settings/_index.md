---
title: Aspose.Tasks 中的数据库设置
linktitle: Aspose.Tasks 中的数据库设置
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 从 Primavera 数据库导入项目。在此综合教程中获取分步指导。
type: docs
weight: 29
url: /zh/net/calendar-scheduling/database-settings/
---
## 介绍

Aspose.Tasks for .NET 是一个功能强大的库，允许开发人员在其 .NET 应用程序中使用 Microsoft Project 文件。在本教程中，我们将重点介绍使用 Aspose.Tasks 从 Primavera 数据库导入项目。

## 先决条件

在我们开始之前，请确保您具备以下条件：

- C# 编程语言的基础知识。
- Visual Studio 安装在您的系统上。
- 安装了 .NET 库的 Aspose.Tasks。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/net/).
- 访问 Primavera 数据库以及必要的权限。

## 导入命名空间

首先，您需要将必要的命名空间导入到您的 C# 项目中。这些命名空间提供对使用 Aspose.Tasks for .NET 所需的类和方法的访问。

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

现在，让我们将提供的示例代码分解为多个步骤：

## 第 1 步：定义连接字符串

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

在此步骤中，我们定义连接字符串以连接到 Primavera 数据库。确保更换`DataDir`与数据库文件所在的目录。

## 第 2 步：创建数据库设置

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

在这里，我们创建一个实例`PrimaveraDbSettings`类，将连接字符串和项目 ID 作为参数传递。根据您的要求调整项目 ID。

## 第 3 步：设置提供者不变名称

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

指定提供者不变名称。在此示例中，我们使用 SQLite，但您可以根据您的数据库提供商更改它。

## 第 4 步：加载项目

```csharp
var project = new Project(settings);
```

创建一个新的`Project`对象，将数据库设置作为参数传递。

## 第 5 步：保存项目

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

最后，以指定的文件格式将项目保存到所需位置。

## 结论

在本教程中，我们学习了如何使用 Aspose.Tasks for .NET 从 Primavera 数据库导入项目。通过遵循提供的步骤，您可以将项目导入功能无缝集成到您的 .NET 应用程序中。

## 常见问题解答

### Q1：我可以使用 Aspose.Tasks for .NET 从不同的数据库提供商导入项目吗？

A1：是的，您可以通过相应地调整连接字符串和提供程序不变名称来从各种数据库提供程序导入项目。

### 问题 2：Aspose.Tasks for .NET 是否有免费试用版？

 A2：是的，您可以从以下位置获得 Aspose.Tasks for .NET 的免费试用版：[这里](https://releases.aspose.com/).

### Q3：在哪里可以找到 Aspose.Tasks for .NET 的文档？

A3：你可以找到文档[这里](https://reference.aspose.com/tasks/net/).

### Q4：如何获得 Aspose.Tasks for .NET 支持？

 A4：您可以从 Aspose.Tasks 社区论坛获得支持[这里](https://forum.aspose.com/c/tasks/15).

### Q5：我需要临时许可证才能使用 Aspose.Tasks for .NET 吗？

 A5：如果您想评估该库的全部功能，您可以从以下地址获取临时许可证：[这里](https://purchase.aspose.com/temporary-license/).