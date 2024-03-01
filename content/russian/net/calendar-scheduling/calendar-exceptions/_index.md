---
title: Обработка исключений календаря в Aspose.Tasks
linktitle: Обработка исключений календаря в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как управлять исключениями календаря в Aspose.Tasks для .NET, с помощью пошаговых руководств и примеров.
type: docs
weight: 12
url: /ru/net/calendar-scheduling/calendar-exceptions/
---
## Введение

В этом руководстве мы рассмотрим, как управлять исключениями календаря в Aspose.Tasks с использованием платформы .NET. Календарные исключения позволяют нам определять особые даты или периоды в календаре проекта, когда обычный рабочий график изменяется, например праздники или временное закрытие. Мы шаг за шагом рассмотрим различные методы обработки исключений календаря, используя Aspose.Tasks для .NET.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- Базовые знания языка программирования C#.
- Visual Studio установлена в вашей системе.
- В ваш проект добавлена библиотека Aspose.Tasks for .NET.

## Импортировать пространства имен

Во-первых, давайте импортируем необходимые пространства имен для нашего проекта:

```csharp
using Aspose.Tasks;
using System;


```

## Шаг 1. Удаление исключения из календаря

Чтобы удалить исключение календаря, выполните следующие действия:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Отображение информации календаря
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Удалить первое исключение
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Шаг 2. Получение рабочего времени календарного исключения

Чтобы получить рабочее время исключения календаря, выполните следующие действия:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Отображение календаря и информации об исключениях
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Получить рабочее время и отобразить детали
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Шаг 3. Определение исключений календаря

Чтобы добавить или удалить исключения календаря, выполните следующие действия:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Создать новое исключение календаря
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Установить сведения об исключении
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Проверьте, является ли дата исключением
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Добавьте исключение в календарь
    calendar.Exceptions.Add(exception);

    // Удалить исключение, если оно существует
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Добавить новое исключение
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Печать исключений
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Заключение

В этой статье мы рассмотрели различные аспекты обработки исключений календаря в Aspose.Tasks для .NET. Следуя предоставленным шагам, вы сможете эффективно управлять исключениями в расписаниях проектов, обеспечивая точное представление рабочего времени и особых событий.

## Часто задаваемые вопросы

### Вопрос 1. Могу ли я добавить несколько исключений в один календарь?

О1: Да, вы можете добавить в календарь несколько исключений, чтобы учесть различные особые даты или периоды.

### Вопрос 2. Как я могу проверить, является ли определенная дата исключением?

 A2: Вы можете использовать`CheckException()` метод, позволяющий проверить, попадает ли конкретная дата в исключение.

### Вопрос 3. Можно ли удалить существующее исключение из календаря?

 О3: Да, вы можете удалить исключения, открыв`Exceptions` сбор календаря и использование`Remove()` метод.

### Вопрос 4. Какие типы исключений календаря поддерживаются?

A4: Aspose.Tasks поддерживает различные типы исключений, включая ежедневные, еженедельные, ежемесячные и ежегодные исключения, обеспечивая гибкость в определении правил исключений.

### Вопрос 5. Могу ли я настроить рабочее время для определенных дат исключений?

О5: Да, вы можете определить собственное рабочее время для отдельных дат исключений, используя соответствующие методы, предоставляемые Aspose.Tasks.