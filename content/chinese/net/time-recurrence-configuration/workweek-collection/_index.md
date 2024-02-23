---
title: 在 Aspose.Tasks 中自定义工作周
linktitle: Aspose.Tasks 中工作周的集合
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中自定义工作周。创建个性化项目日历的分步指南。现在下载！
type: docs
weight: 17
url: /zh/net/time-recurrence-configuration/workweek-collection/
---
## 介绍
欢迎来到我们关于使用 Aspose.Tasks for .NET 创建自定义工作周的教程！在本分步指南中，我们将引导您完成为项目中的日历定义个性化工作周的过程。 Aspose.Tasks 是一个功能强大的库，使开发人员能够在其 .NET 应用程序中高效地处理 Microsoft Project 文档。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1. Visual Studio：确保您的计算机上安装了 Visual Studio。
2.  Aspose.Tasks for .NET：下载并安装 Aspose.Tasks 库。你可以找到下载链接[这里](https://releases.aspose.com/tasks/net/).
3. C# 基础知识：熟悉 C# 编程语言基础知识。
## 导入命名空间
在您的 C# 项目中，确保导入必要的命名空间：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 第 1 步：创建项目和日历
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## 第 2 步：定义自定义工作周
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## 第 3 步：设置工作日
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## 第 4 步：显示工作周信息
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
该综合指南使您能够使用 Aspose.Tasks for .NET 高效地创建和管理自定义工作周。
## 结论
总之，Aspose.Tasks for .NET 提供了一个强大的解决方案，用于处理具有自定义工作周的项目日历。通过学习本教程，您已了解如何在项目中创建和显示有关自定义工作周的信息。
## 常见问题解答
### 我可以在一个项目中设置多个自定义工作周吗？
是的，您可以将多个自定义工作周添加到项目日历中。
### 如何修改现有的工作周？
使用提供的`WorkWeek`修改现有工作周的属性和方法。
### Aspose.Tasks 与 .NET Core 兼容吗？
是的，Aspose.Tasks 支持 .NET Core。
### 我可以将具有自定义工作周的项目导出为 Microsoft Project 文件格式吗？
当然，Aspose.Tasks 允许您以各种格式保存项目，包括 Microsoft Project。
### 我在哪里可以寻求 Aspose.Tasks 相关查询的支持？
访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)寻求任何支持或帮助。