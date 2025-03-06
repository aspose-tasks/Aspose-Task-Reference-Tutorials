---
title: 在 Aspose.Tasks 中配置 MS Project 显示选项
linktitle: 在 Aspose.Tasks 中配置项目显示选项
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 以编程方式配置 MS Project 显示选项。轻松定制您的项目外观。
weight: 17
url: /zh/net/project-management-integration/project-display-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中配置 MS Project 显示选项

## 介绍
Microsoft Project 提供了大量的显示选项来自定义项目的外观。 Aspose.Tasks for .NET 提供了一个强大的框架来以编程方式操作这些选项。在本教程中，我们将探讨如何使用 Aspose.Tasks 配置 MS Project 显示选项。
## 先决条件
在深入学习本教程之前，请确保您具备以下条件：
1.  Aspose.Tasks for .NET：从以下位置下载并安装库[这里](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 文件：准备好有效的 MS Project 文件 (.mpp) 以应用显示选项。
3. C# 基础知识：需要熟悉 C# 编程语言。

## 导入命名空间
首先，确保将必要的命名空间导入到您的 C# 代码中：
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## 第 1 步：加载项目文件
使用以下命令加载 MS Project 文件`Project`Aspose.Tasks 提供的类：
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## 第 2 步：配置显示选项
现在，让我们配置 MS Project 中可用的各种显示选项：
### 禁用任务计划警告
要禁用与手动计划任务的计划冲突的警告（适用于 Project 2010 及更高版本）：
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### 在标签前添加空格
设置在数值和时间缩写前添加空格：
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### 配置时间单位的标签显示
自定义不同时间单位的显示方式：
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### 显示项目摘要任务
在一行上显示有关整个项目的摘要信息：
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### 启用任务计划建议
允许显示与手动计划任务发生冲突的建议：
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### 超链接下划线
设置为项目内的超链接添加下划线：
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## 第 3 步：保存项目
最后，使用应用的显示选项保存项目：
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for .NET 配置 MS Project 显示选项。借助这些功能，您可以以编程方式高效地自定义项目文件的外观。
## 常见问题解答
### 问：我可以将这些显示选项仅应用于特定任务吗？
答：是的，您可以使用 Aspose.Tasks API 有选择地将显示选项应用于各个任务。
### 问：这些显示选项会影响底层项目数据吗？
答：不，这些选项仅修改项目的视觉表示，不会更改底层数据。
### 问：这些显示选项是否与所有版本的 Microsoft Project 兼容？
答：不可以，某些选项可能特定于 MS Project 的某些版本。有关兼容性详细信息，请参阅文档。
### 问：我可以将显示选项恢复为默认设置吗？
答：是的，您可以使用 Aspose.Tasks API 将显示选项重置为其默认值。
### 问：以编程方式自定义显示选项有任何限制吗？
答：虽然 Aspose.Tasks 提供了广泛的自定义功能，但由于 MS Project 文件格式的限制，某些显示选项可能无法通过编程方式访问。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
