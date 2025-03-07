---
title: Обработка назначения ресурсов проекта MS в Aspose.Tasks
linktitle: Обработка назначений ресурсов в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно обрабатывать назначения ресурсов MS Project с помощью Aspose.Tasks для .NET. Это комплексное руководство содержит пошаговые инструкции для разработчиков.
weight: 11
url: /ru/net/resource-risk-analysis/resource-assignments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Обработка назначения ресурсов проекта MS в Aspose.Tasks

## Введение
В этом руководстве мы углубимся в то, как эффективно обрабатывать назначения ресурсов Microsoft Project с помощью Aspose.Tasks для .NET. Aspose.Tasks — это мощный API, который позволяет разработчикам программно манипулировать файлами Microsoft Project. Выполнив эти шаги, вы научитесь эффективно управлять назначениями ресурсов в своих приложениях .NET.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

## Импортировать пространства имен
Во-первых, вам необходимо импортировать необходимые пространства имен для использования функций Aspose.Tasks в вашем проекте .NET. Это включает в себя:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
Теперь давайте разобьем приведенный пример на несколько шагов, чтобы получить полное представление о том, как обрабатывать назначения ресурсов MS Project с помощью Aspose.Tasks.
## Шаг 1. Настройте параметры проекта и календаря
Для начала создайте новый экземпляр проекта и настройте параметры календаря проекта:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## Шаг 2. Добавьте задачу в проект
Далее добавьте новую задачу в корневую задачу проекта:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## Шаг 3. Создание назначения ресурсов и создание повременных данных
Теперь создайте новое назначение ресурса для задачи и сгенерируйте повременные данные:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## Шаг 4. Разделите задачу
Разделите задачу на несколько частей, указав даты начала и окончания:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## Шаг 5: Установите рабочий контур
Установите тип рабочего контура для назначения:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## Шаг 6: Сохраните проект
Наконец, сохраните файл проекта с внесенными изменениями:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Заключение
В заключение, обработка назначений ресурсов Microsoft Project с помощью Aspose.Tasks для .NET — это простой процесс. Следуя шагам, описанным в этом руководстве, вы сможете эффективно управлять назначениями ресурсов в своих приложениях .NET.
## Часто задаваемые вопросы
### Может ли Aspose.Tasks обрабатывать сложные структуры проектов?
Да, Aspose.Tasks предоставляет комплексные функциональные возможности для эффективной работы со сложными структурами проектов.
### Совместим ли Aspose.Tasks с различными версиями Microsoft Project?
Да, Aspose.Tasks поддерживает различные версии Microsoft Project, обеспечивая совместимость в различных средах.
### Могу ли я настроить назначения ресурсов в соответствии с конкретными требованиями?
Безусловно, Aspose.Tasks предлагает широкие возможности настройки назначения ресурсов для удовлетворения конкретных потребностей проекта.
### Поддерживает ли Aspose.Tasks экспорт данных проекта в другие форматы?
Да, Aspose.Tasks позволяет экспортировать данные проекта в различные форматы, такие как XML, PDF и HTML и другие.
### Доступна ли техническая поддержка для пользователей Aspose.Tasks?
Да, Aspose предоставляет специальную техническую поддержку через свой форум и другие каналы, чтобы помочь пользователям с любыми вопросами или проблемами.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
