---
title: Working with Calendar in Aspose.Tasks
linktitle: Working with Calendar in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Manage project calendars, calculate durations, handle exceptions with ease using Aspose.Tasks for .NET.
type: docs
weight: 10
url: /net/calendar-scheduling/working-with-calendar/
---
## Introduction

Aspose.Tasks for .NET provides powerful features for working with calendars, enabling developers to efficiently manage project schedules and resource allocations. In this tutorial, we will explore how to utilize Aspose.Tasks to interact with calendars, covering essential operations such as retrieving calendar information, defining workweeks, calculating work hours, and more.

## Prerequisites

Before we begin, ensure you have the following prerequisites set up:

- Basic understanding of C# programming language.
- Installation of Aspose.Tasks for .NET. If not installed, download it from [here](https://releases.aspose.com/tasks/net/).
- Familiarity with Visual Studio or any other preferred .NET development environment.

## Import Namespaces

Before you start coding, make sure to import the necessary namespaces:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Now, let's break down each example into multiple steps in a step-by-step guide format:

## Step 1: Retrieve Calendar Information

To retrieve calendar information from a project, follow these steps:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Retrieve Calendars Information
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

Explanation:
- Load the project file.
- Iterate through each calendar in the project.
- Print UID and name of each calendar.

## Step 2: Read Work Weeks Information

To read work weeks information from a calendar, follow these steps:

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

Explanation:
- Load the project file.
- Get the calendar by UID.
- Iterate through each work week in the calendar.
- Print name, start date, and end date of each work week.
- Traverse through working days and working times within each week.

## Step 3: Read Calendar Properties

To read properties of project calendars, follow these steps:

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

Explanation:
- Load the project file.
- Iterate through each calendar in the project.
- Print UID, name, and whether it's a base calendar.
- Print working hours for each day type.

## Step 4: Calculate Work Hours

To calculate work hours for a task, follow these steps:

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

Explanation:
- Load the project file.
- Get task details like calendar, start date, and end date.
- Calculate work hours by iterating through each day and checking if it's a working day.
- Sum up the total duration in minutes.

## Step 5: Define Weekdays for Calendar

To define weekdays for a calendar, follow these steps:

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

Explanation:
- Create a new project and calendar.
- Add default working days (Monday to Thursday) and custom working times for Friday.
- Set Saturday and Sunday as non-working days.

## Step 6: Write Updated Calendar Data to MPP

To write updated calendar data to an MPP file, follow these steps:

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
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://purchase.aspose.com/temporary-license/).");
    }
}
```

Explanation:
- Load the project file and retrieve the standard calendar.
- Modify calendar data such as exceptions and working times.
- Save the updated project with the modified calendar data.

## Step 7: Calculate Split Task Finish Date

To calculate the finish date of a split task, follow these steps:

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

Explanation:
- Load the project file and retrieve the split task.
- Get the project calendar.
- Calculate the finish date based on a custom duration.

## Step 8: Retrieve Calendar Exceptions

To retrieve information about calendar exceptions, follow these steps:

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

Explanation:
- Load the project file.
- Iterate through each calendar and its exceptions.
- Print start and end dates of each exception.

## Step 9: Get Base Resource Calendar

To work with the base calendar of a resource's calendar, follow these steps:

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

Explanation:
- Load the project file.
- Add a resource and its calendar.
- Print the base calendar name for all resources.

## Step 10: Delete Calendar

To delete a calendar from a project, follow these steps:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Explanation:
- Load the project file.
- Get the calendar by name.
- Delete the calendar.

## Step 11: Get Finish Date By Start and Work

To calculate a finish date by start date and work, follow these steps:

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

Explanation:
- Load the project file.
- Get the standard calendar.
- Define a start date and work duration.
- Calculate the finish date based on the start date and work.

## Step 12: Get Next Working Day Start

To get the next working day start by using a calendar, follow these steps:

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

Explanation:
- Load the project file.
- Get the calendar by UID.
- Get the next working day start time.

## Step 13: Get Previous Working Day End

To get the previous working day end by using a calendar, follow these steps:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Explanation:
- Load the project file.
- Get the calendar by UID.
- Get the previous working day end time.

## Step 14: Get Start Date From Finish And Duration

To get a start date by finish date and duration, follow these steps:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Explanation:
- Load the project file.
- Get the calendar by UID.
- Calculate the start date from the finish date and duration.

## Step 15: Get Working Hours

To get working hours for a specific date, follow these steps:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Explanation:
- Load the project file.
- Get the calendar by UID.
- Get the working hours for the specified date.

## Step 16: Get Working Times

To get working times for a specific date, follow these steps:

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

Explanation:
- Load the project file.
- Get the calendar by UID.
- Get the working times for the specified date.

## Conclusion

Working with calendars in Aspose.Tasks for .NET is crucial for managing project schedules effectively. With the provided examples and step-by-step guides, you can easily manipulate calendar data, calculate task durations, and handle exceptions efficiently. By integrating these functionalities into your applications, you can streamline project management processes and ensure accurate scheduling.

## FAQ's

### Q1: Do I need a license to use Aspose.Tasks for .NET?

A1: Yes, you need a valid license to utilize Aspose.Tasks for .NET in your applications. You can purchase a full license or obtain a 30-day temporary license from [here](https://purchase.aspose.com/temporary-license/).

### Q2: Can I modify calendar exceptions programmatically?

A2: Yes, you can programmatically add, update, or delete calendar exceptions using Aspose.Tasks for .NET APIs.

### Q3: How can I calculate task finish dates with custom durations?

A3: Aspose.Tasks for .NET provides methods like `GetTaskFinishDateFromDuration()` to calculate task finish dates based on custom durations.

### Q4: Is it possible to create custom calendars, such as night shift calendars?

A4: Yes, you can create custom calendars like night shift calendars using Aspose.Tasks for .NET APIs.

### Q5: Can I retrieve information about calendar exceptions from project files?

A5: Yes, you can easily retrieve information about calendar exceptions from project files using Aspose.Tasks for .NET.
