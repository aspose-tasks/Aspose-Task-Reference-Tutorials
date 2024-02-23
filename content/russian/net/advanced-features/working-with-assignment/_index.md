---
title: Работа с назначениями в Aspose.Tasks
linktitle: Работа с назначениями в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как управлять назначениями проектов в .NET с помощью Aspose.Tasks. Изучите различные схемы планирования ресурсов.
type: docs
weight: 13
url: /ru/net/advanced-features/working-with-assignment/
---
## Введение

В этом уроке мы рассмотрим, как работать с заданиями в Aspose.Tasks для .NET. Назначения имеют решающее значение в управлении проектами, поскольку они распределяют ресурсы по задачам, помогая планировать и отслеживать прогресс. Мы сосредоточимся на создании поэтапных данных о назначении ресурсов с различными контурами с помощью Aspose.Tasks.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

1.  Установка Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks для .NET с сайта[ссылка для скачивания](https://releases.aspose.com/tasks/net/).
2. Базовое понимание C# и .NET Framework. Для дальнейшего обучения необходимо знание языка программирования C# и концепций .NET Framework.

## Импортировать пространства имен

Обязательно импортируйте необходимые пространства имен в свой проект C#:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Шаг 1. Создайте проект и задачу

Начнем с создания нового проекта и добавления в него задачи. Установите дату начала, продолжительность и дату окончания задачи:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Шаг 2. Добавьте ресурс и назначьте задачу

Далее добавляем в проект ресурс и назначаем его ранее созданной задаче:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Шаг 3. Сгенерируйте поэтапные данные с разными контурами

Теперь давайте сгенерируем поэтапные данные с различными контурами для назначения ресурсов:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Шаг 4. Измените контуры и сгенерируйте данные

Мы можем изменить тип контура и соответствующим образом генерировать поэтапные данные. Вот некоторые примеры:

```csharp
// Изменить контур
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Генерация повременных данных и их печать
// Повторите этот шаг для других типов контуров.
```

## Заключение

В этом уроке мы научились работать с заданиями в Aspose.Tasks для .NET. Мы исследовали создание поэтапных по времени данных о назначении ресурсов с различными контурами. Эти знания могут быть чрезвычайно полезны в сценариях управления проектами.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.Tasks для планирования задач в моем .NET-приложении?

О1: Да, Aspose.Tasks предоставляет комплексные API для планирования задач и управления ими в приложениях .NET.

### Вопрос 2. Доступна ли бесплатная пробная версия Aspose.Tasks?

 О2: Да, вы можете воспользоваться бесплатной пробной версией на сайте[здесь](https://releases.aspose.com/).

### В3: Есть ли какие-либо ограничения на количество задач или ресурсов в Aspose.Tasks?

О3: Aspose.Tasks не накладывает никаких ограничений на количество задач или ресурсов, которыми вы можете управлять в своих проектах.

### Вопрос 4: Могу ли я настроить контуры назначения ресурсов в Aspose.Tasks?

О4: Да, как показано в этом уроке, вы можете установить различные контуры, такие как черепаха, колокольчик, пик и т. д., в соответствии с требованиями вашего проекта.

### Вопрос 5: Где я могу найти поддержку по запросам, связанным с Aspose.Tasks?

 A5: Вы можете найти поддержку на[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) где эксперты и члены сообщества активно участвуют в дискуссиях.