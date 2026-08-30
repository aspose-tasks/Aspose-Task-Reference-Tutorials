---
date: 2026-04-01
description: Узнайте, как задать повторяемость в Aspose.Tasks для .NET, добавить повторяющуюся
  задачу и автоматизировать повторяющиеся задачи по месяцам, неделям и дням.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Повторение по месяцам, неделям и дням в Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Как установить повторяемость в Aspose.Tasks (месяц, неделя, день)
url: /ru/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить повторяемость в Aspose.Tasks (Месяц, Неделя, День)

## Введение

Если вам нужно **how to set recurrence** для задач в проекте, Aspose.Tasks for .NET предоставляет чистый программный способ добавить определения повторяющихся задач, которые выполняются по месяцам, неделям или дням. В этом руководстве мы пройдем реальный пример, показывающий, как **add recurring task** записи, **automate recurring tasks**, и управлять ими напрямую из кода C#. К концу вы будете готовы интегрировать эту возможность в любое решение по планированию или управлению проектами.

## Быстрые ответы
- **Что означает “recurrence” в Aspose.Tasks?** Это определяет шаблон (ежедневный, еженедельный, ежемесячный), который автоматически создает экземпляры задач в течение диапазона дат.  
- **Какой основной метод создает повторяемость?** `RecurringTaskParameters` в сочетании с конкретным `RecurrencePattern`.  
- **Нужна ли лицензия для выполнения этого кода?** Пробная версия подходит для оценки; коммерческая лицензия требуется для продакшна.  
- **Могу ли я планировать еженедельные задачи вместо ежемесячных?** Да — замените `MonthlyRecurrencePattern` на `WeeklyRecurrencePattern`.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 и более новые.

## Что такое повторяемость в Aspose.Tasks?

Повторяемость — это набор правил, который говорит Aspose.Tasks генерировать экземпляры задач через регулярные интервалы — ежедневно, еженедельно или ежемесячно — без необходимости вручную дублировать их. Эта функция важна для проектов, содержащих рутинные действия, такие как совещания по статусу, инспекции или техническое обслуживание.

## Зачем использовать функции повторяемости?

- **Экономия времени:** Не нужно копировать‑вставлять задачи вручную.  
- **Снижение ошибок:** Библиотека гарантирует согласованные даты и длительности.  
- **Гибкость:** Комбинируйте шаблоны (например, “первая воскресенье каждого 2‑го месяца”).  
- **Автоматизация:** Идеально подходит для генерации расписаний в CI‑конвейерах или инструментах отчетности.

## Требования

1. **Базовое понимание C#** – вы будете писать несколько строк кода C#.  
2. **Aspose.Tasks for .NET установлен** – скачайте его со [страницы загрузки](https://releases.aspose.com/tasks/net/).  
3. **Файл проекта .mpp** – мы будем использовать `Project1.mpp` в качестве исходного файла.

## Импорт пространств имён

Чтобы начать, импортируйте необходимые пространства имён Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Шаг 1: Загрузить файл проекта

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Мы создаём экземпляр `Project`, указывающий на существующий файл Microsoft Project.

### Шаг 2: Определить параметры повторяющейся задачи

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Здесь мы **create recurring task** параметры:

- **TaskName** – имя генерируемой задачи.  
- **Duration** – продолжительность каждого появления.  
- **RecurrencePattern** – ежемесячный шаблон, который повторяется каждые 2 месяца в первое воскресенье.  
- **RecurrenceRange** – даты начала и окончания, ограничивающие расписание.

### Шаг 3: Добавить повторяющуюся задачу в проект

```csharp
project.RootTask.Children.Add(parameters);
```

Эта строка **adds the recurring task** в корень иерархии проекта.

### Шаг 4: Сохранить обновлённый проект

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Проект сохраняется как новый файл `.mpp`, который теперь содержит автоматическое расписание.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|----------|----------|
| **Задача не отображается** | Диапазон повторения выходит за пределы дат проекта. | Проверьте, что значения `Start` и `Finish` находятся в пределах календаря проекта. |
| **Неправильный день недели** | Несоответствие перечисления `WeekDay`. | Используйте `DayOfWeek.Monday` … `DayOfWeek.Sunday` по необходимости. |
| **Исключение лицензии** | Запуск без действующей лицензии в продакшене. | Примените временную или полную лицензию перед сохранением. |

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я настроить шаблон повторения за пределами предоставленных примеров?

A1: Да, Aspose.Tasks for .NET предлагает обширные возможности настройки шаблонов повторения, позволяя адаптировать их под ваши конкретные требования.

### Вопрос 2: Доступна ли пробная версия Aspose.Tasks for .NET?

A2: Да, вы можете получить бесплатную пробную версию Aspose.Tasks for .NET со [страницы релизов](https://releases.aspose.com/).

### Вопрос 3: Как я могу получить поддержку для Aspose.Tasks for .NET?

A3: Вы можете обратиться за помощью и пообщаться с сообществом на [форуме Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Вопрос 4: Доступны ли временные лицензии для Aspose.Tasks for .NET?

A4: Да, вы можете приобрести временные лицензии со [страницы покупки](https://purchase.aspose.com/temporary-license/) для тестирования и оценки.

### Вопрос 5: Где я могу найти полную документацию по Aspose.Tasks for .NET?

A5: Вы можете обратиться к подробной [документации](https://reference.aspose.com/tasks/net/) на сайте Aspose для глубокого руководства по использованию библиотеки.

---

**Last Updated:** 2026-04-01  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}