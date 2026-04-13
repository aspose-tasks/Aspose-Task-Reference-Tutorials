---
date: 2026-04-13
description: 了解如何在 Aspose.Tasks for .NET 中删除日历例外，并在管理 ASP.NET 日历调度时检查例外日期。
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: 使用 Aspose.Tasks 删除日历例外
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks 删除日历例外
url: /zh/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 删除日历异常（使用 Aspose.Tasks）

## 介绍

在本教程中，您将学习如何 **删除日历异常** 并使用 .NET 框架在 Aspose.Tasks 中管理其他日历异常。日历异常允许您模拟假期、临时关闭或任何正常工作时间发生变化的特殊时期。了解如何添加、查询和移除这些异常对于准确的项目调度至关重要，尤其是在处理 **ASP.NET 日历调度** 场景时。

## 快速答案
- **删除异常的主要方法是什么？** 使用 `CalendarException` 对象的 `Delete()` 方法。  
- **哪个类用于检查日期是否在异常范围内？** `CalendarException.CheckException()` —— 用于 **检查异常日期**。  
- **运行代码是否需要许可证？** 是的，生产环境需要有效的 Aspose.Tasks 许可证。  
- **我可以在单个日历中添加多个异常吗？** 当然可以；`Exceptions` 集合支持多个条目。  
- **支持的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什么是日历异常？

**日历异常** 表示与常规工作日历的偏离——可以将其视为一条规则，说明“在这些日期，工作时间不同或根本没有”。在 Aspose.Tasks 中，每个异常可以拥有自己的工作时间、重复模式以及指示该天是否为工作日的标志。

## 为什么在 ASP.NET 日历调度中管理日历异常？

- **准确的时间线：** 项目会自动遵守假期和特殊关闭，防止出现不切实际的截止日期。  
- **灵活性：** 您可以定义每日、每周、每月或每年的模式，以匹配真实的业务日历。  
- **自动化：** 通过编程方式检查异常日期，可在 ASP.NET 应用程序中构建动态调度逻辑。

## 前提条件

- 对 C# 编程的基本了解。  
- Visual Studio（任意近期版本）。  
- 已在项目中添加 Aspose.Tasks for .NET 库（通过 NuGet 或手动引用）。

## 导入命名空间

首先，导入您需要的命名空间：

```csharp
using Aspose.Tasks;
using System;
```

## 步骤 1：删除日历异常

删除不需要的异常非常简单。以下代码加载项目，选择第一个日历，显示基本信息，删除第一个异常，然后显示更新后的计数。

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **技巧提示：** 在调用 `Delete()` 之前，请始终确认异常索引存在，以避免 `IndexOutOfRangeException`。

## 步骤 2：获取日历异常的工作时间

如果需要检查异常定义的工作时间，请使用 `GetWorkingTime()`。此示例还演示了如何使用 `CheckException` **检查异常日期**。

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## 步骤 3：定义日历异常

下面是完整的演练，展示了如何 **添加**、**检查** 和 **移除** 日历异常。请注意使用 `CheckException` 来 **检查特定时刻的异常日期**。

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## 常见问题与技巧

| 问题 | 原因 | 解决方案 |
|-------|--------|----------|
| **`IndexOutOfRangeException` 删除时出现** | 尝试删除不存在的异常。 | 在调用 `Delete()` 之前，确认 `calendar.Exceptions.Count` 大于索引。 |
| **工作时间不正确** | `DayWorking` 或 `WorkingTimes` 未正确设置。 | 使用 `exception.WorkingTimes.Add(new WorkingTime(...))` 定义明确的时间段。 |
| **异常未被识别** | `CheckException` 返回 `false`，因为日期超出定义的范围。 | 再次检查 `FromDate`/`ToDate` 以及 `Type`（每日、每周等）。 |

## 常见问题

**问：我可以在单个日历中添加多个异常吗？**  
答：是的，您可以根据需要添加任意数量的异常，以表示假期、维护窗口或任何特殊调度规则。

**问：如何对特定日期**check exception date**？**  
答：在 `CalendarException` 实例上使用 `CheckException(DateTime date)` 方法。如果提供的日期在异常范围内，则返回 `true`。

**问：是否可以从日历中移除已有的异常？**  
答：当然可以。访问 `Exceptions` 集合并调用 `Remove()`，或在特定的 `CalendarException` 对象上调用 `Delete()`。

**问：支持哪些类型的日历异常？**  
答：Aspose.Tasks 支持每日、每周、每月和每年异常类型，提供灵活性以建模几乎任何重复模式。

**问：我可以为特定异常日期自定义工作时间吗？**  
答：可以。在创建异常后，使用 `WorkingTime` 对象填充其 `WorkingTimes` 集合，以定义该日的开始和结束时间。

## 结论

我们已经完整演示了 **删除日历异常** 操作的整个生命周期，从检查现有异常到添加新异常以及检查日期。掌握这些技术可确保您的项目计划遵循真实世界的日历，使您的 ASP.NET 日历调度实现更加稳健可靠。

---

**最后更新：** 2026-04-13  
**测试环境：** Aspose.Tasks for .NET（最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}