---
title: Обработка ссылок на задачи в Aspose.Tasks
linktitle: Обработка ссылок на задачи в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Изучите возможности Aspose.Tasks for .NET для эффективного управления связями задач проекта. Следуйте нашему пошаговому руководству, чтобы улучшить свой опыт управления проектами.
type: docs
weight: 19
url: /ru/net/task-table-management/task-link-collection/
---
## Введение
Добро пожаловать в пошаговое руководство по работе со ссылками на задачи в Aspose.Tasks для .NET! Ссылки на задачи играют решающую роль в управлении проектами, позволяя устанавливать связи между задачами и создавать зависимости. В этом уроке мы познакомим вас с процессом работы с коллекциями ссылок задач с помощью Aspose.Tasks.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
1.  Aspose.Tasks для библиотеки .NET: загрузите и установите библиотеку Aspose.Tasks. Вы можете найти библиотеку[здесь](https://releases.aspose.com/tasks/net/).
2. Образец файла проекта: подготовьте образец файла проекта (например, «SampleProject.mpp»), чтобы следовать примерам.
Теперь давайте начнем!
## Импортировать пространства имен
В вашем проекте .NET обязательно импортируйте необходимые пространства имен для работы с Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Шаг 1. Загрузите проект и получите доступ к задачам
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
// Загрузите проект
var project = new Project(DataDir + "SampleProject.mpp");
// Доступ к задачам по идентификатору
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## Шаг 2. Создайте ссылки на задачи
Свяжите задачи вместе, чтобы установить зависимости:
```csharp
// Свяжите задачи с помощью зависимости FinishToStart
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## Шаг 3. Печать ссылок на задачи
Распечатайте ссылки задач для проекта:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
// Перебирать ссылки задач
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## Шаг 4. Измените ссылку на задачу
Отредактируйте ссылку на задачу с помощью индексного доступа:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## Шаг 5. Удаление ссылок на задачи
Удалите все ссылки на задачи из проекта:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## Заключение
Поздравляем! Вы успешно научились обрабатывать ссылки на задачи в Aspose.Tasks для .NET. В этом подробном руководстве описывается загрузка проекта, создание ссылок на задачи, печать ссылок, редактирование ссылок и удаление ссылок на задачи.
Не стесняйтесь изучить дополнительные функции и возможности, предлагаемые Aspose.Tasks, чтобы улучшить свой опыт управления проектами.
## Часто задаваемые вопросы
### Совместим ли Aspose.Tasks со всеми версиями .NET?
Да, Aspose.Tasks предназначен для бесперебойной работы со всеми версиями .NET.
### Могу ли я создавать собственные типы ссылок на задачи с помощью Aspose.Tasks?
В настоящее время Aspose.Tasks поддерживает стандартные типы ссылок на задачи, а пользовательские типы ссылок недоступны.
### Как я могу применить ограничения к задачам в Aspose.Tasks?
 Вы можете применить ограничения, используя`ConstraintType` собственность`Task` класс в Aspose.Tasks.
### Есть ли какие-либо ограничения на размер файлов проекта, которые может обрабатывать Aspose.Tasks?
Aspose.Tasks может эффективно обрабатывать большие файлы проектов с минимальным влиянием на производительность.
### Есть ли форум сообщества для поддержки Aspose.Tasks?
 Да, вы можете найти поддержку и пообщаться с сообществом на[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).