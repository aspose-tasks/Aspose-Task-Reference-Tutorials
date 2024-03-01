---
title: Освоение параметров сохранения MS Project для Aspose.Tasks
linktitle: Общие параметры сохранения для Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Научитесь эффективно сохранять файлы MS Project с помощью Aspose.Tasks для .NET. Легко настройте параметры вывода для своих проектов.
type: docs
weight: 17
url: /ru/net/saving-options/general-save-options/
---
## Введение
Aspose.Tasks для .NET предлагает мощные функции для программного управления файлами Microsoft Project. В этом уроке мы углубимся в тонкости сохранения файлов MS Project с использованием различных опций, предоставляемых Aspose.Tasks. В частности, мы сосредоточимся на общих параметрах сохранения, доступных для Aspose.Tasks, что позволит вам адаптировать выходные данные к вашим конкретным требованиям.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1.  Установка Aspose.Tasks для .NET: Загрузите и установите Aspose.Tasks для .NET с сайта[ссылка для скачивания](https://releases.aspose.com/tasks/net/).
2. Базовое понимание .NET Framework: знание концепций программирования .NET будет полезным.

## Импорт пространств имен
Прежде чем углубляться в код, обязательно импортируйте необходимые пространства имен:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Шаг 1. Загрузите файл проекта
Во-первых, вам необходимо загрузить файл MS Project с помощью Aspose.Tasks:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## Шаг 2. Определите параметры сохранения
 Определите параметры сохранения в соответствии с вашими требованиями. В этом примере мы используем`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Шаг 3. Настройте столбцы представления
Вы можете настроить столбцы представления, такие как диаграмма Ганта, представление ресурсов и представление назначений. Вот как добавить столбцы к каждому:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Шаг 4. Сохраните проект с параметрами
Наконец, сохраните проект с указанными параметрами:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Заключение
Освоение общих параметров сохранения MS Project с помощью Aspose.Tasks для .NET позволит вам эффективно настраивать выходной формат в соответствии с потребностями вашего проекта.
## Часто задаваемые вопросы
### Вопрос: Совместим ли Aspose.Tasks с различными версиями файлов MS Project?
О: Да, Aspose.Tasks поддерживает различные версии файлов MS Project, обеспечивая совместимость в различных средах.
### Вопрос: Могу ли я попробовать Aspose.Tasks перед покупкой?
 О: Да, вы можете изучить Aspose.Tasks, воспользовавшись бесплатной пробной версией.[здесь](https://releases.aspose.com/).
### Вопрос: Где я могу найти документацию для Aspose.Tasks?
 О: Подробную документацию можно найти[здесь](https://reference.aspose.com/tasks/net/), предоставляющий подробные рекомендации по использованию функций Aspose.Tasks.
### Вопрос: Как я могу получить временные лицензии для Aspose.Tasks?
 О: Временные лицензии доступны для ознакомительных целей.[здесь](https://purchase.aspose.com/temporary-license/).
### Вопрос: Где я могу получить поддержку по запросам, связанным с Aspose.Tasks?
 О: Вы можете присоединиться к форуму сообщества Aspose.Tasks.[здесь](https://forum.aspose.com/c/tasks/15)получить помощь от экспертов и коллег-разработчиков.