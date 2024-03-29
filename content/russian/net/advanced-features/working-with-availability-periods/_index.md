---
title: Работа с периодами доступности в Aspose.Tasks
linktitle: Работа с периодами доступности в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно управлять периодами доступности ресурсов с помощью Aspose.Tasks для .NET. В этом руководстве представлено пошаговое руководство по работе с периодами доступности в проектах .NET.
type: docs
weight: 17
url: /ru/net/advanced-features/working-with-availability-periods/
---
## Введение

В этом руководстве мы рассмотрим, как работать с периодами доступности в Aspose.Tasks для .NET. Периоды доступности имеют решающее значение для эффективного управления ресурсами в сценариях управления проектами. Мы проведем вас через этот процесс шаг за шагом.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

1. Visual Studio: установите Visual Studio или любую другую интегрированную среду разработки для разработки .NET.
2.  Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/tasks/net/).
3. Базовое понимание программирования на C#. Знакомство с основами языка программирования C# будет полезным.

## Импортировать пространства имен

Прежде чем углубляться в код, обязательно импортируйте необходимые пространства имен:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Давайте разобьем пример кода на несколько шагов:

## Шаг 1. Создайте новый экземпляр проекта.

```csharp
var project = new Project();
```

Эта строка инициализирует новый экземпляр класса Project, который представляет проект в Aspose.Tasks.

## Шаг 2. Добавьте ресурс

```csharp
var resource = project.Resources.Add("Work Resource");
```

Здесь мы добавляем в проект новый ресурс с именем «Рабочий ресурс».

## Шаг 3. Определите периоды доступности

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 Мы называем`GetPeriods()` метод для получения коллекции периодов доступности.

## Шаг 4. Добавьте периоды доступности к ресурсу

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Мы перебираем коллекцию периодов доступности, полученную на предыдущем шаге, и добавляем их в ресурс.

## Шаг 5. Отображение сведений о периоде доступности

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Наконец, мы просматриваем периоды доступности, связанные с ресурсом, и печатаем их сведения, включая дату начала, дату окончания и доступные единицы.

## Заключение

В этом уроке мы узнали, как работать с периодами доступности в Aspose.Tasks для .NET. Следуя пошаговому руководству, вы сможете эффективно управлять доступностью ресурсов в приложениях для управления проектами.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.Tasks для .NET в коммерческих проектах?

 О1: Да, Aspose.Tasks для .NET можно использовать в коммерческих проектах. Вы можете приобрести лицензию[здесь](https://purchase.aspose.com/buy).

### Вопрос 2. Доступна ли бесплатная пробная версия Aspose.Tasks для .NET?

О2: Да, вы можете получить бесплатную пробную версию Aspose.Tasks для .NET.[здесь](https://releases.aspose.com/).

### Вопрос 3. Где я могу найти документацию по Aspose.Tasks для .NET?

 A3: Вы можете найти документацию[здесь](https://reference.aspose.com/tasks/net/).

### Вопрос 4: Как я могу получить поддержку Aspose.Tasks для .NET?

 A4: Вы можете получить поддержку на форуме сообщества.[здесь](https://forum.aspose.com/c/tasks/15).

### Вопрос 5: Предлагаете ли вы временные лицензии на Aspose.Tasks для .NET?

 О5: Да, доступны временные лицензии.[здесь](https://purchase.aspose.com/temporary-license/).