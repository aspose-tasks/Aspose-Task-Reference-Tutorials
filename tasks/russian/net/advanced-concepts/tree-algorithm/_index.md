---
title: Использование древовидного алгоритма в Aspose.Tasks
linktitle: Использование древовидного алгоритма в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно манипулировать иерархиями задач в ваших проектах .NET с помощью алгоритма дерева Aspose.Tasks.
weight: 13
url: /ru/net/advanced-concepts/tree-algorithm/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Использование древовидного алгоритма в Aspose.Tasks

## Введение

Aspose.Tasks для .NET предоставляет мощные функциональные возможности для работы с задачами, ресурсами и расписаниями управления проектами. Одной из таких функций является древовидный алгоритм, который позволяет пользователям эффективно управлять иерархией задач. В этом руководстве мы рассмотрим, как использовать древовидный алгоритм в Aspose.Tasks для .NET для сбора общих рабочих значений и обновления рабочих значений в проекте.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

1. Visual Studio: убедитесь, что в вашей системе установлена Visual Studio.
2.  Aspose.Tasks для .NET: Загрузите и установите Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/tasks/net/).
3. Базовое понимание C#. Для работы с примерами необходимо знание языка программирования C#.

## Импортировать пространства имен

В свой проект C# импортируйте необходимые пространства имен для работы с функциями Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Теперь давайте разобьем каждый пример на несколько этапов:

## Шаг 1. Загрузите файл проекта

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Загрузите файл проекта в память, используя команду`Project` сорт.

## Шаг 2. Определите иерархию задач

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Определите иерархию задач, добавив родительские и дочерние задачи.

## Шаг 3. Установите свойства задачи

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Установите такие свойства, как дата начала, продолжительность и дата окончания для задач.

## Шаг 4: Добавьте ресурс

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Добавляйте ресурсы в проект и назначайте их задачам по мере необходимости.

## Шаг 5. Примените древовидный алгоритм

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Инициализируйте`WorkAccumulator` класс и применить древовидный алгоритм для сбора общей работы.

## Шаг 6. Обновление задачи задачи

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Обновите значения работы для задач на основе собранной информации.

## Заключение

В этом руководстве мы узнали, как использовать древовидный алгоритм в Aspose.Tasks для .NET для эффективного управления иерархией задач. Следуя пошаговому руководству, вы сможете эффективно управлять задачами и ресурсами в своих проектах.

## Часто задаваемые вопросы

### Вопрос 1. Что такое Aspose.Tasks для .NET?

A1: Aspose.Tasks for .NET — это мощный API, который позволяет разработчикам программно манипулировать файлами Microsoft Project с помощью C#.

### Вопрос 2: Могу ли я загрузить бесплатную пробную версию Aspose.Tasks для .NET?

 О2: Да, вы можете загрузить бесплатную пробную версию Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/).

### Вопрос 3. Где я могу найти документацию по Aspose.Tasks для .NET?

 A3: Вы можете найти документацию по Aspose.Tasks для .NET.[здесь](https://reference.aspose.com/tasks/net/).

### Вопрос 4: Как я могу получить поддержку Aspose.Tasks для .NET?

 A4: Для получения поддержки, связанной с Aspose.Tasks для .NET, вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Вопрос 5. Существует ли временная лицензия для целей тестирования?

 О5: Да, вы можете получить временную лицензию для целей тестирования на сайте[здесь](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
