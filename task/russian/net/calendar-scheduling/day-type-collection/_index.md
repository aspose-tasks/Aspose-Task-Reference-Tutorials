---
title: Управление коллекцией типов дней в Aspose.Tasks
linktitle: Управление коллекцией типов дней в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно управлять коллекциями типов дней в Aspose.Tasks для .NET. С легкостью создавайте, изменяйте и управляйте исключениями календаря.
type: docs
weight: 28
url: /ru/net/calendar-scheduling/day-type-collection/
---
## Введение

 Aspose.Tasks для .NET предоставляет надежную функциональность для управления коллекциями типов дней, что имеет решающее значение для определения исключений еженедельного календаря в приложениях управления проектами. В этом уроке мы рассмотрим, как использовать`DayTypeCollection` класс эффективно. 

## Предварительные условия

Прежде чем мы приступим к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

1. Visual Studio: убедитесь, что в вашей системе установлена Visual Studio.
2.  Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/tasks/net/).
3. Базовые знания C#: Знакомство с языком программирования C# и концепциями платформы .NET.

## Импортировать пространства имен

Для начала вам необходимо импортировать необходимые пространства имен в ваш проект C#:

```csharp
using Aspose.Tasks;
using System;


```

Теперь давайте разобьем приведенный пример на несколько этапов:

## Шаг 1. Загрузите проект и получите доступ к календарю.

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

На этом шаге инициализируется новый экземпляр проекта и извлекается календарь по его UID.

## Шаг 2. Перебор исключений календаря

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

Здесь мы перебираем каждое исключение календаря и печатаем его имя и связанные типы дней.

## Шаг 3. Измените исключения календаря

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

На этом шаге показано, как изменить исключения календаря путем добавления, удаления или обновления типов дней.

## Шаг 4. Создание новых исключений календаря и управление ими

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

На этом последнем этапе мы создаем новые исключения календаря и манипулируем ими, добавляя и копируя типы дней.

## Заключение

 В заключение, управление коллекциями типов дней в Aspose.Tasks для .NET необходимо для определения и изменения исключений еженедельного календаря в приложениях управления проектами. Следуя пошаговому руководству, представленному в этом руководстве, вы сможете эффективно использовать`DayTypeCollection` класс для обработки различных календарных операций.

## Часто задаваемые вопросы

### Вопрос 1. Можно ли использовать Aspose.Tasks для .NET для программного создания диаграмм Ганта?

О1: Да, Aspose.Tasks для .NET предоставляет API для создания диаграмм Ганта и управления ими в приложениях .NET.

### Вопрос 2. Совместим ли Aspose.Tasks для .NET с .NET Core и .NET Framework?

О2: Да, Aspose.Tasks для .NET поддерживает как .NET Core, так и .NET Framework.

### Вопрос 3: Как я могу получить поддержку Aspose.Tasks для .NET?

 A3: Вы можете получить поддержку, посетив[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) где вы можете задавать вопросы и общаться с другими пользователями.

### Вопрос 4. Предлагает ли Aspose.Tasks для .NET бесплатную пробную версию?

 О4: Да, вы можете получить бесплатную пробную версию Aspose.Tasks для .NET на сайте[здесь](https://releases.aspose.com/).

### Вопрос 5: Могу ли я приобрести временную лицензию на Aspose.Tasks для .NET?

 О5: Да, временные лицензии можно приобрести на сайте[Веб-сайт Aspose](https://purchase.aspose.com/temporary-license/).