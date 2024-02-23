---
title: Управляйте критериями группы проектов MS с помощью Aspose.Tasks
linktitle: Управление коллекцией групповых критериев в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как управлять коллекцией групповых критериев MS Project с помощью Aspose.Tasks для .NET. Пошаговое руководство для разработчиков.
type: docs
weight: 28
url: /ru/net/tasks-project-management/group-criterion-collection/
---
## Введение
Aspose.Tasks для .NET — это мощный API, который позволяет разработчикам программно работать с файлами Microsoft Project. В этом уроке мы рассмотрим, как управлять коллекцией групповых критериев в MS Project с помощью Aspose.Tasks.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1.  Aspose.Tasks для .NET: убедитесь, что в вашем проекте .NET установлена библиотека Aspose.Tasks. Вы можете скачать его с[здесь](https://releases.aspose.com/tasks/net/).

2. Файл Microsoft Project: подготовьте файл Microsoft Project (MPP), готовый к работе.

## Импортировать пространства имен

Во-первых, вам необходимо импортировать необходимые пространства имен в ваш код C#. Этот шаг имеет решающее значение для доступа к функциям, предоставляемым Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Шаг 1. Загрузите файл проекта

 Инициализировать`Project` объект, загрузив файл MPP. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Шаг 2. Критерии группы доступа

Извлеките группу из проекта и получите доступ к ее критериям.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Шаг 3. Перебор критериев группы

Прокрутите каждый критерий в группе и отобразите его свойства.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Шаг 4: Очистите критерии группы

Очистите существующие критерии группы, если они не доступны только для чтения.

```csharp
group.GroupCriteria.Clear();
```

## Шаг 5: Добавьте новый критерий

Создайте новый групповой критерий и добавьте его в группу.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Шаг 6. Скопируйте критерии в другую группу

Скопируйте критерии из одной группы в другую.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Заключение

В этом уроке мы узнали, как управлять коллекцией проектов MS Project Group Criterion с помощью Aspose.Tasks для .NET. Выполнив эти шаги, вы сможете эффективно программно манипулировать критериями группы в файлах Microsoft Project.

## Часто задаваемые вопросы

### Вопрос 1. Совместим ли Aspose.Tasks со всеми версиями Microsoft Project?

О: Да, Aspose.Tasks поддерживает файлы Microsoft Project различных версий, включая 2003, 2007, 2010, 2013 и 2016.

### Вопрос 2. Могу ли я применить несколько критериев к одной группе?

О: Конечно, вы можете добавить в группу несколько критериев, просматривая каждый из них и добавляя их соответствующим образом.

### В3: Доступна ли пробная версия для Aspose.Tasks?

 О: Да, вы можете получить бесплатную пробную версию Aspose.Tasks на сайте[здесь](https://releases.aspose.com/).

### Вопрос 4: Где я могу найти документацию для Aspose.Tasks?

 О: Вы можете обратиться к документации[здесь](https://reference.aspose.com/tasks/net/).

### В5: Как я могу получить поддержку, если у меня возникнут какие-либо проблемы?

 О: Если у вас есть какие-либо вопросы или вы столкнулись с какими-либо проблемами, вы можете обратиться за поддержкой на форум Aspose.Tasks.[здесь](https://forum.aspose.com/c/tasks/15).