---
title: Освоение данных проекта с помощью Aspose.Tasks
linktitle: Работа с данными проекта в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как манипулировать данными Microsoft Project с помощью Aspose.Tasks в .NET. С легкостью создавайте задачи, добавляйте ресурсы и сохраняйте проекты.
type: docs
weight: 16
url: /ru/net/project-management-integration/project-data/
---
## Введение
В этом уроке мы рассмотрим, как работать с данными Microsoft Project с помощью библиотеки Aspose.Tasks для .NET. Aspose.Tasks предоставляет мощные функции для управления файлами проектов, включая создание задач, добавление ресурсов, настройку свойств и сохранение проектов в различных форматах.
## Предварительные условия
Прежде чем приступить к работе, убедитесь, что у вас есть следующее:
1.  Установка библиотеки Aspose.Tasks: Загрузите и установите библиотеку Aspose.Tasks с сайта[здесь](https://releases.aspose.com/tasks/net/).
2. Среда разработки: убедитесь, что у вас настроена среда разработки .NET.
3. Базовые знания C#: Знакомство с языком программирования C# будет преимуществом.

## Импортировать пространства имен
Прежде чем работать с Aspose.Tasks, импортируйте в свой проект необходимые пространства имен:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Шаг 1. Инициализация объекта проекта
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Эта строка инициализирует новый экземпляр`Project` класс, который представляет файл Microsoft Project.
## Шаг 2. Установите свойства проекта
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Эти строки демонстрируют, как настроить свойства проекта, такие как формат работы и режим создания задач.
## Шаг 3. Добавление задач
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Здесь к корневой задаче проекта добавляется новая задача с именем «Задача 1».
## Шаг 4. Настройка свойств задачи
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Эти строки устанавливают дату начала, продолжительность и дату окончания «Задачи 1».
## Шаг 5: Добавление ресурсов
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
В этой части показано, как добавить рабочий ресурс в проект.
## Шаг 6. Назначение ресурсов задачам
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
В этих строках показано, как назначить ранее добавленный трудовой ресурс «Задаче 1» с конкретными датами начала, работы и окончания.
## Шаг 7: Сохранение проекта
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Наконец, проект сохраняется в формате файла Microsoft Project XML.

## Заключение
В этом руководстве мы научились работать с данными Microsoft Project с помощью библиотеки Aspose.Tasks в .NET. Следуя пошаговому руководству, вы сможете манипулировать файлами проекта, добавлять задачи, ресурсы, назначать ресурсы задачам и сохранять проекты в различных форматах.
## Часто задаваемые вопросы
### Вопрос: Может ли Aspose.Tasks обрабатывать сложные структуры проектов?
О: Да, Aspose.Tasks обеспечивает комплексную поддержку сложных структур проектов, позволяя вам эффективно управлять задачами, ресурсами и заданиями.
### Вопрос: Совместим ли Aspose.Tasks с различными версиями Microsoft Project?
О: Aspose.Tasks поддерживает широкий спектр версий Microsoft Project, обеспечивая совместимость в различных средах.
### Вопрос: Могу ли я интегрировать Aspose.Tasks с другими библиотеками .NET?
О: Конечно, Aspose.Tasks легко интегрируется с другими библиотеками .NET, обеспечивая гибкость в ваших проектах разработки.
### Вопрос: Предлагает ли Aspose.Tasks поддержку алгоритмов планирования проектов?
О: Да, Aspose.Tasks включает в себя расширенные алгоритмы планирования, которые помогут вам оптимизировать сроки проекта и использование ресурсов.
### Вопрос: Существует ли форум сообщества для пользователей Aspose.Tasks?
 О: Да, вы можете найти полезные ресурсы и пообщаться с другими пользователями Aspose.Tasks на[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).