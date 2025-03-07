---
title: 在 Aspose.Tasks 中设置重复任务参数
linktitle: 在 Aspose.Tasks 中设置重复任务参数
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 在 Microsoft Project 中设置重复任务参数。带有分步指南的综合教程。
weight: 14
url: /zh/net/rate-recurring-tasks/recurring-task-parameters/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中设置重复任务参数

## 介绍
在本教程中，我们将指导您完成使用 Aspose.Tasks for .NET 设置 Microsoft Project 重复任务参数的过程。
## 先决条件
在开始之前，请确保您具备以下条件：
1. 对 C# 编程语言有基本了解。
2. 安装了 Visual Studio 或任何其他 C# IDE。
3. Aspose.Tasks for .NET 库已安装并在您的项目中引用。

## 导入命名空间
首先，您需要在 C# 代码中导入必要的命名空间：
```csharp
using Aspose.Tasks;
using System;

```
## 第 1 步：定义文档目录
```csharp
String DataDir = "Your Document Directory";
```
代替`"Your Document Directory"`与您的文档目录的路径。
## 第 2 步：加载项目文件
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
这行代码将 Microsoft Project 文件加载到`project`多变的。
## 步骤 3：定义重复任务参数
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
在此，您可以定义重复任务的参数，例如任务名称、持续时间、重复模式、重复范围以及是否忽略资源日历。
## 步骤 4：为重复任务设置日历
```csharp
parameters.SetCalendar(project, "Standard");
```
此步骤设置重复任务的日历。在此示例中，它将日历设置为“标准”。
## 第5步：向项目添加参数
```csharp
project.RootTask.Children.Add(parameters);
```
最后，将参数添加到项目的根任务中。

## 结论
在本教程中，我们演示了如何使用 Aspose.Tasks for .NET 设置 Microsoft Project 重复任务参数。通过执行这些步骤，您可以有效地管理项目中的重复任务。
## 常见问题解答
### 我可以进一步自定义重复模式吗？
是的，Aspose.Tasks 提供了各种重复模式和选项，可根据您的项目要求进行自定义。
### 购买前是否有试用版？
是的，您可以从 Aspose.Tasks 下载免费试用版[网站](https://purchase.aspose.com/buy)评估图书馆的功能。
### Aspose.Tasks 是否支持其他项目文件格式？
是的，Aspose.Tasks 支持各种项目文件格式，包括 MPP、XML、XLSX 等。
### 如果在实施过程中遇到任何问题，我可以获得支持吗？
是的，您可以访问 Aspose.Tasks 论坛寻求社区的帮助，或联系支持人员以获得直接帮助。
### 我如何获得 Aspose.Tasks 的临时许可证？
您可以从以下机构获得临时许可证[网站](https://purchase.aspose.com/temporary-license/)用于测试目的。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
