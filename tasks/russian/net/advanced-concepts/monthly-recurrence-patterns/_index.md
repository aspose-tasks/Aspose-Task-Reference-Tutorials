---
title: Обработка шаблонов ежемесячного повторения в Aspose.Tasks
linktitle: Обработка шаблонов ежемесячного повторения в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как обрабатывать ежемесячные шаблоны повторения в Aspose.Tasks для .NET, с помощью этого пошагового руководства.
weight: 18
url: /ru/net/advanced-concepts/monthly-recurrence-patterns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Обработка шаблонов ежемесячного повторения в Aspose.Tasks

## Введение

Aspose.Tasks для .NET — это мощный API, который позволяет разработчикам программно манипулировать файлами Microsoft Project. Одной из важных функций, которые он предлагает, является способность эффективно решать повторяющиеся задачи. В этом уроке мы шаг за шагом углубимся в то, как работать с шаблонами ежемесячного повторения с помощью Aspose.Tasks.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас установлены следующие необходимые компоненты:

## Импортировать пространства имен

Сначала убедитесь, что вы импортировали необходимые пространства имен в свой проект .NET:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Теперь давайте разобьем процесс обработки ежемесячных шаблонов повторения на несколько этапов:

## Шаг 1. Инициализируйте проект

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Шаг 2. Установите параметры повторяющихся задач

Определите параметры повторяющейся задачи, включая имя задачи, продолжительность и шаблон повторения:

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

## Шаг 3. Добавьте параметры в проект

```csharp
project.RootTask.Children.Add(parameters);
```

## Шаг 4. Сохраните проект

Сохраните измененный проект с повторяющейся задачей:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Заключение

Обработка ежемесячных шаблонов повторения в Aspose.Tasks для .NET проста и эффективна. Следуя инструкциям, описанным в этом руководстве, вы можете легко создавать повторяющиеся задачи с определенными ежемесячными интервалами и диапазонами повторения.

## Часто задаваемые вопросы

### Вопрос 1. Совместим ли Aspose.Tasks со всеми версиями файлов Microsoft Project?

A1: Aspose.Tasks поддерживает различные версии файлов Microsoft Project, включая MPP, MPT, XML и MPX.

### Вопрос 2. Могу ли я дополнительно настроить шаблон повторения?

О2: Да, Aspose.Tasks предоставляет широкие возможности для настройки шаблонов повторения, включая ежедневно, еженедельно, ежемесячно и ежегодно.

### Вопрос 3: Существует ли бесплатная пробная версия Aspose.Tasks?

 О3: Да, вы можете получить бесплатную пробную версию Aspose.Tasks на сайте.[здесь](https://releases.aspose.com/).

### В4: Как я могу получить поддержку для Aspose.Tasks?

 О4: Вы можете обратиться за помощью и принять участие в обсуждениях по[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### В5: Где я могу приобрести лицензию на Aspose.Tasks?

 A5: Вы можете приобрести лицензию на Aspose.Tasks на сайте.[здесь](https://purchase.aspose.com/buy)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
