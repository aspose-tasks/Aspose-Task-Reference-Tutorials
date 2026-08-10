---
date: 2026-04-06
description: Узнайте, как удалить все базовые линии и управлять коллекциями базовых
  линий в Aspose.Tasks для .NET с пошаговыми примерами кода.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Удалить все базовые линии с помощью Aspose.Tasks Baseline Collection
second_title: Aspose.Tasks .NET API
title: Удалить все базовые планы с помощью коллекции Baseline в Aspose.Tasks
url: /ru/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Удалить все базовые линии с помощью Aspose.Tasks Baseline Collection

## Введение

Aspose.Tasks for .NET позволяет управлять файлами Microsoft Project напрямую из ваших .NET приложений. Одна из самых мощных возможностей — это способность **delete all baselines** для ресурса, что необходимо, когда нужно сбросить данные отслеживания проекта или начать новый период базовой линии. В этом руководстве мы пройдем весь процесс — от загрузки файла проекта до удаления каждой базовой линии, прикреплённой к конкретному ресурсу — используя понятные объяснения и готовый к запуску код C#.

## Быстрые ответы
- **Что делает “delete all baselines”?** Он удаляет каждую сохранённую запись базовой линии для выбранного ресурса, очищая исторические данные о стоимости и работе.  
- **Зачем это может понадобиться?** Для сброса отслеживания после крупного изменения проекта или когда исходные базовые линии более не актуальны.  
- **Какая библиотека предоставляет эту возможность?** Aspose.Tasks for .NET.  
- **Нужна ли лицензия?** Для использования в продакшене требуется действующая лицензия Aspose.Tasks; доступна бесплатная пробная версия.  
- **Совместим ли код с .NET 6+?** Да, API работает с .NET Framework 4.5+, .NET Core 3.1+ и .NET 5/6.

## Что такое базовая линия и почему удалять все базовые линии?

Базовая линия фиксирует исходный план по стоимости, работе и расписанию в определённый момент времени. В течение жизни проекта вы можете создавать несколько базовых линий (Baseline 1, Baseline 2 и т.д.), чтобы сравнивать фактический прогресс с разными плановыми снимками. Однако существуют сценарии — например, переопределение проекта или новый старт — когда хранение этих исторических базовых линий становится запутанным. Удаление всех базовых линий даёт чистый лист, позволяя установить новые базовые линии, отражающие текущую реальность.

## Требования

1. **Visual Studio** – любой современный выпуск (Community, Professional или Enterprise).  
2. **Aspose.Tasks for .NET** – скачайте его по [download link](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – вы должны быть уверены в работе с переменными, циклами и выводом в консоль.  
4. **A Microsoft Project file** (`.mpp`) – в примерах будет использован образец файла с именем *WorkWithBaselineCollection.mpp*.

## Импорт пространств имён

Сначала импортируйте необходимые пространства имён, чтобы компилятор знал, где находятся используемые нами классы.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Шаг 1: Загрузить файл проекта

Мы начинаем с загрузки существующего файла проекта. Настройте `DataDir`, чтобы он указывал на папку, содержащую ваш файл `.mpp`.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Шаг 2: Получить целевой ресурс

Для демонстрации мы получаем ресурс с UID = 1. В реальном сценарии вы бы находили ресурс по имени или другому идентификатору.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Шаг 3: Показать информацию о существующих базовых линиях

Перед удалением полезно увидеть, какие базовые линии сейчас привязаны к ресурсу. Это даст уверенность, что вы удаляете нужные данные.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Шаг 4: Перебрать все базовые линии

Здесь мы проходим по каждой базовой линии, выводя ключевые метрики, такие как стоимость, работа и заработанная стоимость (BCWP/BCWS). Этот шаг необязателен, но полезен для журналирования или аудита.

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

## Удалить все базовые линии

Теперь мы выполняем основное действие: **delete all baselines** для выбранного ресурса. Сначала копируем коллекцию в список, чтобы избежать изменения коллекции во время итерации, затем удаляем каждую базовую линию по одной.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

После выполнения этого блока `resource.Baselines.Count` будет `0`, подтверждая, что все записи базовых линий удалены.

## Распространённые проблемы и советы

- **NullReferenceException** – Убедитесь, что файл проекта действительно содержит целевой ресурс; иначе `GetByUid` вернёт `null`.  
- **Licensing** – Без действующей лицензии Aspose.Tasks вы увидите водяной знак в выводе и ограниченную функциональность.  
- **Performance** – Для очень больших проектов рассмотрите итерацию с `Parallel.ForEach` для ускорения процесса удаления, но помните, что базовая коллекция не является потокобезопасной.

## Часто задаваемые вопросы

**Q: Может ли Aspose.Tasks работать с большими файлами проектов?**  
A: Да, Aspose.Tasks оптимизирован для производительности и может эффективно обрабатывать многогигабайтные файлы `.mpp`.

**Q: Совместима ли библиотека со всеми версиями Microsoft Project?**  
A: Aspose.Tasks поддерживает Project 2000 до Project 2024, охватывая как старые форматы `.mpp`, так и новые файлы на основе XML.

**Q: Могу ли я настроить базовые линии перед их удалением?**  
A: Абсолютно. Вы можете прочитать или изменить любое свойство базовой линии (стоимость, работа, даты) перед тем, как решить её удалить.

**Q: Работает ли Aspose.Tasks на облачных платформах?**  
A: Да, API работает в любой .NET‑совместимой среде, включая Azure App Service, AWS Lambda (через .NET Core) и Docker‑контейнеры.

**Q: Где я могу обратиться за помощью к сообществу?**  
A: Посетите [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15), чтобы связаться с другими разработчиками и сотрудниками Aspose.

## Заключение

В этом руководстве мы продемонстрировали, как **delete all baselines** из ресурса с помощью Aspose.Tasks for .NET. Следуя пошаговому коду, вы можете сбросить данные базовых линий, поддерживать чистоту отслеживания проекта и подготовить расписание к новому плановому циклу. Не стесняйтесь экспериментировать с созданием новых базовых линий после удаления, чтобы увидеть, как библиотека обновляет файл проекта.

---

**Последнее обновление:** 2026-04-06  
**Тестировано с:** Aspose.Tasks 24.12 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}