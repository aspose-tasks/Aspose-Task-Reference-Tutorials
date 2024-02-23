---
title: Манипулирование критериями группы проектов MS в Aspose.Tasks
linktitle: Критерии группы в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как программно манипулировать файлами MS Project в .NET с помощью Aspose.Tasks. Пошаговые примеры получения информации о группах задач и критериях.
type: docs
weight: 27
url: /ru/net/tasks-project-management/group-criteria/
---
## Введение
Aspose.Tasks для .NET — это мощный API, который упрощает работу с файлами Microsoft Project в ваших .NET-приложениях. Независимо от того, разрабатываете ли вы программное обеспечение для управления проектами или вам необходимо программно манипулировать данными проекта, Aspose.Tasks предлагает полный набор функций для удовлетворения ваших потребностей.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
### 1. Знание C# и .NET Framework.
Знакомство с языком программирования C# и .NET Framework необходимо для понимания и реализации примеров, представленных в этом руководстве.
### 2. Установка Aspose.Tasks для .NET.
 Убедитесь, что в вашей среде разработки установлен Aspose.Tasks for .NET. Вы можете скачать библиотеку с[здесь](https://releases.aspose.com/tasks/net/) и следуйте инструкциям по установке.
### 3. Интегрированная среда разработки (IDE).
Установите в своей системе интегрированную среду разработки, например Visual Studio, для написания и выполнения кода C#.

## Импортировать пространства имен
Для начала импортируйте необходимые пространства имен в свой код C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Шаг 1. Загрузите файл Microsoft Project
Сначала укажите путь к файлу Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 Заменять`"Your Document Directory"` с путем к файлу вашего проекта.
## Шаг 2. Получение информации о группах задач
Затем получите информацию о группах задач в проекте:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Этот фрагмент кода выводит общее количество групп задач, извлекает вторую группу задач, ее имя и количество содержащихся в ней критериев.
## Шаг 3. Получение информации о критериях целевой группы
Теперь давайте углубимся в детали конкретного критерия внутри группы задач:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
В этом сегменте отображаются различные свойства критерия, такие как его индекс, поле, информация о группировке, цвет ячейки, цвет шрифта, интервал группировки и начальная точка.
## Шаг 4. Получение информации о шрифте критерия
Наконец, получите детали критерия, связанные со шрифтом:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
На этом шаге распечатывается имя шрифта, размер, стиль и сортировка критерия по возрастанию или убыванию.

## Заключение
В этом руководстве мы рассмотрели, как использовать Aspose.Tasks для .NET для получения информации о группах задач и критериях из файла Microsoft Project. Следуя пошаговому руководству, вы сможете эффективно работать с данными проекта программно в своих приложениях .NET.
## Часто задаваемые вопросы
### Может ли Aspose.Tasks обрабатывать большие файлы Microsoft Project?
Aspose.Tasks оптимизирован для эффективной обработки больших файлов проектов, обеспечивая высокую производительность и надежность.
### Совместим ли Aspose.Tasks со всеми версиями Microsoft Project?
Да, Aspose.Tasks поддерживает различные версии Microsoft Project, обеспечивая совместимость файлов разных форматов.
### Могу ли я манипулировать данными проекта с помощью Aspose.Tasks?
Конечно, Aspose.Tasks предоставляет обширные функциональные возможности для управления данными проекта, включая задачи, ресурсы, календари и многое другое.
### Предлагает ли Aspose.Tasks поддержку различных платформ .NET?
Да, Aspose.Tasks поддерживает несколько платформ .NET, включая .NET Framework, .NET Core и .NET Standard.
### Есть ли форум сообщества Aspose.Tasks, где я могу обратиться за помощью?
 Да, вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) задавать вопросы, делиться знаниями и сотрудничать с другими пользователями.