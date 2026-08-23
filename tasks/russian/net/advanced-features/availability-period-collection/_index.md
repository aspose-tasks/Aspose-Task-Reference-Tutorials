---
date: 2026-03-21
description: Узнайте, как управлять периодами доступности ресурсов и обеспечить эффективную
  доступность ресурсов проекта с помощью Aspose.Tasks для .NET. Это пошаговое руководство
  показывает, как добавлять, обновлять и удалять периоды доступности.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Доступность ресурсов проекта – Управление периодами доступности в Aspose.Tasks
url: /ru/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Доступность ресурсов проекта: коллекция периодов доступности в Aspose.Tasks

Управление **доступностью ресурсов проекта** является ключевой частью успешного планирования. В этом руководстве вы узнаете **как управлять доступностью** ресурсов с помощью API Aspose.Tasks for .NET, шаг за шагом, от загрузки проекта до копирования периодов между ресурсами.

## Быстрые ответы
- **Какой основной класс для периодов доступности?** `AvailabilityPeriod` в пространстве имён `Aspose.Tasks`.  
- **Можно ли очистить существующие периоды?** Да, вызовите `resource.AvailabilityPeriods.Clear()`.  
- **Как добавить новый период?** Создайте объект `AvailabilityPeriod` и используйте `Add` или `Insert`.  
- **Можно ли скопировать периоды к другому ресурсу?** Конечно – используйте `CopyTo`, а затем добавьте каждый элемент в целевой ресурс.  
- **Нужна ли лицензия для продакшн‑использования?** Да, для не‑тестовых развертываний требуется коммерческая лицензия Aspose.Tasks.

## Что такое доступность ресурсов проекта?
Доступность ресурсов проекта определяет даты и единицы (процент ёмкости), когда ресурс может быть назначен задачам. Управляя этими периодами, вы предотвращаете перегрузку и повышаете точность расписания.

## Почему стоит использовать Aspose.Tasks для управления периодами доступности?
- **Полная интеграция с .NET** – без COM‑interop, чистый управляемый код.  
- **Тонкая настройка** – задавайте точные даты начала/окончания и дробные единицы.  
- **Простое копирование** – перемещайте данные о доступности между ресурсами без ручного парсинга.  
- **Оптимизированная производительность** – эффективно работает с большими MPP‑файлами.

## Предварительные требования
1. **Visual Studio** – любая современная версия (2019, 2022 и новее).  
2. **Aspose.Tasks for .NET** – скачайте с [here](https://releases.aspose.com/tasks/net/).  
3. **Базовые знания C#** – вы должны уверенно работать с классами, коллекциями и LINQ.

## Импорт пространств имён

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

Мы импортируем основное пространство имён Aspose.Tasks вместе со стандартными коллекциями .NET, которые понадобятся позже.

## Шаг 1: Инициализация проекта и ресурса

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Здесь мы загружаем существующий MPP‑файл и получаем ресурс, доступность которого нужно изменить (ID = 1).

## Шаг 2: Очистка существующих периодов доступности

```csharp
resource.AvailabilityPeriods.Clear();
```

Очистка удаляет все ранее определённые периоды, предоставляя чистый лист.

## Шаг 3: Добавление периодов доступности

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

Мы получаем коллекцию объектов `AvailabilityPeriod` (предполагается, что вспомогательная функция `GetPeriods` определена где‑то ещё) и добавляем каждый, проверяя, что коллекция доступна для записи.

## Шаг 4: Вставка нового периода доступности

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Создаём пользовательский период для 2013 года и вставляем его на позицию 1 (второй слот), если он ещё не присутствует.

## Шаг 5: Отображение периодов доступности

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

Быстрый вывод в консоль показывает общее количество и детали каждого периода – удобно для отладки или проверки.

## Шаг 6: Копирование периодов доступности к другому ресурсу

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

Мы копируем всю коллекцию в массив, очищаем периоды целевого ресурса и затем заполняем их заново. Это демонстрирует, как дублировать данные о доступности между ресурсами.

## Шаг 7: Обновление и удаление периодов доступности

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Здесь мы изменяем `AvailableUnits` предпоследнего периода, а затем удаляем добавленный ранее период 2013 года.

## Распространённые проблемы и решения
- **Ошибка «коллекция только для чтения»** – Убедитесь, что проект открыт не в режиме только‑для‑чтения и что вы вызвали `resource.AvailabilityPeriods.Clear()` перед добавлением новых элементов.  
- **Перекрывающиеся периоды** – Aspose.Tasks не объединяет их автоматически; потребуется написать собственную логику для обнаружения и разрешения конфликтов.  
- **Неправильный формат даты** – Всегда используйте объекты `DateTime`; парсинг строк может привести к ошибкам, зависящим от локали.

## Часто задаваемые вопросы

**В: Можно ли добавить пользовательские поля к периодам доступности?**  
О: Нет, в Aspose.Tasks for .NET периоды доступности не поддерживают пользовательские поля.

**В: Связаны ли периоды доступности с конкретными задачами?**  
О: Нет, они привязаны к ресурсам и определяют, когда ресурс в целом доступен для задач.

**В: Можно ли импортировать периоды доступности из внешних источников?**  
О: Да, вы можете импортировать периоды из CSV, XML или базы данных, создавая объекты `AvailabilityPeriod` и добавляя их в коллекцию.

**В: Как обрабатывать перекрывающиеся периоды доступности?**  
О: Перекрытия не решаются автоматически; необходимо реализовать собственную проверку для объединения или отклонения конфликтующих периодов.

**В: Есть ли ограничение на количество периодов доступности у ресурса?**  
О: Жёсткого ограничения нет, но очень большие коллекции могут влиять на производительность; по возможности консолидируйте периоды.

## Заключение

В этом руководстве мы рассмотрели всё, что нужно знать для управления **доступностью ресурсов проекта** с помощью Aspose.Tasks for .NET — от инициализации проекта и очистки старых данных до добавления, вставки, копирования, обновления и удаления периодов доступности. Овладение этими шагами помогает поддерживать календарь ресурсов точным, а графики проектов — реалистичными.

---

**Последнее обновление:** 2026-03-21  
**Тестировано с:** Aspose.Tasks for .NET (последний релиз)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}