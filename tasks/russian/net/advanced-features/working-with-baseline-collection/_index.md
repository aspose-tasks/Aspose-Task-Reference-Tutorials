---
title: Работа с базовой коллекцией в Aspose.Tasks
linktitle: Работа с базовой коллекцией в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно управлять базовыми показателями в Aspose.Tasks для .NET. Следуйте нашему подробному руководству для получения пошаговых инструкций.
weight: 20
url: /ru/net/advanced-features/working-with-baseline-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Работа с базовой коллекцией в Aspose.Tasks

## Введение

Aspose.Tasks for .NET — это мощная библиотека, которая позволяет разработчикам беспрепятственно работать с файлами Microsoft Project в своих .NET-приложениях. Среди множества функций он обеспечивает надежную поддержку управления базовыми показателями в проектах. Базовые показатели важны для управления проектами, поскольку они позволяют сравнивать исходный план проекта с текущим статусом, что позволяет лучше отслеживать и анализировать ход проекта.

## Предварительные условия

Прежде чем мы углубимся в работу с базовыми коллекциями в Aspose.Tasks, убедитесь, что у вас есть следующие предварительные условия:

1. Visual Studio: установите интегрированную среду разработки Visual Studio в вашей системе.
2.  Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks для .NET из[ссылка для скачивания](https://releases.aspose.com/tasks/net/).
3. Базовое понимание C#: познакомьтесь с языком программирования C#.
4. Файл Microsoft Project: подготовьте файл Microsoft Project (.mpp) для тестирования.

## Импортировать пространства имен

Чтобы начать работать с базовыми коллекциями в Aspose.Tasks, вам необходимо импортировать следующие пространства имен:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Теперь давайте разобьем каждый пример на несколько этапов:

## Шаг 1. Загрузите файл проекта

Сначала загрузите файл Microsoft Project с помощью Aspose.Tasks:

```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Шаг 2: Получите ресурс

Затем извлеките нужный ресурс из проекта:

```csharp
var resource = project.Resources.GetByUid(1);
```

## Шаг 3. Отображение базовой информации

Теперь отобразите информацию о базовых показателях, связанных с ресурсом:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Шаг 4. Перебор базовых показателей

Переберите все базовые показатели, связанные с ресурсом, и выведите соответствующую информацию:

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Шаг 5. Удаление базовых показателей

Удалите все базовые показатели, связанные с ресурсом:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## Заключение

В этом руководстве мы рассмотрели, как работать с базовыми коллекциями в Aspose.Tasks для .NET. Следуя пошаговому руководству, вы сможете легко управлять базовыми показателями в своих приложениях .NET, что позволит эффективно отслеживать и анализировать проекты.

## Часто задаваемые вопросы

### Вопрос 1: Может ли Aspose.Tasks обрабатывать большие файлы проектов?

О1: Да, Aspose.Tasks оптимизирован для эффективной обработки больших файлов проектов, обеспечивая плавную работу.

### Вопрос 2. Совместим ли Aspose.Tasks со всеми версиями Microsoft Project?

О2: Aspose.Tasks поддерживает различные версии Microsoft Project, обеспечивая совместимость в различных средах.

### Вопрос 3. Могу ли я настроить базовые показатели в Aspose.Tasks?

О3: Да, вы можете настроить базовые показатели в соответствии с требованиями вашего проекта, используя Aspose.Tasks для .NET.

### Вопрос 4. Предлагает ли Aspose.Tasks поддержку облачных платформ?

О4: Да, Aspose.Tasks обеспечивает поддержку интеграции с популярными облачными платформами, обеспечивая гибкость при развертывании.

### Вопрос 5: Существует ли форум сообщества, на котором пользователи Aspose.Tasks могут обращаться за помощью и делиться знаниями?

 A5: Да, вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) взаимодействовать с сообществом и получать помощь от экспертов.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
