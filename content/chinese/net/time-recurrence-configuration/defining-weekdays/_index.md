---
title: 在 Aspose.Tasks for .NET 中掌握工作日
linktitle: 在 Aspose.Tasks 中定义工作日
second_title: Aspose.Tasks .NET API
description: 探索在 Aspose.Tasks .NET 中定义工作日的强大功能。按照我们的详细教程来有效管理项目日历、自定义工作时间等。
type: docs
weight: 10
url: /zh/net/time-recurrence-configuration/defining-weekdays/
---
## 介绍
如果您正在使用 Aspose.Tasks for .NET 进入项目管理世界，那么理解和操作工作日是一个至关重要的方面。在项目日历中有效管理和自定义工作日可以显着影响项目时间表。在本教程中，我们将指导您完成使用 Aspose.Tasks 定义工作日的过程，并提供分步说明和示例，以便更加清晰。
## 先决条件
在我们开始这一旅程之前，请确保您满足以下先决条件：
- 对 C# 编程语言有基本了解。
- 安装了 .NET 库的 Aspose.Tasks。如果没有，请从以下位置下载[这里](https://releases.aspose.com/tasks/net/).
## 导入命名空间
首先将必要的命名空间导入到您的项目中：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. 检查平日平等
```csharp
//您的文档目录
String DataDir = "Your Document Directory";
//加载项目文件
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
//工作日访问
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
//根据各种属性检查相等性
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
//为DayWorking、FromDate、ToDate 和WorkingTimes 添加类似的输出语句
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. 克隆工作日
```csharp
//加载项目文件
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
//创建工作日的深层副本
var weekDay2 = weekDay1.Clone();
//两个工作日的输出属性
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
//为DayWorking、FromDate、ToDate 和WorkingTimes 添加类似的输出语句
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. 获取工作日的哈希码
```csharp
//加载项目文件
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
//两个工作日的输出属性
//为DayWorking、FromDate、ToDate 和WorkingTimes 添加类似的输出语句
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. 创建一个包含已定义工作日的新日历
```csharp
//创建一个新项目
var project = new Project();
//定义日历
var calendar = project.Calendars.Add("Calendar1");
//添加工作日和例外日
//为 FromDate 和 ToDate 添加类似的输出语句
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
//设置周五的工作时间
//为DayWorking、FromDate、ToDate 和WorkingTimes 添加类似的输出语句
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5.设置一天的默认工作时间
```csharp
//创建一个新项目
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
//添加周一至周五的默认工作时间
//为DayWorking、FromDate、ToDate 和WorkingTimes 添加类似的输出语句
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
//周二、周三、周四和周五重复
//设置周六、周日为非工作日
//为DayWorking、FromDate、ToDate 和WorkingTimes 添加类似的输出语句
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## 结论
在本教程中，我们介绍了在 Aspose.Tasks for .NET 中定义工作日的基本方面。掌控工作日是有效项目管理的一项关键技能。尝试提供的示例，根据您的项目需求进行定制，并释放 Aspose.Tasks 的全部潜力。
## 常见问题解答
### 我可以定义每天的自定义工作时间吗？
是的，您可以使用提供的示例为特定工作日设置自定义工作时间。
### 是否可以在日历中添加多个例外日？
绝对地。修改第四个示例中的代码以包含其他例外日期。
### 如何从日历中删除特定工作日？
利用 Aspose.Tasks 库提供的适当方法根据需要删除工作日。
### 对工作日所做的更改是否会保留在项目文件中？
是的，对工作日的任何修改都会在保存时反映在项目文件中。
### 我可以将 Aspose.Tasks 与其他编程语言一起使用吗？
Aspose.Tasks 支持各种编程语言，但此处的示例专门针对 .NET。