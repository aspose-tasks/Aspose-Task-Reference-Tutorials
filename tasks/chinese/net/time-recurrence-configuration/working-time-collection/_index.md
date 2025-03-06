---
title: 掌握 Aspose.Tasks 的工作时间
linktitle: Aspose.Tasks 中工作时间的集合
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 在有效管理项目时间表方面的强大功能。自定义日历、设置工作时间并轻松简化您的项目。
weight: 14
url: /zh/net/time-recurrence-configuration/working-time-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 掌握 Aspose.Tasks 的工作时间

## 介绍
您是否希望掌握在 Aspose.Tasks for .NET 中管理工作时间的艺术？别再犹豫了！在本分步指南中，我们将深入研究使用 Aspose.Tasks 收集工作时间的复杂性，使您能够有效地处理自定义日历并简化项目时间表。
## 先决条件
在我们开始这一旅程之前，请确保您具备以下先决条件：
-  Aspose.Tasks for .NET 库：从以下位置下载并安装 Aspose.Tasks for .NET 库：[Aspose.Tasks 发布页面](https://releases.aspose.com/tasks/net/).
- 工作环境：设置合适的开发环境，最好使用.NET兼容的IDE。
## 导入命名空间
在您的项目中，导入必要的命名空间以访问 Aspose.Tasks 功能：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
现在，让我们将教程分解为多个步骤，以确保顺利的学习体验。
## 第 1 步：创建自定义日历
首先创建一个新项目并向其中添加自定义日历：
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## 第 2 步：定义工作日
设置默认工作日为周一至周五：
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## 步骤 3：配置周六工作时间
指定周六的工作时间：
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## 第 4 步：打印周六工作时间
打印周六配置的工作时间：
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## 步骤 5：配置周日工作时间
定义周日的工作时间：
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## 第 6 步：打印周日工作时间
打印周日配置的工作时间：
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## 第 7 步：将自定义日期添加到日历中
在日历中包含配置的星期六和星期日：
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## 第 8 步：遍历工作时间
遍历工作时间并在日历中显示每天的工作时间：
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
既然您已成功完成这些步骤，您就可以利用 Aspose.Tasks for .NET 的强大功能来有效管理工作时间。
## 结论
掌握 Aspose.Tasks 中的工作时间集合使您能够自定义项目日历，确保精确的调度和高效的资源利用。借助从本综合指南中获得的知识，充满信心地投入到您的项目中。
## 经常问的问题
### Aspose.Tasks适合大型项目管理吗？
是的，Aspose.Tasks 旨在处理不同规模的项目，为高效的项目管理提供强大的功能。
### 我可以将 Aspose.Tasks 与其他 .NET 库集成吗？
当然！ Aspose.Tasks 与其他 .NET 库无缝集成，增强了其多功能性和兼容性。
### Aspose.Tasks 多久更新一次？
 Aspose.Tasks 定期更新以纳入新功能、增强功能和兼容性改进。检查[发布页面](https://releases.aspose.com/tasks/net/)了解最新动态。
### Aspose.Tasks 是否有免费试用版？
是的，您可以通过访问免费试用来探索 Aspose.Tasks[这个链接](https://releases.aspose.com/).
### 我在哪里可以寻求 Aspose.Tasks 的支持？
如有任何疑问或帮助，请访问[Aspose.Tasks 支持论坛](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
