---
title: 在 Aspose.Tasks 中配置工作时间
linktitle: 在 Aspose.Tasks 中配置工作时间
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks 增强 .NET 中的项目调度。轻松配置工作时间以实现精确的资源管理。立即下载库！
weight: 13
url: /zh/net/time-recurrence-configuration/working-times/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中配置工作时间

## 介绍
在项目管理中，精确控制工作时间对于准确调度和资源分配至关重要。 Aspose.Tasks for .NET 提供了一个强大的解决方案来处理项目中的工作时间信息。本教程将指导您完成在 .NET 环境中使用 Aspose.Tasks 配置工作时间的过程。
## 先决条件
在深入学习本教程之前，请确保您具备以下条件：
- 对 C# 编程语言有基本了解。
- 安装了 .NET 库的 Aspose.Tasks。你可以下载它[这里](https://releases.aspose.com/tasks/net/).
- 设置 Visual Studio 或任何首选的 C# 开发环境。
## 导入命名空间
首先导入必要的命名空间来访问 Aspose.Tasks 功能：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## 第 1 步：创建日历
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
在这里，我们启动一个新项目，并基于标准日历创建一个名为“MyCalendar”的日历。该日历将用于定义具体的工作时间。

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## 第 2 步：显示工作周信息
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
此步骤打印指定日历中的总工作日数。
## 第 3 步：工作时间详情
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
在这一部分中，我们迭代一周中的每一天，打印日期类型和相关的工作时间。您可以根据您的项目要求自定义每个工作日的工作时间。
## 结论
在 Aspose.Tasks for .NET 中有效配置工作时间可确保准确的项目规划和资源管理。通过遵循此分步指南，您可以将工作时间调整无缝集成到项目工作流程中。
## 经常问的问题
### Aspose.Tasks适合大型项目管理吗？
是的，Aspose.Tasks 旨在处理各种规模的项目，为高效的项目管理提供强大的功能。
### 我可以为不同的团队成员设置不同的工作时间吗？
绝对地。您可以根据每个资源自定义工作时间，从而实现个性化的时间表。
### Aspose.Tasks 是否支持与其他项目管理工具集成？
是的，Aspose.Tasks 有助于与各种项目管理工具集成，增强互操作性。
### 是否可以导入/导出不同格式的项目数据？
Aspose.Tasks支持多种文件格式，实现项目数据的无缝导入/导出操作。
### Aspose.Tasks 更新发布的频率是多少？
定期发布更新以确保与最新技术的兼容性并解决用户反馈。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
