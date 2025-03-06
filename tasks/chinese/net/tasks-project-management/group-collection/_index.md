---
title: 在 Aspose.Tasks 中管理项目集合
linktitle: 在 Aspose.Tasks 中管理组集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 高效管理 MS Project 集合。请遵循我们的分步指南。
type: docs
weight: 26
url: /zh/net/tasks-project-management/group-collection/
---
## 介绍
在本教程中，我们将探讨如何使用 Aspose.Tasks for .NET 管理组 MS Project 集合。管理组集合对于在项目中有效地组织和操作任务和资源至关重要。
## 先决条件
在继续本教程之前，请确保您满足以下先决条件：
1.  Aspose.Tasks for .NET 库：从以下位置下载并安装 Aspose.Tasks for .NET 库：[下载链接](https://releases.aspose.com/tasks/net/).
2. C# 基础知识：熟悉 C# 编程语言基础知识，因为本教程涉及 C# 编码。
3. 开发环境：设置开发环境，例如 Visual Studio 或任何其他支持 .NET 开发的 IDE。

## 导入命名空间
首先，我们导入必要的命名空间，以便在 C# 代码中使用 Aspose.Tasks 功能。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## 第 1 步：加载项目
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
此步骤涉及将 MS Project 文件加载到 Aspose.Tasks 项目对象中，以便我们对其执行操作。
## 第 2 步：迭代任务组
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
在这里，我们迭代项目中的任务组，打印每个组菜单中的索引、名称和可见性等详细信息。
## 第 3 步：迭代资源组
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
同样，此步骤迭代资源组，在菜单中显示它们的索引、名称和可见性。
## 步骤 4：清除组并将其复制到另一个项目
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
//清除其他项目组
otherProject.TaskGroups.Clear();
//将组复制到其他项目
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
在这里，我们清除另一个项目的组，然后将组从原始项目复制到它。
## 步骤 5：添加自定义任务组
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
在此步骤中，我们创建一个自定义任务组，并将其添加到其他项目（如果尚不存在）。
## 第 6 步：删除所有组
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
最后，我们从其他项目中删除所有组。

## 结论
在 Aspose.Tasks for .NET 中管理组 MS Project 集合对于有效组织和操作项目数据至关重要。通过遵循本教程中概述的步骤，您可以有效地处理项目中的任务和资源组，从而改进整体项目管理。
## 常见问题解答
### Aspose.Tasks for .NET 是否与所有版本的 MS Project 兼容？
Aspose.Tasks for .NET支持各种版本的Microsoft Project，包括2003、2007、2010、2013、2016和2019。
### 我可以使用 Aspose.Tasks for .NET 自定义组属性吗？
是的，您可以使用 Aspose.Tasks for .NET 自定义组属性，例如名称和可见性。
### Aspose.Tasks for .NET 是否提供跨平台兼容性？
Aspose.Tasks for .NET 主要针对 .NET 框架，但它可以用于 .NET Core 和 .NET Standard 的跨平台场景。
### 如何获得 Aspose.Tasks for .NET 支持？
您可以通过以下方式获得对 Aspose.Tasks for .NET 的支持[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks for .NET 是否有试用版？
是的，您可以从以下位置下载 Aspose.Tasks for .NET 的免费试用版：[网站](https://releases.aspose.com/).