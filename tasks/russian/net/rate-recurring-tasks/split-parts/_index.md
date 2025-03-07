---
title: Обработка разделенных частей MS Project в Aspose.Tasks
linktitle: Обработка разделенных частей в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно обрабатывать разделенные части MS Project с помощью Aspose.Tasks для .NET. Улучшите рабочий процесс управления проектами.
weight: 18
url: /ru/net/rate-recurring-tasks/split-parts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Обработка разделенных частей MS Project в Aspose.Tasks


## Введение
Управление разделенными частями MS Project может быть важным аспектом управления проектами при использовании Aspose.Tasks для .NET. В этом уроке мы рассмотрим, как эффективно обрабатывать разделенные части, используя пошаговые инструкции.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
1.  Установка Aspose.Tasks для .NET: Загрузите и установите Aspose.Tasks для .NET с сайта[Веб-сайт](https://releases.aspose.com/tasks/net/).
   
2. Базовое понимание C#: Знакомство с языком программирования C# будет полезным.

## Импортировать пространства имен
Обязательно импортируйте в свой код C# необходимые пространства имен:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Шаг 1. Создание экземпляра проекта
```csharp
var project = new Project();
```
 Создайте новый экземпляр`Project` сорт.
## Шаг 2. Установка дат начала и окончания проекта
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Установите даты начала и окончания проекта.
## Шаг 3. Добавление задачи
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Добавьте в проект новую задачу.
## Шаг 4. Настройка свойств задачи
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Установите такие свойства, как статус вручную, дату начала и продолжительность задачи.
## Шаг 5. Добавление назначений ресурсов
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Добавьте назначения ресурсов в задачу.
## Шаг 6. Настройка свойств назначения
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Установите такие свойства, как дата начала, работа и дата окончания для назначения.
## Шаг 7: Генерация повременных данных
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Создавайте повременные данные для назначения на основе календаря проекта.
## Шаг 8: Разделение задачи
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Разделите задачу на несколько частей в течение указанного периода времени.
## Шаг 9: Итерация по разделенным частям
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Переберите разделенные части задачи и распечатайте даты их начала и окончания.

## Заключение
Эффективная обработка разделенных частей MS Project в Aspose.Tasks для .NET имеет решающее значение для эффективности управления проектами. Следуя шагам, описанным в этом руководстве, вы сможете легко управлять разделенными задачами и улучшить рабочий процесс управления проектами.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks для .NET с другими платформами .NET?
О: Да, Aspose.Tasks для .NET совместим с различными платформами .NET, включая .NET Core и .NET Standard.
### Вопрос: Существует ли бесплатная пробная версия Aspose.Tasks для .NET?
 О: Да, вы можете получить бесплатную пробную версию на сайте[здесь](https://releases.aspose.com/).
### Вопрос: Поддерживает ли Aspose.Tasks для .NET управление ресурсами?
О: Да, Aspose.Tasks для .NET позволяет эффективно управлять ресурсами проекта.
### Вопрос: Могу ли я настроить календари проектов с помощью Aspose.Tasks для .NET?
О: Конечно, вы можете настроить календари проектов в соответствии с требованиями вашего проекта.
### Вопрос: Где я могу найти поддержку Aspose.Tasks для .NET?
 О: Вы можете найти поддержку и помощь на[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
