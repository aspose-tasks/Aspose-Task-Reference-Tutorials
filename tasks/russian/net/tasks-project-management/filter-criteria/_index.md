---
title: Освоение критериев фильтрации проектов MS с помощью Aspose.Tasks
linktitle: Критерии фильтрации в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как реализовать критерии фильтрации в MS Project с помощью Aspose.Tasks для .NET. Повысьте эффективность управления проектами с помощью целевого анализа данных.
weight: 18
url: /ru/net/tasks-project-management/filter-criteria/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Освоение критериев фильтрации проектов MS с помощью Aspose.Tasks

## Введение
В сфере управления проектами Microsoft Project является надежным инструментом, предлагающим множество функций, которые помогут планировщикам и менеджерам проектов. Среди его многочисленных функций — возможность фильтровать данные проекта, позволяя пользователям сосредоточиться на конкретных аспектах задач своего проекта. Однако освоение этих возможностей фильтрации может оказаться сложной задачей без правильного руководства. Цель этого руководства — прояснить этот процесс, предоставив пошаговое руководство по реализации критериев фильтра в MS Project с использованием Aspose.Tasks для .NET.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
1. Базовое понимание C#. Знакомство с языком программирования C# необходимо для понимания концепций, изложенных в этом руководстве.
2.  Установка Aspose.Tasks для .NET: Убедитесь, что в вашей среде разработки установлен Aspose.Tasks для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/tasks/net/).
3. Файл Microsoft Project: подготовьте файл Microsoft Project (например, Project2003.mpp), который вы будете использовать для реализации критериев фильтра.

## Импортировать пространства имен
Во-первых, вам необходимо импортировать необходимые пространства имен для работы с Aspose.Tasks for .NET. Следуй этим шагам:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## Шаг 1. Загрузите файл проекта
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 Объяснение: Эта строка кода инициализирует новый экземпляр`Project` class и загружает файл Microsoft Project, указанный по его пути.
## Шаг 2. Получение фильтра задач
```csharp
var filter = project.TaskFilters.ToList()[1];
```
Объяснение: Здесь мы извлекаем фильтр задач из проекта. Отрегулируйте индекс (`[1]`) согласно вашему требованию, чтобы выбрать нужный фильтр.
## Шаг 3. Отображение строк критериев
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
Объяснение: В этом разделе выполняется итерация по каждой строке критериев фильтра и отображаются ее поле, операция, тест и значения (если таковые имеются).
## Шаг 4. Распечатка критериев фильтра
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
Объяснение: Распечатывает действие критериев фильтра.
## Шаг 5. Отображение сведений о критериях
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
Объяснение: Эта часть извлекает и отображает подробную информацию о каждой строке критериев, предоставляя представление о конфигурации фильтра.

## Заключение
Освоение критериев фильтрации в MS Project с использованием Aspose.Tasks for .NET — ценный навык, который может значительно повысить эффективность управления проектами. Следуя этому руководству, вы научились программно манипулировать критериями фильтра, что позволит вам адаптировать представления проекта к вашим конкретным потребностям.
## Часто задаваемые вопросы
### Вопрос: Могу ли я одновременно применить несколько фильтров в MS Project?
О: Да, вы можете комбинировать несколько фильтров для дальнейшего уточнения данных вашего проекта.
### Вопрос: Поддерживает ли Aspose.Tasks старые версии файлов Microsoft Project?
О: Да, Aspose.Tasks обеспечивает обратную совместимость, позволяя вам работать с различными версиями файлов Microsoft Project.
### Вопрос: Совместим ли Aspose.Tasks с другими платформами .NET?
О: Aspose.Tasks поддерживает .NET Framework, .NET Core и .NET Standard, обеспечивая гибкость в различных средах разработки.
### Вопрос: Могу ли я настроить критерии фильтрации на основе динамических условий?
О: Конечно, вы можете программно настроить критерии фильтра на основе динамических параметров, что позволяет проводить адаптивный анализ данных проекта.
### Вопрос: Куда я могу обратиться за помощью, если у меня возникнут проблемы с Aspose.Tasks?
 О: Вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) чтобы обратиться за поддержкой к сообществу или напрямую обратиться в службу поддержки Aspose.Tasks для получения индивидуальной помощи.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
