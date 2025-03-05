---
title: Сбор назначений ресурсов в Aspose.Tasks
linktitle: Сбор назначений ресурсов в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как управлять назначениями ресурсов в Microsoft Project с помощью Aspose.Tasks для .NET. Пошаговое руководство с примерами кода.
type: docs
weight: 12
url: /ru/net/resource-risk-analysis/resource-assignment-collection/
---
## Введение
Добро пожаловать в это подробное руководство по управлению назначением ресурсов в Microsoft Project с использованием Aspose.Tasks для .NET. В этом руководстве мы шаг за шагом углубимся в этот процесс, чтобы у вас было четкое понимание того, как эффективно управлять назначениями ресурсов. Независимо от того, являетесь ли вы опытным разработчиком или только начинаете, это руководство проведет вас через все, что вам нужно знать.
## Предварительные условия
Прежде чем мы углубимся в код, убедитесь, что у вас настроено следующее:
1.  Установлен Aspose.Tasks для .NET: убедитесь, что в вашей среде разработки установлен Aspose.Tasks для .NET. Если нет, вы можете скачать его с[здесь](https://releases.aspose.com/tasks/net/).
2. Базовые знания C#. В этом руководстве предполагается, что у вас есть базовые знания языка программирования C#.
3. Файл Microsoft Project: подготовьте файл Microsoft Project для тестирования. Если у вас его нет, вы можете создать образец файла.

## Импортировать пространства имен
Сначала давайте импортируем необходимые пространства имен:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Шаг 1. Загрузите файл проекта
Начните с загрузки файла Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Шаг 2. Добавьте задачу и ресурс
Теперь добавим в проект задачу и ресурс:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Шаг 3. Назначьте ресурс задаче
Далее мы назначим ресурс задаче:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Шаг 4. Работа с различными типами назначений
Вы также можете работать с назначениями, включающими единицы измерения или затраты:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Установите свойства для назначений с единицами измерения и стоимостью аналогично тому, как показано в шаге 3.
```
## Шаг 5. Распечатайте задания
Распечатайте задания по проекту:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Распечатать детали задания
}
```
## Шаг 6. Получение назначения по UID
Вы можете получить задания по UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Шаг 7. Проверьте статус «только для чтения»
Убедитесь, что коллекция назначений ресурсов доступна только для чтения:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Шаг 8. Преобразование коллекции в список и повторение
Преобразуйте коллекцию в список и выполните итерацию по нему:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Заключение
Поздравляем! Вы узнали, как управлять назначениями ресурсов в Microsoft Project с помощью Aspose.Tasks для .NET. Следуя этим шагам, вы сможете эффективно манипулировать задачами и ресурсами, упрощая управление проектами.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks для .NET с разными версиями файлов Microsoft Project?
О: Да, Aspose.Tasks для .NET поддерживает различные версии файлов Microsoft Project, включая форматы MPP, MPT и XML.
### Вопрос: Доступна ли пробная версия перед покупкой Aspose.Tasks для .NET?
 О: Да, вы можете получить бесплатную пробную версию Aspose.Tasks для .NET на сайте[здесь](https://releases.aspose.com/).
### Вопрос: Как я могу получить поддержку, если у меня возникнут какие-либо проблемы при использовании Aspose.Tasks для .NET?
 О: Вы можете обратиться за поддержкой на форум Aspose.Tasks.[здесь](https://forum.aspose.com/c/tasks/15).
### Вопрос: Могу ли я использовать временные лицензии для Aspose.Tasks для .NET?
 О: Да, временные лицензии доступны для ознакомительных целей. Вы можете получить один из[здесь](https://purchase.aspose.com/temporary-license/).
### Вопрос: Где я могу приобрести полную лицензию на Aspose.Tasks для .NET?
 О: Вы можете приобрести полную лицензию в интернет-магазине Aspose.[здесь](https://purchase.aspose.com/buy).