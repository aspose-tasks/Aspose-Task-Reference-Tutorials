---
title: 在 Aspose.Tasks 中使用日历
linktitle: 在 Aspose.Tasks 中使用日历
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 轻松管理项目日历、计算工期、处理异常情况。
type: docs
weight: 10
url: /zh/net/calendar-scheduling/working-with-calendar/
---
## 介绍

Aspose.Tasks for .NET 提供了强大的日历处理功能，使开发人员能够有效地管理项目进度和资源分配。在本教程中，我们将探索如何利用 Aspose.Tasks 与日历交互，涵盖基本操作，例如检索日历信息、定义工作周、计算工作时间等。

## 先决条件

在我们开始之前，请确保您已设置以下先决条件：

- 对 C# 编程语言有基本了解。
- 安装 Aspose.Tasks for .NET。如果没有安装，请从以下位置下载[这里](https://releases.aspose.com/tasks/net/).
- 熟悉 Visual Studio 或任何其他首选的 .NET 开发环境。

## 导入命名空间

在开始编码之前，请确保导入必要的命名空间：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

现在，让我们以分步指南的形式将每个示例分解为多个步骤：

## 第 1 步：检索日历信息

要从项目中检索日历信息，请执行以下步骤：

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    //检索日历信息
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

解释：
- 加载项目文件。
- 迭代项目中的每个日历。
- 打印每个日历的 UID 和名称。

## 第 2 步：阅读工作周信息

要从日历中读取工作周信息，请按照下列步骤操作：

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

解释：
- 加载项目文件。
- 通过UID获取日历。
- 迭代日历中的每个工作周。
- 打印每个工作周的名称、开始日期和结束日期。
- 遍历每周的工作日和工作时间。

## 第 3 步：读取日历属性

要读取项目日历的属性，请执行以下步骤：

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

解释：
- 加载项目文件。
- 迭代项目中的每个日历。
- 打印 UID、名称以及是否为基准日历。
- 打印每天类型的工作时间。

## 第四步：计算工作时间

要计算任务的工时，请按照下列步骤操作：

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

解释：
- 加载项目文件。
- 获取任务详细信息，例如日历、开始日期和结束日期。
- 通过迭代每一天并检查当天是否是工作日来计算工作时间。
- 以分钟为单位总结总持续时间。

## 步骤 5：定义日历的工作日

要定义日历的工作日，请按照下列步骤操作：

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

解释：
- 创建一个新项目和日历。
- 添加默认工作日（周一至周四）和周五的自定义工作时间。
- 将周六和周日设置为非工作日。

## 步骤 6：将更新的日历数据写入 MPP

要将更新的日历数据写入 MPP 文件，请按照下列步骤操作：

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/。”）；
    }
}
```

解释：
- 加载项目文件并检索标准日历。
- 修改日历数据，例如例外情况和工作时间。
- 使用修改后的日历数据保存更新的项目。

## 第 7 步：计算拆分任务完成日期

要计算拆分任务的完成日期，请执行以下步骤：

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

解释：
- 加载项目文件并检索拆分任务。
- 获取项目日历。
- 根据自定义持续时间计算完成日期。

## 步骤 8：检索日历异常

要检索有关日历例外的信息，请执行以下步骤：

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

解释：
- 加载项目文件。
- 迭代每个日历及其例外情况。
- 打印每个异常的开始和结束日期。

## 第 9 步：获取基础资源日历

要使用资源日历的基准日历，请执行以下步骤：

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

解释：
- 加载项目文件。
- 添加资源及其日历。
- 打印所有资源的基准日历名称。

## 第10步：删除日历

要从项目中删除日历，请按照下列步骤操作：

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

解释：
- 加载项目文件。
- 按名称获取日历。
- 删除日历。

## 第 11 步：通过开始和工作确定完成日期

要根据开始日期和工时计算完成日期，请执行以下步骤：

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

解释：
- 加载项目文件。
- 获取标准日历。
- 定义开始日期和工作持续时间。
- 根据开始日期和工时计算完成日期。

## 第 12 步：开始下一个工作日

要使用日历开始下一个工作日，请按照下列步骤操作：

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

解释：
- 加载项目文件。
- 通过UID获取日历。
- 获取下一个工作日的开始时间。

## 第 13 步：获取前一个工作日结束时间

要使用日历获取前一个工作日的结束时间，请按照下列步骤操作：

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

解释：
- 加载项目文件。
- 通过UID获取日历。
- 获取前一个工作日的结束时间。

## 第 14 步：根据完成时间和持续时间获取开始日期

要按结束日期和持续时间获取开始日期，请按照以下步骤操作：

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

解释：
- 加载项目文件。
- 通过UID获取日历。
- 根据结束日期和持续时间计算开始日期。

## 第 15 步：获取工作时间

要获取特定日期的工作时间，请执行以下步骤：

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

解释：
- 加载项目文件。
- 通过UID获取日历。
- 获取指定日期的工作时间。

## 第 16 步：获取工作时间

要获取特定日期的工作时间，请按照以下步骤操作：

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

解释：
- 加载项目文件。
- 通过UID获取日历。
- 获取指定日期的工作时间。

## 结论

在 Aspose.Tasks for .NET 中使用日历对于有效管理项目进度至关重要。通过提供的示例和分步指南，您可以轻松操作日历数据、计算任务持续时间并有效处理异常。通过将这些功能集成到您的应用程序中，您可以简化项目管理流程并确保准确的调度。

## 常见问题解答

### Q1：我需要许可证才能使用 Aspose.Tasks for .NET 吗？

 A1：是的，您需要有效的许可证才能在应用程序中使用 Aspose.Tasks for .NET。您可以购买完整许可证或从以下位置获取 30 天的临时许可证：[这里](https://purchase.aspose.com/temporary-license/).

### 问题 2：我可以通过编程方式修改日历例外吗？

A2：是的，您可以使用 Aspose.Tasks for .NET API 以编程方式添加、更新或删除日历例外。

### 问题 3：如何计算具有自定义持续时间的任务完成日期？

 A3：Aspose.Tasks for .NET 提供了类似的方法`GetTaskFinishDateFromDuration()`根据自定义持续时间计算任务完成日期。

### Q4：是否可以创建自定义日历，例如夜班日历？

A4：是的，您可以使用 Aspose.Tasks for .NET API 创建自定义日历，例如夜班日历。

### Q5：我可以从项目文件中检索有关日历例外的信息吗？

A5：是的，您可以使用 Aspose.Tasks for .NET 轻松地从项目文件中检索有关日历异常的信息。