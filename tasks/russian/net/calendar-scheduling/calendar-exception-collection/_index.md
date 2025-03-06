---
title: Сбор исключений календаря в Aspose.Tasks
linktitle: Сбор исключений календаря в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно обрабатывать исключения календаря в ваших проектах .NET с помощью Aspose.Tasks, обеспечивая точное планирование и управление ресурсами.
type: docs
weight: 13
url: /ru/net/calendar-scheduling/calendar-exception-collection/
---
## Введение

В управлении проектами точное планирование жизненно важно для успеха. Однако реальные сценарии часто требуют отклонений от стандартных графиков из-за праздников, особых событий или других факторов. Aspose.Tasks для .NET предоставляет надежное решение для управления такими исключениями с помощью функции сбора исключений календаря. Это руководство шаг за шагом проведет вас через процесс использования этой функции.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

1.  Aspose.Tasks для .NET: убедитесь, что у вас установлена библиотека. Вы можете скачать его[здесь](https://releases.aspose.com/tasks/net/).
2. Базовые знания C#: Знакомство с языком программирования C# будет полезно для понимания примеров.
3. Среда разработки: настройте предпочитаемую среду разработки, например Visual Studio или JetBrains Rider.

## Импортировать пространства имен

Прежде чем вы начнете работать с Aspose.Tasks для .NET, вам необходимо импортировать необходимые пространства имен в ваш проект. Этот шаг позволяет вам получить доступ к классам и методам, необходимым для управления исключениями календаря.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Теперь давайте разобьем приведенный пример на несколько шагов:

## Шаг 1. Загрузите проект и получите календарь

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

На этом этапе мы загружаем файл проекта и получаем нужный календарь по его UID.

## Шаг 2. Очистите существующие исключения и установите стандартный календарь

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

На этом шаге из календаря удаляются все существующие исключения и устанавливается стандартная конфигурация.

## Шаг 3. Определите и добавьте исключение рабочего времени

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

На этом этапе определяется исключение рабочего времени с конкретными датами начала и окончания, а также рабочее время в пределах этих дат, и добавляется в календарь.

## Шаг 4. Определите и добавьте исключения для нерабочего времени

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// При необходимости добавьте дополнительные исключения

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

На этом шаге определяются исключения нерабочего времени, например праздники, и добавляются в календарь.

## Шаг 5. Отображение исключений календаря

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

На этом шаге отображаются добавленные исключения календаря вместе с их подробностями.

## Шаг 6. Удалите все исключения

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Наконец, на этом шаге из календаря удаляются все исключения.

## Заключение

Управление исключениями из календаря имеет решающее значение для точного планирования проекта. Aspose.Tasks для .NET упрощает эту задачу, предоставляя полный набор функций, включая сбор исключений календаря. Следуя шагам, описанным в этом руководстве, вы сможете эффективно обрабатывать различные сценарии планирования в своих проектах.

## Часто задаваемые вопросы

### Вопрос 1. Могу ли я добавить несколько исключений в один календарь?

 О1: Да, вы можете добавить в календарь несколько исключений, используя`AddRange` метод.

### Вопрос 2. Как обрабатывать повторяющиеся исключения, например еженедельные праздники?

A2. Вы можете программно рассчитывать повторяющиеся исключения и добавлять их в календарь, используя собственную логику.

### Вопрос 3. Можно ли импортировать исключения календаря из внешних источников?

О3: Да, вы можете читать исключения календаря из внешних источников, таких как базы данных или файлы CSV, и интегрировать их в свой проект.

### Вопрос 4. Что произойдет, если в календаре есть перекрывающиеся исключения?

A4: Aspose.Tasks for .NET позволяет вам обрабатывать перекрывающиеся исключения, определяя приоритеты или разрешая конфликты на основе требований вашего проекта.

### В5: Могу ли я настроить рабочее время для каждого дня в рамках исключения?

О5: Да, вы можете указать индивидуальное рабочее время для отдельных дней в рамках исключения, чтобы удовлетворить конкретные потребности планирования.