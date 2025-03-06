---
title: Освоение представлений использования задач в Aspose.Tasks для .NET
linktitle: Настройка представлений использования задач в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Изучите Aspose.Tasks для .NET и узнайте, как настраивать представления использования задач. Настройте параметры шкалы времени и улучшите визуальные эффекты управления проектами.
weight: 24
url: /ru/net/task-table-management/task-usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Освоение представлений использования задач в Aspose.Tasks для .NET

## Введение
В сфере управления проектами визуализация использования задач имеет решающее значение для эффективного планирования и выполнения. Aspose.Tasks для .NET предоставляет надежное решение для визуализации представлений использования задач, позволяющее настраивать параметры шкалы времени и форматы представления. В этом руководстве мы рассмотрим шаги по настройке представлений использования задач с помощью Aspose.Tasks.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
1.  Aspose.Tasks для .NET: убедитесь, что библиотека Aspose.Tasks интегрирована в ваш проект .NET. Вы можете скачать его[здесь](https://releases.aspose.com/tasks/net/).
2. Среда .NET: на вашем компьютере должна быть установлена рабочая среда .NET.
## Импортировать пространства имен
В свой проект .NET импортируйте необходимые пространства имен для доступа к функциям Aspose.Tasks. Добавьте в свой код следующие строки:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Шаг 1. Установите путь к каталогу документов
 Прежде чем работать с функциями Aspose.Tasks, укажите путь к каталогу ваших документов. Заменять`"Your Document Directory"` с реальным путем.
```csharp
String DataDir = "Your Document Directory";
```
## Шаг 2. Загрузите проект
 Инициализируйте Aspose.Tasks`Project` объект, загрузив файл проекта (например, TaskUsageView.mpp).
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## Шаг 3. Определите параметры сохранения.
 Создать`SaveOptions`объект для указания параметров рендеринга. Установите временную шкалу «Дни» и формат представления «TaskUsage».
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## Шаг 4. Сохраните, используя временную шкалу дней.
Сохраните проект с предопределенными настройками шкалы времени «Дни».
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Шаг 5. Сохраните с использованием шкалы времени ThirdsOfMonths.
Измените настройки шкалы времени на «ThirdsOfMonths» и сохраните проект.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Шаг 6: Сэкономьте, используя временную шкалу в месяцах
Установите временную шкалу «Месяцы» и сохраните проект с обновленными настройками.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Заключение
Настройка представлений использования задач с помощью Aspose.Tasks для .NET — это простой процесс. Настраивая параметры шкалы времени, вы можете адаптировать визуализацию задач проекта в соответствии с вашими конкретными потребностями.
 Не стесняйтесь изучить дополнительные функции и возможности в[документация](https://reference.aspose.com/tasks/net/).
## Часто задаваемые вопросы
### Могу ли я настроить временную шкалу за пределами предопределенных настроек?
Да, вы можете установить собственную шкалу времени, указав интервалы и единицы измерения.
### Существуют ли другие форматы презентаций?
Aspose.Tasks поддерживает различные форматы презентаций, включая GanttChart, ResourceUsage и другие.
### Совместим ли Aspose.Tasks с различными форматами файлов проектов?
Да, Aspose.Tasks поддерживает популярные форматы файлов проектов, такие как MPP, XML и CSV.
### Могу ли я применить разные настройки шкалы времени к конкретным задачам?
Конечно, вы можете настроить параметры шкалы времени для отдельных задач в рамках вашего проекта.
### Как я могу получить поддержку или обратиться за помощью по Aspose.Tasks?
 Посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) за поддержку и руководство сообщества.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
