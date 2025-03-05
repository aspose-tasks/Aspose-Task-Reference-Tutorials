---
title: 处理 Aspose.Tasks 中的日历异常
linktitle: 处理 Aspose.Tasks 中的日历异常
second_title: Aspose.Tasks .NET API
description: 通过分步教程和示例，了解如何在 Aspose.Tasks for .NET 中管理日历异常。
type: docs
weight: 12
url: /zh/net/calendar-scheduling/calendar-exceptions/
---
## 介绍

在本教程中，我们将探讨如何使用 .NET 框架在 Aspose.Tasks 中管理日历异常。日历例外允许我们在项目日历中定义特殊日期或时期，其中常规工作时间表会发生变化，例如假期或临时关闭。我们将使用 Aspose.Tasks for .NET 逐步介绍处理日历异常的各种方法。

## 先决条件

在我们开始之前，请确保您满足以下先决条件：
- C# 编程语言的基础知识。
- Visual Studio 安装在您的系统上。
- Aspose.Tasks for .NET 库已添加到您的项目中。

## 导入命名空间

首先，让我们为我们的项目导入必要的命名空间：

```csharp
using Aspose.Tasks;
using System;


```

## 步骤 1：删除日历例外

要删除日历例外，请按照下列步骤操作：

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    //显示日历信息
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    //删除第一个异常
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## 步骤2：获取日历异常的工作时间

要检索日历例外的工作时间，请按照下列步骤操作：

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    //显示日历和异常信息
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    //获取工作时间并显示详细信息
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## 步骤 3：定义日历例外

要添加或删除日历例外，请按照下列步骤操作：

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    //创建新的日历例外
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    //设置异常详细信息
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    //检查日期是否异常
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    //将例外添加到日历中
    calendar.Exceptions.Add(exception);

    //删除异常（如果存在）
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    //添加新的例外
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    //打印异常
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## 结论

在本文中，我们介绍了在 Aspose.Tasks for .NET 中处理日历异常的各个方面。通过遵循提供的步骤，您可以有效地管理项目进度中的异常情况，确保准确表示工作时间和特殊事件。

## 常见问题解答

### Q1：我可以在一个日历中添加多个例外吗？

A1：是的，您可以向日历添加多个例外，以适应各种特殊日期或时段。

### Q2：如何检查特定日期是否异常？

 A2：您可以使用`CheckException()`方法来验证特定日期是否属于例外情况。

### 问题 3：是否可以从日历中删除现有的例外情况？

 A3：是的，您可以通过访问`Exceptions`收集日历并使用`Remove()`方法。

### 问题 4：支持哪些类型的日历例外？

A4：Aspose.Tasks支持各种类型的异常，包括每日、每周、每月和每年的异常，为定义异常规则提供了灵活性。

### Q5：我可以自定义特定例外日期的工作时间吗？

A5：是的，您可以使用 Aspose.Tasks 提供的适当方法为各个例外日期定义自定义工作时间。