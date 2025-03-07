---
title: Ежедневное повторение работы в Aspose.Tasks
linktitle: Ежедневное повторение работы в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как создавать ежедневно повторяющиеся задачи в файлах Microsoft Project с помощью Aspose.Tasks для .NET. Повышайте производительность и организованность без особых усилий.
weight: 26
url: /ru/net/calendar-scheduling/daily-work-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ежедневное повторение работы в Aspose.Tasks

## Введение

Aspose.Tasks для .NET — это мощная библиотека, которая позволяет разработчикам с легкостью манипулировать файлами Microsoft Project. Среди множества его функций — способность эффективно решать повторяющиеся задачи. В этом уроке мы углубимся в функцию ежедневного повторения работ, которая позволяет создавать задачи, которые повторяются ежедневно в рамках проекта.

## Предварительные условия

Прежде чем погрузиться в это руководство, убедитесь, что у вас есть следующее:

- Базовые знания C# и .NET framework.
- Visual Studio установлена в вашей системе.
-  Aspose.Tasks для библиотеки .NET. Вы можете скачать его[здесь](https://releases.aspose.com/tasks/net/).
- Знакомство с файлами Microsoft Project (.mpp).

## Импортировать пространства имен

Прежде чем мы начнем, убедитесь, что вы импортировали необходимые пространства имен:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Разобьем приведенный пример на несколько этапов:

## Шаг 1. Загрузите файл проекта

Сначала загрузите файл проекта, используя`Project` сорт:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Шаг 2. Определите параметры повторяющихся задач

Определите параметры повторяющейся задачи:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## Шаг 3. Установите календарь и дату начала задачи

Установите календарь и дату начала задачи:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## Заключение

В этом руководстве мы рассмотрели, как использовать Aspose.Tasks для .NET для создания повторяющихся задач с ежедневным повторением работы. Следуя этим шагам, вы сможете эффективно управлять задачами в своих проектах, обеспечивая бесперебойный рабочий процесс и организацию.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я дополнительно настроить шаблон повторения?

О1: Да, вы можете настроить такие параметры, как дата начала, количество повторений и интервал повторения, чтобы настроить шаблон повторения в соответствии с вашими требованиями.

### Вопрос 2. Совместим ли Aspose.Tasks с различными версиями Microsoft Project?

О2: Да, Aspose.Tasks поддерживает различные версии Microsoft Project, обеспечивая совместимость и бесшовную интеграцию.

### Вопрос 3. Как обрабатывать исключения или изменения в повторяющихся задачах?

A3: Aspose.Tasks обеспечивает надежную функциональность для управления исключениями и изменениями в повторяющихся задачах, обеспечивая гибкость и настройку.

### В4: Могу ли я экспортировать проект в другие форматы?

О4: Конечно, Aspose.Tasks предлагает поддержку экспорта проектов в различные форматы, включая PDF, HTML, XML и другие, что упрощает совместное использование и совместную работу.

### В5: Предлагает ли Aspose.Tasks техническую поддержку?

О5: Да, Aspose.Tasks предоставляет комплексную техническую поддержку через свой форум, где вы можете обратиться за помощью, поделиться опытом и пообщаться с другими пользователями.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
