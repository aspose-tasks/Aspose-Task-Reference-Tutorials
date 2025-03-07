---
title: Управление базовым планом назначений в Aspose.Tasks
linktitle: Управление базовым планом назначений в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно управлять базовыми планами заданий с помощью Aspose.Tasks для .NET, обеспечивая точное отслеживание хода выполнения и производительности проекта.
weight: 14
url: /ru/net/advanced-features/assignment-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Управление базовым планом назначений в Aspose.Tasks

## Введение

При работе над задачами управления проектами управление базовыми планами заданий имеет решающее значение для точного отслеживания прогресса. Aspose.Tasks для .NET предоставляет полный набор инструментов для эффективной обработки базовых показателей назначения. В этом руководстве мы шаг за шагом углубимся в процесс управления базовыми планами назначений.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

- Базовые знания языка программирования C#.
- Visual Studio установлена в вашей системе.
- В ваш проект добавлена библиотека Aspose.Tasks for .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/tasks/net/).
- Доступ к файлу проекта в формате MPP.

## Импортировать пространства имен

Чтобы начать работу с Aspose.Tasks, вам необходимо импортировать необходимые пространства имен в ваш проект C#. Добавьте следующие пространства имен в начало файла C#:

```csharp
using Aspose.Tasks;
using System;


```

## Шаг 1. Загрузите проект и установите базовый план

 Сначала загрузите файл проекта, используя`Project` класс из Aspose.Tasks. Затем установите тип базового плана для проекта, используя`SetBaseline` метод.

```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Шаг 2. Прочтите базовую информацию о задании

Выполните итерацию каждого назначения ресурсов в проекте и получите базовую информацию для каждого назначения.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Шаг 3. Проверьте базовое равенство

Сравните базовую информацию для разных заданий, используя различные методы сравнения, предоставляемые Aspose.Tasks.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Проверьте базовое равенство
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Проверьте сравнение базовых показателей
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Отображение базовых хэш-кодов
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Заключение

Управление базовыми планами заданий является неотъемлемой частью управления проектами, позволяя точно отслеживать ход выполнения и производительность. Благодаря Aspose.Tasks для .NET обработка базовых планов назначений становится упрощенной и эффективной, предоставляя разработчикам мощные инструменты для улучшения рабочих процессов управления проектами.

## Часто задаваемые вопросы

### Вопрос 1. Может ли Aspose.Tasks обрабатывать несколько базовых показателей для одного задания?

О1: Да, Aspose.Tasks поддерживает несколько базовых показателей для каждого задания, что позволяет всесторонне отслеживать ход проекта с течением времени.

### Вопрос 2. Совместим ли Aspose.Tasks с различными форматами файлов проектов, кроме MPP?

О2: Да, Aspose.Tasks поддерживает широкий спектр форматов файлов проектов, включая XML, MPX и MPP, обеспечивая совместимость с различными инструментами управления проектами.

### Вопрос 3. Могу ли я изменить базовую информацию программно с помощью Aspose.Tasks?

О3: Конечно, Aspose.Tasks предоставляет обширные API-интерфейсы для динамического изменения базовой информации в соответствии с требованиями проекта, предлагая гибкость и контроль над процессами управления проектами.

### Вопрос 4: Предлагает ли Aspose.Tasks документацию и ресурсы поддержки для разработчиков?

О4: Да, разработчики могут получить доступ к подробной документации, руководствам и форумам на веб-сайте Aspose.Tasks, что облегчает интеграцию и устранение неполадок.

### Вопрос 5: Доступна ли пробная версия Aspose.Tasks для .NET?

 О5: Да, разработчики могут получить бесплатную пробную версию Aspose.Tasks для .NET на сайте[здесь](https://releases.aspose.com/), что позволяет им оценить его характеристики и возможности перед принятием решения о покупке.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
