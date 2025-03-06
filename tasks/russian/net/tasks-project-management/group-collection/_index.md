---
title: Управление коллекциями проектов в Aspose.Tasks
linktitle: Управление коллекцией групп в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно управлять коллекциями MS Project с помощью Aspose.Tasks для .NET. Следуйте нашему пошаговому руководству.
weight: 26
url: /ru/net/tasks-project-management/group-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Управление коллекциями проектов в Aspose.Tasks

## Введение
В этом уроке мы рассмотрим, как управлять групповыми коллекциями MS Project с помощью Aspose.Tasks для .NET. Управление групповыми коллекциями имеет решающее значение для эффективной организации и управления задачами и ресурсами в рамках вашего проекта.
## Предварительные условия
Прежде чем продолжить работу с этим руководством, убедитесь, что у вас есть следующие предварительные условия:
1.  Библиотека Aspose.Tasks для .NET: загрузите и установите библиотеку Aspose.Tasks для .NET из[ссылка для скачивания](https://releases.aspose.com/tasks/net/).
2. Базовые знания C#. Ознакомьтесь с основами языка программирования C#, поскольку в этом руководстве рассматривается программирование на C#.
3. Среда разработки: настройте среду разработки, например Visual Studio или любую другую среду разработки, поддерживающую разработку .NET.

## Импортировать пространства имен
Сначала давайте импортируем необходимые пространства имен для работы с функциями Aspose.Tasks в нашем коде C#.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Шаг 1. Загрузите проект
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Этот шаг включает загрузку файла MS Project в объект проекта Aspose.Tasks, что позволяет нам выполнять над ним операции.
## Шаг 2. Перебор групп задач
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Здесь мы перебираем группы задач в проекте, печатая такие детали, как индекс, имя и видимость, в меню для каждой группы.
## Шаг 3. Перебор групп ресурсов
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
Аналогично, на этом шаге происходит перебор групп ресурсов, отображая их индекс, имя и видимость в меню.
## Шаг 4. Очистите и скопируйте группы в другой проект
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Очистить группы других проектов
otherProject.TaskGroups.Clear();
// Копировать группы в другой проект
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Здесь мы очищаем группы другого проекта, а затем копируем в него группы из исходного проекта.
## Шаг 5. Добавьте пользовательскую группу задач
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
На этом этапе мы создаем пользовательскую группу задач и добавляем ее в другой проект, если она еще не существует.
## Шаг 6: Удалить все группы
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Наконец, мы удаляем все группы из другого проекта.

## Заключение
Управление групповыми коллекциями MS Project в Aspose.Tasks for .NET необходимо для эффективной организации данных проекта и управления ими. Следуя шагам, описанным в этом руководстве, вы сможете эффективно управлять группами задач и ресурсов в своих проектах, улучшая общее управление проектами.
## Часто задаваемые вопросы
### Совместим ли Aspose.Tasks для .NET со всеми версиями MS Project?
Aspose.Tasks для .NET поддерживает различные версии Microsoft Project, включая 2003, 2007, 2010, 2013, 2016 и 2019.
### Могу ли я настроить свойства группы с помощью Aspose.Tasks для .NET?
Да, вы можете настроить свойства группы, такие как имя и видимость, с помощью Aspose.Tasks для .NET.
### Обеспечивает ли Aspose.Tasks для .NET кроссплатформенную совместимость?
Aspose.Tasks для .NET в первую очередь ориентирован на платформу .NET, но его можно использовать в кроссплатформенных сценариях с .NET Core и .NET Standard.
### Как я могу получить поддержку Aspose.Tasks для .NET?
 Вы можете получить поддержку Aspose.Tasks для .NET через[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Доступна ли пробная версия Aspose.Tasks для .NET?
 Да, вы можете загрузить бесплатную пробную версию Aspose.Tasks для .NET с сайта[Веб-сайт](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
