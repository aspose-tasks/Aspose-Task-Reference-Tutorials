---
date: 2026-03-08
description: Узнайте, как создать ежемесячную повторяющуюся задачу в Aspose.Tasks
  для .NET с помощью этого пошагового руководства.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Как создать ежемесячную повторяющуюся задачу в Aspose.Tasks
url: /ru/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание ежемесячной повторяющейся задачи с помощью Aspose.Tasks

## Introduction

Aspose.Tasks for .NET позволяет программно манипулировать файлами Microsoft Project, и одной из самых распространённых реальных потребностей является **создание расписаний ежемесячных повторяющихся задач**. Независимо от того, создаёте ли вы инструмент отслеживания проектов, автоматизируете распределение ресурсов или генерируете повторяющиеся задачи обслуживания, этот учебник проведёт вас через точные шаги добавления ежемесячного шаблона повторения к задаче.

В следующих разделах вы увидите, как настроить проект, определить параметры повторения и, наконец, сохранить обновлённый файл — всё с понятными объяснениями и практическими советами.

## Quick Answers
- **Что означает «ежемесячная повторяющаяся задача»?** Задача, которая повторяется по определённому шаблону день‑или‑неделя каждый месяц.  
- **Какой класс API обрабатывает повторения?** `RecurringTaskParameters` вместе с `MonthlyRecurrencePattern`.  
- **Нужна ли лицензия для запуска примера?** Бесплатная пробная версия подходит для оценки; лицензия требуется для продакшн.  
- **Можно ли изменить интервал?** Да — задайте `RepetitionInterval` числом месяцев между появлениями.  
- **Какие форматы файлов поддерживаются?** Можно загружать и сохранять файлы проекта в форматах `.mpp` и `.xml`.

## What is a Monthly Recurrence Pattern?

Ежемесячный шаблон повторения сообщает Microsoft Project (и Aspose.Tasks), как часто задача должна повторяться каждый месяц. Вы можете указать фиксированный день месяца (например, 1‑е) или относительное положение (например, последний пятница). API переводит эти правила в структуру файла проекта.

## Why use Aspose.Tasks for this?

- **Полный контроль** — без ограничений UI; вы определяете каждый аспект шаблона в коде.  
- **Кросс‑платформенный** — работает на .NET Framework, .NET Core и .NET 5/6+.  
- **Не требуется Microsoft Project** — генерируйте или изменяйте файлы на сервере или в CI‑конвейере.  

## Prerequisites

Перед началом убедитесь, что у вас есть:

- .NET 6 (или .NET 5/Framework 4.7+) установлен.  
- Пакет NuGet Aspose.Tasks for .NET добавлен в ваш проект.  
- Пример файла проекта (`Project1.mpp`) размещён в известной папке (`DataDir`).  

## Import Namespaces

First, import the namespaces required for working with tasks and saving projects:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Step 1: Initialize the Project

Create a `Project` instance that points to your existing `.mpp` file. This loads the file into memory so you can modify it.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Совет:** Если файл не существует, Aspose.Tasks автоматически создаст новый пустой проект.

## Step 2: Set Recurring Task Parameters

Define the details of the recurring task, including its name, duration, and the monthly pattern you want to apply.

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

- `DayPosition = 1` означает, что задача происходит в **первый день** месяца.  
- `RepetitionInterval = 2` заставляет задачу повторяться **каждые два месяца**.  
- `Start` и `Finish` определяют общий период, в течение которого повторение активно.

## Step 3: Add Parameters to the Project

Attach the `RecurringTaskParameters` object to the root task’s children collection. This effectively creates the recurring task in the project hierarchy.

```csharp
project.RootTask.Children.Add(parameters);
```

## Step 4: Save the Project

Persist the changes by saving the project to a new file. You can choose any supported format; here we use the native `.mpp` format.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

After running the code, open the resulting file in Microsoft Project to see the monthly recurring task you just created.

## Common Issues and Solutions

| Проблема | Причина | Решение |
|----------|---------|---------|
| Задача не появляется после сохранения | Проект не обновлён в UI | Перезапустите файл или вызовите `project.UpdateTaskLinks()` перед сохранением. |
| Неправильная дата начала | `Start` установлен на выходные | Используйте `DateTime`, попадающий на рабочий день, или скорректируйте календарь. |
| Игнорируется интервал повторения | Используется `ByMonthDayRepetition` с `DayPosition` = 0 | Убедитесь, что `DayPosition` в диапазоне 1‑31. |

## Conclusion

Следуя этим шагам, вы теперь знаете, как **создавать расписания ежемесячных повторяющихся задач** с помощью Aspose.Tasks для .NET. API предоставляет детальный контроль над интервалами повторения, диапазонами начала/завершения и конкретным шаблоном дня, позволяя автоматизировать сложные сценарии планирования проектов.

## FAQ's

### Q1: Is Aspose.Tasks compatible with all versions of Microsoft Project files?

A1: Aspose.Tasks supports various versions of Microsoft Project files, including MPP, MPT, XML, and MPX.

### Q2: Can I customize the recurrence pattern further?

A2: Yes, Aspose.Tasks provides extensive options for customizing recurrence patterns, including daily, weekly, monthly, and yearly.

### Q3: Is there a free trial available for Aspose.Tasks?

A3: Yes, you can obtain a free trial of Aspose.Tasks from the website [here](https://releases.aspose.com/).

### Q4: How can I get support for Aspose.Tasks?

A4: You can seek assistance and participate in discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: Where can I purchase a license for Aspose.Tasks?

A5: You can purchase a license for Aspose.Tasks from the website [here](https://purchase.aspose.com/buy)

## Frequently Asked Questions

**Q: Can I use this code in a .NET Core application?**  
A: Absolutely. Aspose.Tasks for .NET fully supports .NET Core 3.1 and later versions.

**Q: How do I change the recurrence to “last weekday of the month”?**  
A: Use `ByMonthDayRepetition` with `DayPosition = -1` (negative values count from the end of the month) and set `WeekDay` accordingly.

**Q: What happens if the recurrence range exceeds the project’s calendar?**  
A: The API respects the project calendar; occurrences falling on non‑working days are either skipped or moved based on the calendar’s settings.

**Q: Is it possible to delete a specific occurrence of a recurring task?**  
A: Yes. After adding the recurring task, you can retrieve individual occurrences via `Task.GetOccurrences()` and delete the ones you don’t need.

**Q: Does Aspose.Tasks handle timezone differences automatically?**  
A: The library stores dates in UTC; you can convert to local time using standard .NET `DateTime` methods if needed.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}