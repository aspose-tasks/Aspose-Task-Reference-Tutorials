---
title: Соберите статистику по элементам риска MS Project в Aspose.Tasks
linktitle: Сбор статистики по элементам риска в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как собирать статистику по элементам риска из файлов MS Project с помощью Aspose.Tasks для .NET. Расширьте свои возможности управления проектами.
type: docs
weight: 22
url: /ru/net/resource-risk-analysis/risk-item-statistics-collection/
---
## Введение
В этом руководстве мы рассмотрим, как собирать статистику по элементам риска из файлов MS Project с помощью Aspose.Tasks для .NET. Эта библиотека предоставляет мощные функции для анализа данных проекта, включая оценку рисков и статистический анализ.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1. Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks. Вы можете получить его из[страница загрузки](https://releases.aspose.com/tasks/net/).
2. Среда разработки: настройте среду разработки для программирования .NET.

## Импортировать пространства имен
Прежде чем приступить к кодированию, обязательно импортируйте необходимые пространства имен в свой проект:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Шаг 1. Загрузите файл проекта
Сначала вам необходимо загрузить файл MS Project в ваше приложение. Вот как вы можете этого добиться:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Шаг 2. Определите настройки анализа рисков
Инициализируйте настройки анализа рисков, включая количество итераций, как показано ниже:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Шаг 3. Инициализация шаблона риска
Настройте шаблон риска для анализа, указав тип распределения, оптимистические и пессимистические проценты и уровень достоверности:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## Шаг 4. Выполните анализ рисков
 Создайте экземпляр`RiskAnalyzer` класс и анализ проекта:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Шаг 5: Получить статистику
Получите статистику по элементам риска, например досрочное завершение, из результатов анализа:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Шаг 6. Распечатайте статистику
Переберите статистику и распечатайте детали:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Распечатать другую соответствующую статистику...
}
```

## Заключение
В этом руководстве мы узнали, как использовать Aspose.Tasks для .NET для сбора статистики по элементам риска из файлов MS Project. Следуя этим шагам, вы сможете эффективно анализировать данные проекта и оценивать потенциальные риски, а также способствовать более эффективному принятию решений и управлению проектом.

## Часто задаваемые вопросы
### Вопрос: Может ли Aspose.Tasks обрабатывать большие файлы MS Project?
О: Да, Aspose.Tasks способен эффективно обрабатывать большие файлы MS Project, обеспечивая надежную производительность и масштабируемость.
### Вопрос: Поддерживает ли Aspose.Tasks другие форматы файлов проекта, кроме .mpp?
О: Да, Aspose.Tasks поддерживает различные форматы файлов проектов, включая XML и MPT.
### Вопрос: Подходит ли Aspose.Tasks для приложений управления проектами корпоративного уровня?
О: Безусловно, Aspose.Tasks разработан для удовлетворения потребностей приложений управления проектами корпоративного уровня, предоставляя надежные функции и обширную документацию.
### Вопрос: Могу ли я настроить параметры анализа рисков в Aspose.Tasks?
О: Да, Aspose.Tasks предлагает гибкость в настройке параметров анализа рисков в соответствии с конкретными требованиями и сценариями вашего проекта.
### Вопрос: Доступна ли техническая поддержка для пользователей Aspose.Tasks?
 О: Да, пользователи Aspose.Пользователи Tasks могут получить доступ к технической поддержке через Aspose.[форумы](https://forum.aspose.com/c/tasks/15), где они могут задавать вопросы, сообщать о проблемах и взаимодействовать с сообществом.