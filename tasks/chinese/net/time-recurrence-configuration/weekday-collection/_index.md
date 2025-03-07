---
title: 掌握 Aspose.Tasks 中的工作日
linktitle: Aspose.Tasks 中工作日的集合
second_title: Aspose.Tasks .NET API
description: 发现 Aspose.Tasks for .NET 在轻松管理工作日方面的强大功能。自定义工作日、删除周末并轻松创建专门的日历。
weight: 11
url: /zh/net/time-recurrence-configuration/weekday-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 掌握 Aspose.Tasks 中的工作日

## 介绍
Aspose.Tasks for .NET 是一个功能强大的库，可促进项目管理数据的高效操作。在本教程中，我们将探索 Aspose.Tasks 中的工作日集合，使您能够自定义工作日、删除周末以及创建专门的日历来满足您的项目要求。无论您是经验丰富的开发人员还是新手，本分步指南都将引导您完成在 Aspose.Tasks for .NET 中处理工作日的过程。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
- 安装 Aspose.Tasks for .NET 库。您可以从[Aspose.Tasks for .NET 下载页面](https://releases.aspose.com/tasks/net/).
- 熟悉C#编程语言。
- 集成开发环境 (IDE)，例如 Visual Studio。
## 导入命名空间
首先将必要的命名空间导入到您的 C# 项目中：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 第1步：创建项目实例
初始化一个新的 Aspose.Tasks 项目：
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## 第 2 步：访问日历
检索项目日历：
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## 第 3 步：自定义工作日
清除现有工作日并设置默认工作日：
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
//以同样的方式添加其他工作日...
```
## 第 4 步：添加工作时间
添加特定工作日的工作时间：
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## 第5步：显示日历信息
将日历详细信息输出到控制台：
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
//显示每个工作日和工作时间...
```
## 第 6 步：删除周末
从工作日中删除周六和周日：
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## 第 7 步：显示更新的工作时间
输出删除周末后更新的工作时间：
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
//显示每个更新的工作日和工作时间...
```
## 第 8 步：创建 24 小时日历
创建 24 小时日历并复制工作日：
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## 结论
在本教程中，我们探索了 Aspose.Tasks for .NET 在项目日历中管理工作日的强大功能。从定制工作日到创建专门的 24 小时日历，Aspose.Tasks 简化了流程，为项目管理提供了灵活性和控制力。
## 经常问的问题
### 问：我可以将 Aspose.Tasks for .NET 与其他编程语言一起使用吗？
答：Aspose.Tasks 主要支持 .NET 语言，但也提供 Java 版本。
### 问：Aspose.Tasks for .NET 是否有免费试用版？
答：是的，您可以从以下网站下载免费试用版：[Aspose.Tasks 发布页面](https://releases.aspose.com/).
### 问：如何获得 Aspose.Tasks for .NET 支持？
答：访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)寻求社区支持或考虑购买支持计划。
### 问：在哪里可以找到 Aspose.Tasks for .NET 的综合文档？
答：请参阅[.NET 文档的 Aspose.Tasks](https://reference.aspose.com/tasks/net/)获取详细信息。
### 问：如何获得 Aspose.Tasks for .NET 的临时许可证？
答：您可以从以下机构获得临时许可证：[临时许可证页面](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
