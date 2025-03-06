---
title: Статистика по элементам риска в Aspose.Tasks
linktitle: Статистика по элементам риска в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Раскройте возможности анализа рисков в файлах MS Project с помощью Aspose.Tasks для .NET. Получайте ценную информацию, устраняйте неопределенности и добивайтесь успеха проекта без особых усилий.
type: docs
weight: 21
url: /ru/net/resource-risk-analysis/risk-item-statistics/
---
## Введение
Вы хотите улучшить свои навыки управления проектами с помощью Aspose.Tasks для .NET? Погрузитесь в область анализа рисков с помощью нашего пошагового руководства по получению статистики по элементам риска в файлах MS Project. Используя мощные возможности Aspose.Tasks, вы можете получить бесценную информацию о неопределенностях проекта и принять обоснованные решения для эффективного снижения рисков.
## Предварительные условия
Прежде чем мы отправимся в это путешествие, убедитесь, что у вас есть следующие предварительные условия:
1.  Aspose.Tasks для библиотеки .NET: загрузите и установите библиотеку из[Документация Aspose.Tasks для .NET](https://reference.aspose.com/tasks/net/). Эта библиотека предоставляет вам надежные инструменты для программного управления файлами MS Project.
2. Среда разработки .NET: настройте среду разработки .NET, включая Visual Studio или любую другую IDE по вашему выбору, чтобы облегчить интеграцию Aspose.Tasks в ваши проекты.

## Импортировать пространства имен
Включите в свой проект необходимые пространства имен, чтобы использовать функциональные возможности Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Шаг 1: Определите каталог данных
```csharp
String DataDir = "Your Document Directory";
```
 Обязательно замените`"Your Document Directory"` с путем к каталогу ваших документов, где расположены файлы MS Project.
## Шаг 2. Настройте параметры анализа рисков
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Настроить`IterationsCount`параметр, основанный на требованиях вашего проекта, для контроля точности анализа рисков.
## Шаг 3. Загрузите файл проекта MS
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Загрузите нужный файл MS Project в`project` объект для дальнейшего анализа.
## Шаг 4. Определите задачу и инициализируйте шаблон риска
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
Укажите задачу для анализа рисков и настройте шаблон рисков с соответствующими параметрами, такими как тип распределения, оптимистическая и пессимистическая продолжительность и уровень достоверности.
## Шаг 5: Анализ рисков проекта
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Инициируйте процесс анализа рисков, используя определенные настройки и данные проекта.
## Шаг 6: Получение и отображение статистики
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
Извлекайте и отображайте различные статистические показатели, связанные с элементами риска в файле MS Project, включая ожидаемое значение, стандартное отклонение, процентили, минимальные и максимальные значения.

## Заключение
В заключение, освоение анализа рисков в файлах MS Project с использованием Aspose.Tasks для .NET открывает множество возможностей для менеджеров проектов и заинтересованных сторон. Следуя нашему подробному руководству, вы сможете уверенно преодолевать неопределенности, обеспечивая успешные результаты проекта.
## Часто задаваемые вопросы
### Могу ли я интегрировать Aspose.Tasks с другими библиотеками .NET для расширения функциональности?
Абсолютно! Aspose.Tasks легко интегрируется с различными библиотеками .NET, что позволяет вам расширять его возможности в соответствии с требованиями вашего проекта.
### Доступна ли пробная версия Aspose.Tasks для .NET?
 Да, вы можете изучить возможности Aspose.Tasks, открыв[бесплатная пробная версия](https://releases.aspose.com/) доступны на нашем сайте.
### Как часто выпускаются обновления и улучшения для Aspose.Tasks?
Мы стремимся постоянно улучшать Aspose.Tasks, периодически выпуская обновления и улучшения, гарантируя, что у вас всегда будет доступ к новейшим функциям и оптимизациям.
### Могу ли я получить техническую поддержку для Aspose.Tasks?
Конечно! Наша специализированная группа поддержки всегда доступна на[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) чтобы помочь вам с любыми вопросами или проблемами, с которыми вы можете столкнуться в процессе внедрения.
### Предлагаете ли вы временные лицензии для краткосрочных проектов?
 Да, если вам требуется Aspose.Tasks для краткосрочного проекта, вы можете воспользоваться нашим удобным[временная лицензия](https://purchase.aspose.com/temporary-license/) возможность удовлетворить ваши потребности в лицензировании без каких-либо долгосрочных обязательств.