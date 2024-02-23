---
title: 在 Aspose.Tasks for .NET 中管理项目大纲代码
linktitle: 在 Aspose.Tasks 中管理大纲代码
second_title: Aspose.Tasks .NET API
description: 学习使用 Aspose.Tasks for .NET 管理 MS Project 大纲代码。毫不费力地简化项目组织。
type: docs
weight: 10
url: /zh/net/outline-code-page-settings/outline-codes/
---
## 介绍
在本教程中，我们将探讨如何使用 Aspose.Tasks for .NET 管理 Microsoft Project 大纲代码。大纲代码是 Microsoft Project 中的自定义字段，允许用户根据特定条件对任务进行分类和组织。 Aspose.Tasks 简化了以编程方式读取和操作这些大纲代码的过程。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1.  Aspose.Tasks for .NET 库：从以下位置下载并安装 Aspose.Tasks for .NET 库：[网站](https://releases.aspose.com/tasks/net/).
2. 开发环境：为.NET编程搭建合适的开发环境，例如Visual Studio。
3. C#基础知识：熟悉C#编程语言有利于理解代码示例。

## 导入命名空间
首先，您需要将必要的命名空间导入到您的 C# 项目中。这允许您访问 Aspose.Tasks 库提供的类和方法。
1. 打开 Visual Studio：启动 Visual Studio IDE。
2. 创建新项目：启动一个新的 C# 项目或打开一个要使用 Aspose.Tasks 的现有项目。
3. 添加 Aspose.Tasks 参考：在解决方案资源管理器中右键单击您的项目，选择“管理 NuGet 包”，搜索“Aspose.Tasks”，然后安装最新版本。
4. 导入 Aspose.Tasks 命名空间：在 C# 文件的顶部，添加以下 using 指令：
```csharp
using Aspose.Tasks;
using System;

```
## 第 1 步：定义文档目录
首先，设置包含 MS Project 文件的目录的路径。
```csharp
String DataDir = "Your Document Directory";
```
代替`"Your Document Directory"`与项目文件的实际路径。
## 第 2 步：加载项目文件
实例化一个新的`Project`通过加载 MS Project 文件来实现对象。
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
这将使用指定的文件初始化项目对象。
## 第三步：阅读大纲代码
迭代项目中的所有任务并检索其大纲代码。
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
此代码片段循环遍历每个任务，检查其是否有大纲代码，并打印与该任务关联的每个大纲代码的字段 Id、值 Guid 和值 Id 等详细信息。

## 结论
总之，Aspose.Tasks for .NET 提供了以编程方式管理 Microsoft Project 大纲代码的强大功能。通过遵循本教程中概述的步骤，您可以使用 C# 高效地读取和操作 MS Project 文件中的大纲代码。
## 常见问题解答
### 问：我可以使用Aspose.Tasks修改大纲代码吗？
答：是的，您可以使用 Aspose.Tasks for .NET 以编程方式修改大纲代码。只需访问任务的大纲代码并根据需要更新其值即可。
### 问：Aspose.Tasks 是否与所有版本的 Microsoft Project 兼容？
答：Aspose.Tasks 支持多种 Microsoft Project 版本，包括 2003、2007、2010、2013、2016 和 2019。
### 问：Aspose.Tasks 是否需要商业使用许可证？
答：是的，Aspose.Tasks 的商业用途需要有效的许可证。您可以从 Aspose 网站获取许可证。
### 问：我可以在购买前试用 Aspose.Tasks 吗？
答：是的，您可以从网站下载 Aspose.Tasks 的免费试用版来评估其特性和功能。
### 问：我在哪里可以获得 Aspose.Tasks 的支持？
答：您可以通过访问论坛获得 Aspose.Tasks 的支持：[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).## 完整源代码