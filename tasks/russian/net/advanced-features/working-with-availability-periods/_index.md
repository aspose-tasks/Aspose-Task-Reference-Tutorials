---
date: 2026-04-06
description: Узнайте, как добавить ресурс в проект и установить периоды доступности
  ресурса с помощью Aspose.Tasks для .NET. Пошаговое руководство по управлению календарями
  ресурсов.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Работа с периодами доступности в Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Добавить ресурс в проект и установить доступность в Aspose.Tasks
url: /ru/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить ресурс в проект и установить доступность в Aspose.Tasks

## Введение

В этом руководстве вы узнаете **как добавить ресурс в проект** и затем определить периоды его доступности, используя библиотеку Aspose.Tasks для .NET. Управление календарями ресурсов необходимо для реалистичных графиков проекта, а ниже приведённые шаги проведут вас через весь процесс — от создания экземпляра проекта до вывода деталей каждого периода.

## Быстрые ответы
- **Какова основная цель?** Добавить ресурс в проект и настроить его периоды доступности.  
- **Какая библиотека требуется?** Aspose.Tasks for .NET.  
- **Нужна ли лицензия для эксплуатации?** Да, требуется коммерческая лицензия.  
- **Поддерживаемые версии .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Время реализации?** Обычно менее 15 минут для базовых сценариев.

## Что такое «add resource to project»?

Добавление ресурса в проект создаёт заполнитель для человека, оборудования или материала, который может быть назначен задачам. После создания ресурса вы можете **set resource availability**, определить его рабочий календарь и позволить планировщику учитывать эти ограничения.

## Почему настраивать график работы и периоды доступности?

- **Точное планирование:** Задачи планируются только тогда, когда ресурс действительно свободен.  
- **Контроль затрат:** Единицы доступности отражают неполный рабочий день, помогая правильно рассчитывать затраты на труд.  
- **Уравнивание ресурсов:** Движок может автоматически уравнивать переизбытки, когда знает календарь каждого ресурса.

## Требования

1. Visual Studio (или любой совместимый с .NET IDE).  
2. Aspose.Tasks for .NET – загрузить с [здесь](https://releases.aspose.com/tasks/net/).  
3. Базовые знания C#.

## Импорт пространств имён

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Как добавить ресурс в проект?

### Шаг 1: Создать новый экземпляр `Project`

```csharp
var project = new Project();
```

Этот объект представляет весь файл проекта в памяти.

### Шаг 2: Добавить ресурс в проект

```csharp
var resource = project.Resources.Add("Work Resource");
```

Вызов создаёт **resource** с именем *Work Resource*, который позже можно привязать к задачам.

### Шаг 3: Определить периоды доступности

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` — вспомогательный метод (реализация не показана), который возвращает коллекцию объектов `AvailabilityPeriod`. Каждый период указывает дату начала, дату окончания и единицы (процент полной занятости), в которых ресурс доступен.

### Шаг 4: Добавить периоды к ресурсу

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Здесь мы **set resource availability**, проходя по коллекции и добавляя каждый период в календарь ресурса.

### Шаг 5: Показать детали доступности

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Вывод в консоль позволяет проверить, что периоды были сохранены корректно.

## Распространённые ошибки и советы

- **Точность даты:** `AvailableFrom` и `AvailableTo` являются значениями `DateTime`; убедитесь, что они установлены на полночь, если нужны целодневные периоды.  
- **Диапазон единиц:** Допустимые значения от 0‑100 %; значения вне этого диапазона вызовут исключение.  
- **Перекрывающиеся периоды:** Перекрывающиеся периоды автоматически объединяются, но лучше сохранять их раздельными.

## Часто задаваемые вопросы

### Q1: Могу ли я использовать Aspose.Tasks for .NET в коммерческих проектах?
A1: Да, Aspose.Tasks for .NET можно использовать в коммерческих проектах. Вы можете приобрести лицензию [здесь](https://purchase.aspose.com/buy).

### Q2: Есть ли бесплатная пробная версия Aspose.Tasks for .NET?
A2: Да, вы можете получить бесплатную пробную версию Aspose.Tasks for .NET [здесь](https://releases.aspose.com/).

### Q3: Где я могу найти документацию по Aspose.Tasks for .NET?
A3: Вы можете найти документацию [здесь](https://reference.aspose.com/tasks/net/).

### Q4: Как я могу получить поддержку для Aspose.Tasks for .NET?
A4: Вы можете получить поддержку на форуме сообщества [здесь](https://forum.aspose.com/c/tasks/15).

### Q5: Предлагаете ли вы временные лицензии для Aspose.Tasks for .NET?
A5: Да, временные лицензии доступны [здесь](https://purchase.aspose.com/temporary-license/).

---

**Последнее обновление:** 2026-04-06  
**Тестировано с:** Aspose.Tasks for .NET (latest stable release)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}