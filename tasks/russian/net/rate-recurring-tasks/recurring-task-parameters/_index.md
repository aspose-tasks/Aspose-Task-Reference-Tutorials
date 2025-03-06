---
title: Настройка параметров повторяющихся задач в Aspose.Tasks
linktitle: Настройка параметров повторяющихся задач в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как установить параметры повторяющихся задач в Microsoft Project с помощью Aspose.Tasks для .NET. Подробное руководство с пошаговым руководством.
weight: 14
url: /ru/net/rate-recurring-tasks/recurring-task-parameters/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Настройка параметров повторяющихся задач в Aspose.Tasks

## Введение
В этом руководстве мы проведем вас через процесс настройки параметров повторяющихся задач Microsoft Project с помощью Aspose.Tasks для .NET.
## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующее:
1. Базовое понимание языка программирования C#.
2. Установленная Visual Studio или любая другая C# IDE.
3. Библиотека Aspose.Tasks для .NET установлена и используется в вашем проекте.

## Импортировать пространства имен
Во-первых, вам необходимо импортировать необходимые пространства имен в ваш код C#:
```csharp
using Aspose.Tasks;
using System;

```
## Шаг 1. Определите каталог документов
```csharp
String DataDir = "Your Document Directory";
```
 Заменять`"Your Document Directory"` с путем к каталогу вашего документа.
## Шаг 2. Загрузите файл проекта
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Эта строка кода загружает файл Microsoft Project в`project` переменная.
## Шаг 3. Определите параметры повторяющихся задач
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Здесь вы определяете параметры повторяющейся задачи, такие как имя задачи, продолжительность, шаблон повторения, диапазон повторения и необходимость игнорировать календарь ресурсов.
## Шаг 4. Установите календарь для повторяющихся задач
```csharp
parameters.SetCalendar(project, "Standard");
```
На этом шаге устанавливается календарь для повторяющейся задачи. В этом примере для календаря установлено значение «Стандартный».
## Шаг 5. Добавьте параметры в проект
```csharp
project.RootTask.Children.Add(parameters);
```
Наконец, добавьте параметры в корневую задачу проекта.

## Заключение
В этом руководстве мы продемонстрировали, как установить параметры повторяющихся задач Microsoft Project с помощью Aspose.Tasks для .NET. Следуя этим шагам, вы сможете эффективно управлять повторяющимися задачами в своих проектах.
## Часто задаваемые вопросы
### Могу ли я дополнительно настроить шаблон повторения?
Да, Aspose.Tasks предоставляет различные шаблоны повторения и параметры, которые можно настроить в соответствии с требованиями вашего проекта.
### Доступна ли пробная версия перед покупкой?
 Да, вы можете скачать бесплатную пробную версию на сайте Aspose.Tasks.[Веб-сайт](https://purchase.aspose.com/buy) оценить возможности библиотеки.
### Поддерживает ли Aspose.Tasks другие форматы файлов проекта?
Да, Aspose.Tasks поддерживает различные форматы файлов проектов, включая MPP, XML, XLSX и другие.
### Могу ли я получить поддержку, если у меня возникнут какие-либо проблемы во время реализации?
Да, вы можете посетить форум Aspose.Tasks для получения помощи от сообщества или обратиться в службу поддержки для получения прямой помощи.
### Как я могу получить временную лицензию для Aspose.Tasks?
 Вы можете получить временную лицензию в[Веб-сайт](https://purchase.aspose.com/temporary-license/) в целях тестирования.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
