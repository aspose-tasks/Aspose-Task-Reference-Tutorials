---
title: 在 Aspose.Tasks 中处理 MS Project 资源分配
linktitle: 在 Aspose.Tasks 中处理资源分配
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 高效处理 MS Project 资源分配。该综合指南为开发人员提供了分步指导。
weight: 11
url: /zh/net/resource-risk-analysis/resource-assignments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中处理 MS Project 资源分配

## 介绍
在本教程中，我们将深入研究如何使用 Aspose.Tasks for .NET 高效处理 Microsoft Project 资源分配。 Aspose.Tasks 是一个功能强大的 API，允许开发人员以编程方式操作 Microsoft Project 文件。通过执行这些步骤，您将了解如何在 .NET 应用程序中有效管理资源分配。
## 先决条件
在我们开始之前，请确保您满足以下先决条件：

## 导入命名空间
首先，您需要导入必要的命名空间以在 .NET 项目中使用 Aspose.Tasks 功能。这包括：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
现在让我们将提供的示例分解为多个步骤，以便全面了解如何使用 Aspose.Tasks 处理 MS Project 资源分配。
## 第 1 步：设置项目和日历设置
首先，创建一个新的项目实例并设置项目的日历设置：
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## 第 2 步：向项目添加任务
接下来，将新任务添加到项目的根任务中：
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## 步骤 3：创建资源分配并生成时间分段数据
现在，为任务创建新的资源分配并生成时间分段数据：
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## 第 4 步：拆分任务
通过提供开始日期和完成日期将任务分成多个部分：
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## 第 5 步：设置工作轮廓
设置分配的工作轮廓类型：
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## 第 6 步：保存项目
最后，保存所做更改的项目文件：
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## 结论
总之，使用 Aspose.Tasks for .NET 处理 Microsoft Project 资源分配是一个简单的过程。通过遵循本教程中概述的步骤，您可以有效地管理 .NET 应用程序中的资源分配。
## 常见问题解答
### Aspose.Tasks 可以处理复杂的项目结构吗？
是的，Aspose.Tasks 提供了全面的功能来有效地处理复杂的项目结构。
### Aspose.Tasks 与不同版本的 Microsoft Project 兼容吗？
是的，Aspose.Tasks 支持各种版本的 Microsoft Project，确保不同环境之间的兼容性。
### 我可以根据具体要求定制资源分配吗？
当然，Aspose.Tasks 为资源分配提供了广泛的自定义选项，以满足特定的项目需求。
### Aspose.Tasks 是否支持将项目数据导出为其他格式？
是的，Aspose.Tasks 允许将项目数据导出为各种格式，例如 XML、PDF 和 HTML 等。
### Aspose.Tasks 用户可以获得技术支持吗？
是的，Aspose 通过其论坛和其他渠道提供专门的技术支持，以帮助用户解决任何疑问或问题。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
