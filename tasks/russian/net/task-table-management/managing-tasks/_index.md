---
title: Управление задачами в Aspose.Tasks
linktitle: Управление задачами в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Изучите подробное руководство по управлению задачами с помощью Aspose.Tasks для .NET. Научитесь добавлять, отображать разделенные части, перемещать, получать/устанавливать свойства и многое другое.
type: docs
weight: 15
url: /ru/net/task-table-management/managing-tasks/
---
## Введение
Если вы .NET-разработчик и хотите эффективно управлять задачами в своих проектах, Aspose.Tasks for .NET предоставляет надежное решение. Это руководство проведет вас через различные аспекты управления задачами с помощью Aspose.Tasks, предлагая пошаговые инструкции и примеры кода. Независимо от того, добавляете ли вы задачи, отображаете разделенные части, перемещаете задачи под одним родительским элементом, получаете/настраиваете свойства задач, перебираете назначения задач, читаете базовые показатели задач или удаляете задачи, это руководство поможет вам.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
1. Библиотека Aspose.Tasks для .NET: убедитесь, что у вас установлена библиотека Aspose.Tasks для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/tasks/net/).
2. Каталог документов: настройте каталог, в котором будут храниться документы вашего проекта.
## Импортировать пространства имен
В свой проект .NET включите необходимые пространства имен для работы с Aspose.Tasks:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Добавление задачи в проект
```csharp
// Создать новый проект
var project = new Project();
// Добавить задачу
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Сохранить проект
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Отображение разделенных частей задачи
```csharp
// Загрузка проекта с разделенными задачами
var project = new Project(DataDir + "ViewSplitTasks.mpp");
// Доступ к задаче
var task = project.RootTask.Children.GetById(4);
// Отображение разделенных частей
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Перемещение задачи под одного родителя
```csharp
try
{
    // Загрузить проект
    var project = new Project(DataDir + "MoveTask.mpp");
    // Переместить задачу с идентификатором 5 перед задачей с идентификатором 3.
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Сохраняем измененный проект
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Получение/установка свойств задачи
```csharp
// Создать новый проект
var project = new Project();
// Добавьте задачу и задайте свойства
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Сбор и отображение свойств задачи
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Перебор назначений задачи
```csharp
// Загрузка проекта с заданиями
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Собирайте и отображайте назначения задач
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Чтение базовых показателей задачи
```csharp
// Создать новый проект
var project = new Project();
// Добавьте задачу и установите базовый план
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Отображение базовой продолжительности задачи
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Удаление задачи
```csharp
// Создать новый проект
var project = new Project();
// Добавить задачу
var task = project.RootTask.Children.Add("Task");
//Отображение количества задач до и после удаления
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Удалить задачу
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Заключение
Управление задачами в Aspose.Tasks for .NET — это простой процесс с предоставленными примерами. Независимо от того, являетесь ли вы опытным разработчиком или только начинаете, использование этих методов расширит ваши возможности управления проектами.
## Часто задаваемые вопросы
### Вопрос: Совместим ли Aspose.Tasks со всеми платформами .NET?
О: Да, Aspose.Tasks поддерживает различные платформы .NET, обеспечивая совместимость с вашей средой разработки.
### Вопрос: Как я могу получить временную лицензию на Aspose.Tasks?
 О: Вы можете получить 30-дневную временную лицензию на сайте[здесь](https://purchase.aspose.com/temporary-license/).
### Вопрос: Есть ли какие-либо ограничения при работе с разделенными задачами в Aspose.Tasks?
 О: Разделение задач — это мощная функция, подробную документацию можно найти.[здесь](https://reference.aspose.com/tasks/net/).
### Вопрос: Могу ли я настроить свойства задачи помимо показанных в примерах?
А: Абсолютно! Aspose.Tasks предоставляет широкие возможности настройки свойств задач. Проверьте документацию для получения более подробной информации.
### Вопрос: Как мне получить поддержку Aspose.Tasks?
 А: Посетите[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) за поддержку сообщества и обсуждения.