---
title: 在 Aspose.Tasks 中管理日期类型集合
linktitle: 在 Aspose.Tasks 中管理日期类型集合
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中有效管理日期类型集合。轻松创建、修改和操作日历例外。
weight: 28
url: /zh/net/calendar-scheduling/day-type-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中管理日期类型集合

## 介绍

 Aspose.Tasks for .NET 提供了管理日期类型集合的强大功能，这对于在项目管理应用程序中定义每周日历例外至关重要。在本教程中，我们将探讨如何利用`DayTypeCollection`高效上课。 

## 先决条件

在继续学习本教程之前，请确保您满足以下先决条件：

1. Visual Studio：确保您的系统上安装了 Visual Studio。
2.  Aspose.Tasks for .NET：下载并安装 Aspose.Tasks for .NET 库[这里](https://releases.aspose.com/tasks/net/).
3. C# 基础知识：熟悉 C# 编程语言和 .NET 框架概念。

## 导入命名空间

首先，您需要将必要的命名空间导入到您的 C# 项目中：

```csharp
using Aspose.Tasks;
using System;


```

现在，让我们将提供的示例分解为多个步骤：

## 第 1 步：加载项目并访问日历

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

此步骤初始化一个新的项目实例并通过其 UID 检索日历。

## 第 2 步：遍历日历异常

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

在这里，我们遍历每个日历异常并打印其名称和关联的日期类型。

## 步骤 3：修改日历例外

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

此步骤演示如何通过添加、删除或更新日期类型来修改日历例外。

## 第 4 步：创建和操作新的日历例外

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

在最后一步中，我们创建新的日历例外并通过添加和复制日期类型来操作它们。

## 结论

总之，在 Aspose.Tasks for .NET 中管理日期类型集合对于在项目管理应用程序中定义和修改每周日历例外至关重要。通过遵循本教程中提供的分步指南，您可以有效地利用`DayTypeCollection`类来处理各种日历操作。

## 常见问题解答

### Q1：Aspose.Tasks for .NET 可用于以编程方式创建甘特图吗？

A1：是的，Aspose.Tasks for .NET 提供了 API 来在 .NET 应用程序中创建和操作甘特图。

### Q2：Aspose.Tasks for .NET 是否与 .NET Core 和 .NET Framework 兼容？

A2：是的，Aspose.Tasks for .NET 同时支持 .NET Core 和 .NET Framework。

### Q3：如何获得 Aspose.Tasks for .NET 支持？

 A3：您可以通过访问获得支持[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)您可以在其中提出问题并与其他用户互动。

### Q4：Aspose.Tasks for .NET 提供免费试用吗？

 A4：是的，您可以从以下位置获得 Aspose.Tasks for .NET 的免费试用版：[这里](https://releases.aspose.com/).

### Q5：我可以购买 Aspose.Tasks for .NET 的临时许可证吗？

 A5：是的，临时许可证可以从[阿斯普斯网站](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
