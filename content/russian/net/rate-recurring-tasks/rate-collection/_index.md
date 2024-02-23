---
title: Освойте ставки по проектам MS с помощью Aspose.Tasks
linktitle: Сбор ставок в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как управлять ставками в файлах MS Project с помощью Aspose.Tasks для .NET. Пошаговое руководство по эффективному управлению ресурсами.
type: docs
weight: 11
url: /ru/net/rate-recurring-tasks/rate-collection/
---
## Введение
Добро пожаловать в наше руководство по управлению ставками в MS Project с использованием Aspose.Tasks для .NET! В этом руководстве мы познакомим вас с процессом работы со ставками в файлах MS Project с помощью Aspose.Tasks. Независимо от того, являетесь ли вы опытным разработчиком или только начинаете разработку .NET, это руководство предоставит вам пошаговые инструкции по эффективному управлению ставками в ваших проектах.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:
### 1. Установленная Visual Studio
Убедитесь, что в вашей системе установлена Visual Studio. Вы можете скачать его с сайта, если еще этого не сделали.
### 2. Aspose.Tasks для .NET
 Загрузите и установите библиотеку Aspose.Tasks для .NET с сайта[Веб-сайт](https://releases.aspose.com/tasks/net/).
### 3. Базовые знания C# и .NET.
Ознакомьтесь с языком программирования C# и основами .NET Framework, чтобы лучше понять примеры кода, представленные в этом руководстве.
## Импортировать пространства имен
В свой проект C# импортируйте необходимые пространства имен для использования функций Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Теперь давайте разобьем каждый пример на несколько этапов:
## Шаг 1. Загрузите файл проекта MS
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Здесь мы создаем новый`Project` объект, загрузив существующий файл MS Project.
## Шаг 2. Добавьте ресурс и установите работу и ставки.
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Добавляем в проект новый ресурс, задаем ему тип работы, объем работы и нормативную ставку.
## Шаг 3. Добавьте тарифы к ресурсу
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Мы добавляем ставки на ресурс, указывая даты начала и окончания, стандартную ставку и формат ставки.
## Шаг 4: Информация о скорости печати
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
На этом шаге выводится информация о ставках, связанных с ресурсом.
## Шаг 5. Обновите тариф
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Мы обновляем дату окончания определенного тарифа.
## Шаг 6. Удаление ставок
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
На этом шаге удаляются все ставки определенного типа.
## Шаг 7: Перебрать оставшиеся ставки
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Наконец, мы перебираем оставшиеся ставки после удаления.
## Заключение
В заключение, это руководство предоставило вам подробное руководство по управлению ставками в файлах MS Project с использованием Aspose.Tasks для .NET. Следуя пошаговым инструкциям, изложенным в этом руководстве, вы сможете эффективно управлять ставками в своих проектах, обеспечивая точное управление ресурсами.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks для .NET с другим программным обеспечением для управления проектами?
О: Да, Aspose.Tasks for .NET поддерживает интеграцию с различным программным обеспечением для управления проектами, включая MS Project, Primavera и другие.
### Вопрос: Совместим ли Aspose.Tasks для .NET с различными версиями файлов MS Project?
О: Безусловно, Aspose.Tasks for .NET поддерживает работу с файлами MS Project разных версий, обеспечивая гибкость и совместимость.
### Вопрос: Предлагает ли Aspose.Tasks для .NET документацию и поддержку?
 О: Да, вы можете найти подробную документацию и доступ к форумам поддержки на Aspose.Tasks.[Веб-сайт](https://reference.aspose.com/tasks/net/).
### Вопрос: Могу ли я попробовать Aspose.Tasks для .NET перед покупкой?
О: Да, вы можете воспользоваться бесплатной пробной версией Aspose.Tasks для .NET, чтобы оценить ее возможности и совместимость с вашими требованиями.
### Вопрос: Как я могу приобрести лицензию на Aspose.Tasks для .NET?
 О: Вы можете приобрести лицензию на Aspose.Tasks для .NET на сайте[Веб-сайт](https://purchase.aspose.com/temporary-license/)который предоставляет гибкие варианты лицензирования в соответствии с вашими потребностями.