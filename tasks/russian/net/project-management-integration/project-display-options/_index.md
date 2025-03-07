---
title: Настройка параметров отображения MS Project в Aspose.Tasks
linktitle: Настройка параметров отображения проекта в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как программно настроить параметры отображения MS Project с помощью Aspose.Tasks для .NET. Настройте внешний вид вашего проекта без особых усилий.
weight: 17
url: /ru/net/project-management-integration/project-display-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Настройка параметров отображения MS Project в Aspose.Tasks

## Введение
Microsoft Project предлагает множество вариантов отображения для настройки внешнего вида вашего проекта. Aspose.Tasks для .NET предоставляет надежную среду для программного управления этими параметрами. В этом уроке мы рассмотрим, как настроить параметры отображения MS Project с помощью Aspose.Tasks.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующее:
1.  Aspose.Tasks для .NET: Загрузите и установите библиотеку с сайта[здесь](https://releases.aspose.com/tasks/net/).
2. Файл Microsoft Project: подготовьте действительный файл MS Project (.mpp), готовый применить параметры отображения.
3. Базовые знания C#: Требуется знание языка программирования C#.

## Импорт пространств имен
Во-первых, обязательно импортируйте необходимые пространства имен в ваш код C#:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Шаг 1. Загрузите файл проекта
 Загрузите файл MS Project, используя`Project` класс, предоставленный Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Шаг 2. Настройте параметры отображения
Теперь давайте настроим различные параметры отображения, доступные в MS Project:
### Отключить предупреждения расписания задач
Чтобы отключить предупреждения о конфликтах планирования с задачами, запланированными вручную (доступно для Project 2010 и более поздних версий):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Добавить пробел перед меткой
Установите для добавления пробела перед числовым значением и сокращением времени:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Настройка отображения меток для единиц времени
Настройте отображение различных единиц времени:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Показать сводную задачу проекта
Отобразить сводную информацию обо всем проекте в одной строке:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Включить предложения по расписанию задач
Разрешить отображение предложений по планированию конфликтов с задачами, запланированными вручную:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Подчеркивание гиперссылок
Установите для подчеркивания гиперссылок внутри проекта:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Шаг 3. Сохраните проект
Наконец, сохраните проект с примененными параметрами отображения:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Заключение
В этом уроке мы узнали, как настроить параметры отображения MS Project с помощью Aspose.Tasks для .NET. Благодаря этим возможностям вы можете эффективно программно настроить внешний вид файлов проекта.
## Часто задаваемые вопросы
### Вопрос: Могу ли я применить эти параметры отображения только к определенным задачам?
О: Да, вы можете выборочно применять параметры отображения к отдельным задачам с помощью API Aspose.Tasks.
### Вопрос: Влияют ли эти параметры отображения на базовые данные проекта?
О: Нет, эти параметры изменяют только визуальное представление проекта и не изменяют базовые данные.
### Вопрос. Совместимы ли эти параметры отображения со всеми версиями Microsoft Project?
О: Нет, некоторые параметры могут быть специфичны для определенных версий MS Project. Подробную информацию о совместимости см. в документации.
### Вопрос: Могу ли я вернуть параметры отображения к настройкам по умолчанию?
О: Да, вы можете сбросить параметры отображения до значений по умолчанию, используя API Aspose.Tasks.
### Вопрос. Существуют ли какие-либо ограничения на программную настройку параметров отображения?
О: Хотя Aspose.Tasks предоставляет широкие возможности настройки, некоторые параметры отображения могут быть недоступны программно из-за ограничений формата файла MS Project.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
