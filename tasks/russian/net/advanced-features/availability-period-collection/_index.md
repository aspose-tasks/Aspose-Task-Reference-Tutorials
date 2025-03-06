---
title: Сбор периодов доступности в Aspose.Tasks
linktitle: Сбор периодов доступности в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как управлять периодами доступности ресурсов в Aspose.Tasks для .NET. Это пошаговое руководство поможет вам добавлять, обновлять и удалять периоды доступности, обеспечивая эффективное планирование ресурсов проекта.
weight: 18
url: /ru/net/advanced-features/availability-period-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сбор периодов доступности в Aspose.Tasks

## Введение

В этом руководстве мы рассмотрим, как работать с коллекцией периодов доступности ресурса в Aspose.Tasks для .NET. Управление периодами доступности имеет решающее значение для управления проектами, позволяя нам определять, когда ресурсы доступны для задач в рамках проекта.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1. Visual Studio: убедитесь, что в вашей системе установлена Visual Studio.
2.  Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/tasks/net/).
3. Базовые знания: Знакомство с C# и .NET framework.

## Импортировать пространства имен

Во-первых, нам нужно импортировать необходимые пространства имен в наш проект:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Давайте разобьем пример кода на несколько этапов и разберем каждую часть:

## Шаг 1. Инициализируйте проект и ресурс

```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Здесь мы загружаем файл проекта и получаем конкретный ресурс по его идентификатору.

## Шаг 2. Очистите существующие периоды доступности

```csharp
resource.AvailabilityPeriods.Clear();
```

Мы очищаем все существующие периоды доступности, связанные с ресурсом.

## Шаг 3. Добавьте периоды доступности

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Мы перебираем набор периодов доступности и добавляем их в ресурс.

## Шаг 4. Добавьте новый период доступности

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Мы создаем новый период доступности на 2013 год и вставляем его в коллекцию.

## Шаг 5. Отображение периодов доступности

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Мы распечатываем количество и подробную информацию о каждом периоде доступности, связанном с ресурсом.

## Шаг 6. Скопируйте периоды доступности на другой ресурс

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Копируем периоды доступности с одного ресурса на другой.

## Шаг 7. Обновление и удаление периодов доступности

```csharp
// Обновить доступные единицы за определенный период
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Удалить определенный период
otherResource.AvailabilityPeriods.Remove(period2013);
```

Мы обновляем доступные единицы за период и удаляем из коллекции определенные периоды.

## Заключение

В этом уроке мы узнали, как работать с коллекциями периодов доступности в Aspose.Tasks для .NET. Управление доступностью ресурсов имеет важное значение для эффективного планирования и реализации проекта.

## Часто задаваемые вопросы

### Вопрос 1. Могу ли я добавлять настраиваемые поля в периоды доступности?

О1: Нет, периоды доступности в Aspose.Tasks for .NET не поддерживают настраиваемые поля.

### Вопрос 2. Связаны ли периоды доступности с конкретными задачами?

О2: Нет, периоды доступности связаны с ресурсами и определяют, когда они доступны для задач в целом.

### Вопрос 3. Могу ли я импортировать периоды доступности из внешних источников?

О3: Да, вы можете импортировать периоды доступности из различных источников данных с помощью API Aspose.Tasks для .NET.

### Вопрос 4. Как справиться с перекрывающимися периодами доступности?

О4: Aspose.Tasks для .NET не предоставляет встроенных механизмов для обработки перекрывающихся периодов. Для управления такими сценариями может потребоваться реализация специальной логики.

### Вопрос 5. Существует ли ограничение на количество периодов доступности, которые может иметь ресурс?

A5. Предопределенного ограничения на количество периодов доступности, которое может иметь ресурс, не существует, но при большом количестве периодов производительность может снижаться.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
