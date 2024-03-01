---
title: Расширенные операции AND в Aspose.Tasks
linktitle: Расширенные операции AND в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как выполнять расширенные операции И в Aspose.Tasks для .NET, чтобы эффективно фильтровать задачи проекта по множеству критериев.
type: docs
weight: 10
url: /ru/net/advanced-features/advanced-and-operation/
---
## Введение

 В этом уроке мы углубимся в расширенную операцию И в Aspose.Tasks для .NET, мощном инструменте для управления задачами и проектами. Мы рассмотрим, как фильтровать задачи проекта на основе нескольких условий, используя`Util.And` сорт.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1. Базовые знания языка программирования C#.
2.  Установлен Aspose.Tasks для .NET. Если нет, вы можете скачать его с[здесь](https://releases.aspose.com/tasks/net/).
3. Интегрированная среда разработки (IDE), такая как Visual Studio.

## Импортировать пространства имен

Сначала давайте импортируем необходимые пространства имен в наш проект C#:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## Шаг 1. Инициализируйте проект и соберите задачи

Начните с инициализации нового проекта Aspose.Tasks и сбора в нем всех задач:

```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Шаг 2. Определите условия фильтра

Далее определите условия фильтра. В этом примере мы создадим два условия: одно для фильтрации суммарных задач, а другое — для фильтрации ненулевых задач:

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Шаг 3. Объедините условия с помощью операции AND

 Теперь объедините условия, используя`Util.And` класс для создания составного условия:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Шаг 4. Примените условие и отфильтруйте задачи

Примените комбинированное условие к собранным задачам и соответствующим образом отфильтруйте их:

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Шаг 5. Вывод отфильтрованных задач

Наконец, выведите отфильтрованные задачи:

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Дополнительную обработку можно выполнить здесь.
}
```

## Заключение

 В этом руководстве мы узнали, как выполнять расширенные операции И в Aspose.Tasks для .NET. Комбинируя условия с помощью`Util.And`class, мы можем эффективно фильтровать задачи по множеству критериев.

## Часто задаваемые вопросы

### Вопрос 1. Что такое Aspose.Tasks для .NET?

О: Aspose.Tasks for .NET — это надежный API, который позволяет разработчикам программно манипулировать файлами Microsoft Project в приложениях .NET.

### Вопрос 2. Могу ли я применить более двух условий с помощью Util.And?

О: Да, Util.And можно использовать для объединения любого количества условий для создания сложных критериев фильтрации.

### Вопрос 3. Доступна ли бесплатная пробная версия Aspose.Tasks для .NET?

 О: Да, вы можете загрузить бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).

### Вопрос 4. Где я могу найти документацию по Aspose.Tasks для .NET?

 О: Вы можете найти документацию[здесь](https://reference.aspose.com/tasks/net/).

### Вопрос 5: Как я могу получить поддержку Aspose.Tasks для .NET?

О: Вы можете получить поддержку на форуме сообщества Aspose.Tasks.[здесь](https://forum.aspose.com/c/tasks/15).