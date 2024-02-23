---
title: 使用 Aspose.Tasks 掌握项目数据
linktitle: 在 Aspose.Tasks 中处理项目数据
second_title: Aspose.Tasks .NET API
description: 了解如何使用 .NET 中的 Aspose.Tasks 操作 Microsoft Project 数据。轻松创建任务、添加资源和保存项目。
type: docs
weight: 16
url: /zh/net/project-management-integration/project-data/
---
## 介绍
在本教程中，我们将探讨如何使用 .NET 的 Aspose.Tasks 库处理 Microsoft Project 数据。 Aspose.Tasks 提供了强大的功能来操作项目文件，包括创建任务、添加资源、设置属性以及以各种格式保存项目。
## 先决条件
在开始之前，请确保您具备以下条件：
1.  Aspose.Tasks 库的安装：从以下位置下载并安装 Aspose.Tasks 库：[这里](https://releases.aspose.com/tasks/net/).
2. 开发环境：确保您已设置 .NET 开发环境。
3. C# 基础知识：熟悉 C# 编程语言将会很有帮助。

## 导入命名空间
在使用 Aspose.Tasks 之前，将必要的命名空间导入到您的项目中：
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 第 1 步：初始化项目对象
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project();
```
这一行初始化了一个新的实例`Project`类，代表 Microsoft Project 文件。
## 第2步：设置项目属性
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
这些行演示了如何设置项目的属性，例如工作格式和任务创建模式。
## 第三步：添加任务
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
这里，一个名为“Task 1”的新任务被添加到项目的根任务中。
## 步骤 4：设置任务属性
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
这些行设置“任务 1”的开始日期、持续时间和完成日期。
## 第 5 步：添加资源
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
本部分演示如何向项目添加工作资源。
## 步骤 6：为任务分配资源
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
这些行显示如何将先前添加的工作资源分配给具有特定开始、工作和完成日期的“任务 1”。
## 第7步：保存项目
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
最后，项目以 Microsoft Project XML 文件格式保存。

## 结论
在本教程中，我们学习了如何使用 .NET 中的 Aspose.Tasks 库处理 Microsoft Project 数据。通过遵循分步指南，您可以操作项目文件、添加任务、资源、向任务分配资源以及以各种格式保存项目。
## 常见问题解答
### 问：Aspose.Tasks 可以处理复杂的项目结构吗？
答：是的，Aspose.Tasks 为复杂的项目结构提供全面的支持，使您能够有效地管理任务、资源和分配。
### 问：Aspose.Tasks 是否与不同版本的 Microsoft Project 兼容？
答：Aspose.Tasks 支持多种 Microsoft Project 版本，确保不同环境之间的兼容性。
### 问：我可以将 Aspose.Tasks 与其他 .NET 库集成吗？
答：当然，Aspose.Tasks 与其他 .NET 库无缝集成，为您的开发项目提供灵活性。
### 问：Aspose.Tasks 是否提供对项目调度算法的支持？
答：是的，Aspose.Tasks 包含先进的调度算法，可以帮助您优化项目时间表和资源利用率。
### 问：是否有针对 Aspose.Tasks 用户的社区论坛？
答：是的，您可以找到有用的资源并与其他 Aspose.Tasks 用户互动[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).