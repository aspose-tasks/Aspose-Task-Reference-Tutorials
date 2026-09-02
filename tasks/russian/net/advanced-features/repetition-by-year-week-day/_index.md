---
date: 2026-04-03
description: Узнайте, как использовать Aspose.Tasks для добавления повторяющихся задач
  в проект и сохранения проекта в формате MPP. Это руководство пошагово демонстрирует
  функцию повторения по годам, неделям и дням.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Повторение по году, неделе и дню в Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Как использовать Aspose.Tasks — Повторение по году, неделе, дню
url: /ru/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Повторение по году, неделе, дню в Aspose.Tasks

## Введение

Когда вам нужно **how to use Aspose.Tasks** для работы со сложными повторяющимися расписаниями, библиотека предоставляет тонкий контроль над годовыми шаблонами. В этом руководстве мы пройдем процесс создания задачи, которая повторяется в определенный день недели конкретного месяца, охватывая несколько лет. К концу вы сможете **add recurring task project** записи и **save project as MPP** всего несколькими строками C#.

## Быстрые ответы
- **What does “Repetition by Year Week Day” mean?** Он повторяет задачу в выбранный день недели (например, первое воскресенье) заданного месяца каждый год.  
- **Which .NET versions are supported?** Поддерживаются все современные версии .NET Framework и .NET Core/5/6.  
- **Do I need a license to run the code?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.  
- **Can I change the recurrence range?** Да — вы можете задать дату начала, дату окончания или фиксированное количество повторений.  
- **Is the output an MPP file?** Абсолютно — проект сохраняется в файл MPP, готовый для Microsoft Project.

## Что такое функция “Repetition by Year Week Day”?

Эта функция позволяет определить годовое повторение, которое нацелено на определенный **day of the week** (например, Sunday) и **position** внутри месяца (первый, второй, последний и т.д.). Это идеально подходит для задач, таких как квартальные обзоры, ежегодные аудиты или любые события, следящие за календарным ритмом.

## Почему использовать Aspose.Tasks для повторяющихся задач?

- **Precision** – Полный контроль над месяцами, днями недели и порядковыми позициями.  
- **Compatibility** – Генерирует нативные файлы MPP, которые открываются без проблем в Microsoft Project.  
- **No COM interop** – Чистый .NET API, без необходимости установки Office.  
- **Scalability** – Работает как с небольшими проектами, так и с расписаниями корпоративного уровня.

## Требования

Before diving into the code, make sure you have:

1. **Basic .NET knowledge** – Знание C# и объектно‑ориентированных концепций.  
2. **Aspose.Tasks for .NET** – Скачайте его по [download link](https://releases.aspose.com/tasks/net/) и добавьте DLL в ваш проект.  
3. **Access to the official docs** – [documentation](https://reference.aspose.com/tasks/net/) содержит полные детали обо всех классах.  
4. **A development IDE** – Visual Studio, Rider или любой совместимый .NET редактор.

Теперь, когда всё готово, посмотрим реализацию.

## Как использовать Aspose.Tasks для повторяющихся задач

### Импорт необходимых пространств имён

Сначала импортируйте необходимые пространства имён, чтобы работать с проектами, задачами и параметрами сохранения.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Шаг 1: Инициализация проекта и параметров задачи

Создайте новый экземпляр `Project`, затем определите объект `RecurringTaskParameters`, описывающий шаблон повторения.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** Настройте `Month`, `WeekDay` и `Position` в соответствии с вашим реальным расписанием.

### Шаг 2: Добавление параметров в проект

Вставьте определение повторяющейся задачи в корень проекта.

```csharp
project.RootTask.Children.Add(parameters);
```

### Шаг 3: Сохранение проекта в формате MPP

Наконец, сохраните проект в файл MPP, чтобы его можно было открыть в Microsoft Project или любом совместимом просмотрщике.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> Это демонстрирует **save project as mpp** в одну строку кода.

## Распространённые проблемы и решения

| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| Задачи не отображаются после открытия файла MPP | Даты диапазона повторения находятся за пределами календаря проекта | Убедитесь, что даты `Start` и `Finish` находятся в пределах рабочего времени проекта |
| Исключение `ArgumentNullException` при `Add` | `parameters` равно null или не полностью инициализировано | Убедитесь, что установлены все обязательные свойства (TaskName, Duration, RecurrencePattern) |
| Выбран неверный день недели | Несоответствие значения перечисления `WeekDay` | Используйте `DayOfWeek.Monday` … `DayOfWeek.Sunday` по необходимости |

## Часто задаваемые вопросы

**Q: Могу ли я настроить шаблон повторения за пределами приведённого примера?**  
**A:** Да, Aspose.Tasks позволяет комбинировать `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern` или даже пользовательские объекты `RecurrenceRange` для любой схемы.

**Q: Совместим ли Aspose.Tasks для .NET с другим программным обеспечением для управления проектами?**  
**A:** Абсолютно — библиотека читает и записывает форматы MPP, XML и Primavera, обеспечивая плавный обмен данными.

**Q: Как обрабатывать исключения или изменения в повторяющихся задачах?**  
**A:** Используйте класс `ExceptionTask` для создания переопределений конкретных повторений, либо отредактируйте `RecurringTaskParameters` и снова сохраните проект.

**Q: Поддерживает ли Aspose.Tasks облачные решения?**  
**A:** Да, вы можете запускать API в Azure Functions, AWS Lambda или любом облачном сервисе, совместимом с .NET.

**Q: Доступна ли пробная версия Aspose.Tasks для .NET?**  
**A:** Да, вы можете получить бесплатную пробную версию Aspose.Tasks для .NET с [website](https://releases.aspose.com/), что позволяет изучить функции перед принятием решения о покупке.

**Q: Как добавить повторяющуюся задачу в существующий проект, не перезаписывая другие данные?**  
**A:** Загрузите существующий проект с помощью `new Project("Existing.mpp")`, добавьте `RecurringTaskParameters` в `RootTask.Children` и затем `Save` файл.

## Заключение

Освоив **how to use Aspose.Tasks** для сценария **Repetition by Year Week Day**, вы получаете возможность **add recurring task project** записей, которые идеально соответствуют реальным календарям, и **save project as MPP** для бесшовного сотрудничества. Внедрите эти фрагменты в свои решения, чтобы повысить точность планирования и сократить ручные усилия.

---

**Последнее обновление:** 2026-04-03  
**Тестировано с:** Aspose.Tasks 24.12 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}