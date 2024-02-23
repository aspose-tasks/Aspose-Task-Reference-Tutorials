---
title: Эффективно управляйте фильтрами проектов MS с помощью Aspose.Tasks
linktitle: Управление коллекцией фильтров в Aspose.Задачи
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно управлять коллекциями фильтров MS Project с помощью Aspose.Tasks для .NET.
type: docs
weight: 17
url: /ru/net/tasks-project-management/filter-collection/
---
## Введение
В этом руководстве мы рассмотрим, как эффективно управлять коллекциями фильтров MS Project с помощью Aspose.Tasks для .NET. Управление фильтрами имеет решающее значение для эффективной организации и анализа данных проекта. Aspose.Tasks обеспечивает надежную функциональность для беспрепятственной обработки фильтров задач и ресурсов.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1.  Установка Aspose.Tasks для .NET: Загрузите и установите Aspose.Tasks для .NET с сайта[ссылка для скачивания](https://releases.aspose.com/tasks/net/).
2. Доступ к среде разработки .NET. Убедитесь, что у вас настроена среда разработки .NET для работы с Aspose.Tasks.

## Импортировать пространства имен
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Шаг 1. Загрузите файл проекта
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadFilterDefinitionData.mpp");
```
## Шаг 2. Перебор фильтров задач
```csharp
Console.WriteLine("Print task filters of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Filters Count: " + project.TaskFilters.Count);
foreach (var filter in project.TaskFilters)
{
    Console.WriteLine("All Tasks: " + filter.Name);
    Console.WriteLine("Task Item: " + filter.FilterType);
    Console.WriteLine("Task Filters Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Task filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
    Console.WriteLine();
}
```
## Шаг 3. Перебор фильтров ресурсов
```csharp
Console.WriteLine("Project.ResourceFilters count: " + project.ResourceFilters.Count);
foreach (var filter in project.ResourceFilters)
{
    Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + filter.FilterType);
    Console.WriteLine("Resource filter ShowInMenu" + filter.ShowInMenu);
    Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
}
```
## Шаг 4. Очистите и скопируйте фильтры
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Очистить фильтры других проектов
otherProject.TaskFilters.Clear();
// Копировать фильтры в другой проект
var filters = new Filter[project.TaskFilters.Count];
project.TaskFilters.CopyTo(filters, 0);
foreach (var filter in filters)
{
    otherProject.TaskFilters.Add(filter);
}
```
## Шаг 5. Добавьте настраиваемый фильтр задач
```csharp
// Добавить собственный фильтр задач
var customFilter = new Filter();
customFilter.Name = "Custom Filter";
customFilter.ShowInMenu = true;
customFilter.ShowRelatedSummaryRows = true;
if (!otherProject.TaskFilters.Contains(customFilter))
{
    if (!otherProject.TaskFilters.IsReadOnly)
    {
        otherProject.TaskFilters.Add(customFilter);
    }
}
```
## Шаг 6. Удалите все фильтры.
```csharp
// Удалить все фильтры
List<Filter> filtersToDelete = otherProject.TaskFilters.ToList();
foreach (var filter in filtersToDelete)
{
    otherProject.TaskFilters.Remove(filter);
}
```
Следуя этим шагам, вы сможете эффективно управлять коллекциями фильтров MS Project с помощью Aspose.Tasks для .NET.

## Заключение
Эффективное управление фильтрами в коллекциях MS Project имеет решающее значение для организации и анализа данных проекта. Aspose.Tasks для .NET предоставляет комплексные функциональные возможности для беспрепятственной обработки фильтров задач и ресурсов, позволяя разработчикам эффективно оптимизировать задачи управления проектами.
## Часто задаваемые вопросы
### Вопрос: Может ли Aspose.Tasks обрабатывать сложные структуры проектов?
О: Aspose.Tasks предлагает надежные функции для работы с различными структурами проектов, в том числе сложными, обеспечивая комплексные возможности управления проектами.
### Вопрос: Совместим ли Aspose.Tasks с различными версиями файлов MS Project?
О: Да, Aspose.Tasks поддерживает широкий спектр форматов файлов MS Project, обеспечивая совместимость различных версий.
### Вопрос: Могу ли я настроить фильтры в соответствии с требованиями конкретного проекта?
А: Абсолютно! Aspose.Tasks позволяет разработчикам создавать собственные фильтры, адаптированные к уникальным потребностям проекта, повышая гибкость и эффективность.
### Вопрос: Предоставляет ли Aspose.Tasks документацию и ресурсы поддержки?
О: Да, Aspose.Tasks предлагает обширную документацию, учебные пособия и специальный форум поддержки, помогающий разработчикам на каждом этапе реализации проекта.
### Вопрос: Доступна ли пробная версия для Aspose.Tasks?
О: Да, разработчики могут получить доступ к бесплатной пробной версии Aspose.Tasks, чтобы изучить ее возможности, прежде чем принимать решение о покупке.