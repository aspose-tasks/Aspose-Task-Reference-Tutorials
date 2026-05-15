---
date: 2026-04-13
description: Узнайте, как удалить исключение календаря в Aspose.Tasks для .NET и проверить
  дату исключения при управлении расписанием календаря ASP.NET.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Удалить исключение календаря с помощью Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Удаление исключения календаря с помощью Aspose.Tasks
url: /ru/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Удаление исключения календаря с Aspose.Tasks

## Введение

В этом руководстве вы узнаете, как **удалять исключение календаря** и управлять другими исключениями календаря в Aspose.Tasks, используя .NET‑framework. Исключения календаря позволяют моделировать праздники, временные закрытия или любые специальные периоды, когда обычный график работы меняется. Понимание того, как добавлять, запрашивать и удалять такие исключения, необходимо для точного планирования проектов, особенно при работе со сценариями **ASP.NET calendar scheduling**.

## Быстрые ответы
- **Каков основной метод для удаления исключения?** Используйте метод `Delete()` у объекта `CalendarException`.  
- **Какой класс проверяет дату на наличие исключения?** `CalendarException.CheckException()` — полезно для **проверки даты исключения**.  
- **Нужна ли лицензия для выполнения кода?** Да, для использования в продакшене требуется действующая лицензия Aspose.Tasks.  
- **Могу ли я добавить несколько исключений в один календарь?** Да; коллекция `Exceptions` поддерживает множество записей.  
- **Поддерживаемые версии .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое исключение календаря?

**Исключение календаря** представляет отклонение от обычного рабочего календаря — условие, которое гласит: «в эти даты рабочие часы отличаются или их нет вовсе». В Aspose.Tasks каждое исключение может иметь собственные рабочие часы, шаблон повторения и флаги, указывающие, является ли день рабочим.

## Почему управлять исключениями календаря в планировании ASP.NET?

- **Точные сроки:** Проекты автоматически учитывают праздники и специальные закрытия, избегая нереалистичных дедлайнов.  
- **Гибкость:** Можно задавать ежедневные, еженедельные, ежемесячные или ежегодные шаблоны, соответствующие реальным бизнес‑календарям.  
- **Автоматизация:** Программная проверка даты исключения позволяет создавать динамическую логику планирования в приложениях ASP.NET.

## Требования

- Базовые знания программирования на C#.  
- Visual Studio (любая современная версия).  
- Библиотека Aspose.Tasks for .NET, добавленная в проект (через NuGet или вручную).

## Импорт пространств имён

Сначала импортируйте необходимые пространства имён:

```csharp
using Aspose.Tasks;
using System;
```

## Шаг 1: Удалить исключение календаря

Удаление нежелательного исключения простое. Ниже приведён код, который загружает проект, выбирает первый календарь, выводит базовую информацию, удаляет первое исключение и затем показывает обновлённое количество.

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

> **Совет:** Всегда проверяйте, существует ли индекс исключения, перед вызовом `Delete()`, чтобы избежать `IndexOutOfRangeException`.

## Шаг 2: Получить рабочее время исключения календаря

Если нужно просмотреть рабочие часы, определённые для исключения, используйте `GetWorkingTime()`. Этот пример также демонстрирует, как **проверять дату исключения** с помощью `CheckException`.

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

## Шаг 3: Определить исключения календаря

Ниже полное пошаговое руководство, показывающее, как **добавлять**, **проверять** и **удалять** исключения календаря. Обратите внимание на использование `CheckException` для **проверки даты исключения** в конкретный момент.

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

## Распространённые проблемы и советы

| Проблема | Причина | Решение |
|----------|---------|---------|
| **`IndexOutOfRangeException` при удалении** | Попытка удалить несуществующее исключение. | Убедитесь, что `calendar.Exceptions.Count` > индекса перед вызовом `Delete()`. |
| **Неправильное рабочее время** | Не корректно заданы `DayWorking` или `WorkingTimes`. | Используйте `exception.WorkingTimes.Add(new WorkingTime(...))` для определения явных периодов. |
| **Исключение не распознано** | `CheckException` возвращает `false`, потому что дата находится вне заданного диапазона. | Перепроверьте `FromDate`/`ToDate` и `Type` (Daily, Weekly и т.д.). |

## Часто задаваемые вопросы

**Q: Могу ли я добавить несколько исключений в один календарь?**  
A: Да, вы можете добавить столько исключений, сколько необходимо, чтобы представить праздники, окна обслуживания или любые специальные правила планирования.

**Q: Как я могу **проверить дату исключения** для конкретного дня?**  
A: Используйте метод `CheckException(DateTime date)` у экземпляра `CalendarException`. Он возвращает `true`, если указанная дата попадает в диапазон исключения.

**Q: Возможно ли удалить существующее исключение из календаря?**  
A: Абсолютно. Обратитесь к коллекции `Exceptions` и вызовите `Remove()` или выполните `Delete()` у конкретного объекта `CalendarException`.

**Q: Какие типы исключений календаря поддерживаются?**  
A: Aspose.Tasks поддерживает типы исключений Daily, Weekly, Monthly и Yearly, предоставляя гибкость для моделирования практически любого шаблона повторения.

**Q: Могу ли я настроить рабочие часы для конкретных дат исключения?**  
A: Да. После создания исключения заполните его коллекцию `WorkingTimes` объектами `WorkingTime`, определяющими время начала и окончания для этого дня.

## Заключение

Мы прошли полный цикл операций **удаления исключения календаря**, от просмотра существующих исключений до их добавления и проверки дат. Овладение этими приёмами гарантирует, что расписания ваших проектов учитывают реальные календари, делая реализации планирования в ASP.NET надёжными и устойчивыми.

---

**Последнее обновление:** 2026-04-13  
**Тестировано с:** Aspose.Tasks for .NET (latest release)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}