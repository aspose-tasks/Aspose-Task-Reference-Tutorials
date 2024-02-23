---
title: Работа с календарем в Aspose.Задачи
linktitle: Работа с календарем в Aspose.Задачи
second_title: Aspose.Tasks .NET API
description: Управляйте календарями проектов, рассчитывайте продолжительность, легко обрабатывайте исключения с помощью Aspose.Tasks для .NET.
type: docs
weight: 10
url: /ru/net/calendar-scheduling/working-with-calendar/
---
## Введение

Aspose.Tasks для .NET предоставляет мощные функции для работы с календарями, позволяющие разработчикам эффективно управлять расписаниями проектов и распределением ресурсов. В этом уроке мы рассмотрим, как использовать Aspose.Tasks для взаимодействия с календарями, охватывая такие важные операции, как получение информации о календаре, определение рабочих недель, расчет рабочих часов и многое другое.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас настроены следующие предварительные условия:

- Базовое понимание языка программирования C#.
-  Установка Aspose.Tasks для .NET. Если он не установлен, загрузите его с[здесь](https://releases.aspose.com/tasks/net/).
- Знакомство с Visual Studio или любой другой предпочитаемой средой разработки .NET.

## Импортировать пространства имен

Прежде чем приступить к кодированию, обязательно импортируйте необходимые пространства имен:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Теперь давайте разобьем каждый пример на несколько шагов в формате пошагового руководства:

## Шаг 1. Получите информацию о календаре

Чтобы получить информацию календаря из проекта, выполните следующие действия:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Получить информацию о календарях
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

Объяснение:
- Загрузите файл проекта.
- Переберите каждый календарь в проекте.
- Распечатайте UID и название каждого календаря.

## Шаг 2. Прочтите информацию о рабочих неделях

Чтобы прочитать информацию о рабочих неделях из календаря, выполните следующие действия:

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

Объяснение:
- Загрузите файл проекта.
- Получите календарь по UID.
- Переберите каждую рабочую неделю в календаре.
- Напечатайте имя, дату начала и окончания каждой рабочей недели.
- Просматривайте рабочие дни и рабочее время в течение каждой недели.

## Шаг 3. Прочтите свойства календаря

Чтобы прочитать свойства календарей проекта, выполните следующие действия:

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

Объяснение:
- Загрузите файл проекта.
- Переберите каждый календарь в проекте.
- Распечатайте UID, имя и укажите, является ли это базовым календарем.
- Распечатайте рабочее время для каждого типа дня.

## Шаг 4: Рассчитайте рабочее время

Чтобы рассчитать рабочее время для задачи, выполните следующие действия:

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

Объяснение:
- Загрузите файл проекта.
- Получите подробную информацию о задаче, например календарь, дату начала и дату окончания.
- Подсчитайте рабочее время, перебирая каждый день и проверяя, рабочий ли это день.
- Подсчитайте общую продолжительность в минутах.

## Шаг 5. Определите дни недели для календаря

Чтобы определить дни недели для календаря, выполните следующие действия:

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

Объяснение:
- Создайте новый проект и календарь.
- Добавьте рабочие дни по умолчанию (с понедельника по четверг) и пользовательское рабочее время для пятницы.
- Установите субботу и воскресенье как нерабочие дни.

## Шаг 6. Запишите обновленные данные календаря в MPP

Чтобы записать обновленные данные календаря в файл MPP, выполните следующие действия:

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
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://Purchase.aspose.com/temporary-license/).");
    }
}
```

Объяснение:
- Загрузите файл проекта и получите стандартный календарь.
- Измените данные календаря, такие как исключения и рабочее время.
- Сохраните обновленный проект с измененными данными календаря.

## Шаг 7. Рассчитайте дату завершения разделенной задачи

Чтобы рассчитать дату окончания разделенной задачи, выполните следующие действия:

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

Объяснение:
- Загрузите файл проекта и получите разделенную задачу.
- Получите календарь проекта.
- Рассчитайте дату окончания на основе заданной продолжительности.

## Шаг 8. Получение исключений календаря

Чтобы получить информацию об исключениях календаря, выполните следующие действия:

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

Объяснение:
- Загрузите файл проекта.
- Переберите каждый календарь и его исключения.
- Выведите даты начала и окончания каждого исключения.

## Шаг 9: Получите базовый календарь ресурсов

Чтобы работать с базовым календарем календаря ресурса, выполните следующие действия:

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

Объяснение:
- Загрузите файл проекта.
- Добавьте ресурс и его календарь.
- Распечатайте название базового календаря для всех ресурсов.

## Шаг 10: Удалить календарь

Чтобы удалить календарь из проекта, выполните следующие действия:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Объяснение:
- Загрузите файл проекта.
- Получить календарь по имени.
- Удалить календарь.

## Шаг 11: Узнайте дату окончания по началу и приступайте к работе

Чтобы рассчитать дату окончания по дате начала и работе, выполните следующие действия:

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

Объяснение:
- Загрузите файл проекта.
- Возьмите стандартный календарь.
- Определите дату начала и продолжительность работы.
- Рассчитайте дату окончания на основе даты начала и работы.

## Шаг 12. Начните следующий рабочий день

Чтобы начать следующий рабочий день с помощью календаря, выполните следующие действия:

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

Объяснение:
- Загрузите файл проекта.
- Получите календарь по UID.
- Получите время начала следующего рабочего дня.

## Шаг 13: Получите конец предыдущего рабочего дня

Чтобы получить конец предыдущего рабочего дня с помощью календаря, выполните следующие действия:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Объяснение:
- Загрузите файл проекта.
- Получите календарь по UID.
- Получите время окончания предыдущего рабочего дня.

## Шаг 14: Получите дату начала от окончания и продолжительности

Чтобы получить дату начала по дате окончания и продолжительности, выполните следующие действия:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Объяснение:
- Загрузите файл проекта.
- Получите календарь по UID.
- Рассчитайте дату начала на основе даты окончания и продолжительности.

## Шаг 15: Получите рабочее время

Чтобы получить рабочее время на определенную дату, выполните следующие действия:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Объяснение:
- Загрузите файл проекта.
- Получите календарь по UID.
- Получите рабочее время на указанную дату.

## Шаг 16: Узнайте рабочее время

Чтобы получить рабочее время на конкретную дату, выполните следующие действия:

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

Объяснение:
- Загрузите файл проекта.
- Получите календарь по UID.
- Получите рабочее время на указанную дату.

## Заключение

Работа с календарями в Aspose.Tasks для .NET имеет решающее значение для эффективного управления расписаниями проектов. С помощью предоставленных примеров и пошаговых руководств вы можете легко манипулировать данными календаря, рассчитывать длительность задач и эффективно обрабатывать исключения. Интегрируя эти функции в свои приложения, вы можете оптимизировать процессы управления проектами и обеспечить точное планирование.

## Часто задаваемые вопросы

### Вопрос 1: Нужна ли мне лицензия для использования Aspose.Tasks для .NET?

 О1: Да, вам нужна действующая лицензия для использования Aspose.Tasks для .NET в ваших приложениях. Вы можете приобрести полную лицензию или получить 30-дневную временную лицензию на сайте[здесь](https://purchase.aspose.com/temporary-license/).

### Вопрос 2. Могу ли я программно изменить исключения календаря?

О2: Да, вы можете программно добавлять, обновлять или удалять исключения календаря с помощью Aspose.Tasks для API .NET.

### Вопрос 3. Как рассчитать даты завершения задач с настраиваемой длительностью?

 A3: Aspose.Tasks для .NET предоставляет такие методы, как`GetTaskFinishDateFromDuration()` для расчета дат окончания задач на основе настраиваемой длительности.

### Вопрос 4. Можно ли создавать собственные календари, например календари ночных смен?

О4: Да, вы можете создавать собственные календари, например календари ночных смен, используя Aspose.Tasks для API .NET.

### Вопрос 5. Могу ли я получить информацию об исключениях календаря из файлов проекта?

О5: Да, вы можете легко получить информацию об исключениях календаря из файлов проекта, используя Aspose.Tasks для .NET.