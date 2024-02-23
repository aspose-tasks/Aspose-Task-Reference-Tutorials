---
title: Простые повторяющиеся интервалы проекта MS в Aspose.Tasks
linktitle: Управление повторяющимися интервалами в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как легко управлять повторяющимися интервалами в MS Project с помощью Aspose.Tasks для .NET.
type: docs
weight: 12
url: /ru/net/rate-recurring-tasks/recurring-intervals/
---
## Введение
Вы хотите эффективно управлять повторяющимися интервалами в файлах Microsoft Project с помощью Aspose.Tasks для .NET? Это подробное руководство шаг за шагом проведет вас через весь процесс, гарантируя, что вы сможете легко справляться с повторяющимися интервалами в своих проектах. Прежде чем углубиться в руководство, давайте рассмотрим некоторые предварительные условия, чтобы убедиться, что вы готовы приступить к работе.
## Предварительные условия
Прежде чем приступить к изучению этого руководства, убедитесь, что у вас есть следующее:
1. Знание программирования C#: требуется базовое понимание языка программирования C# и его синтаксиса.
2. Установленная Visual Studio. Убедитесь, что в вашей системе установлена Visual Studio для кодирования и компиляции приложений .NET.
3. Библиотека Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks для .NET. Вы можете получить его от[здесь](https://releases.aspose.com/tasks/net/).

## Импортировать пространства имен
Начните с импорта необходимых пространств имен для доступа к функциям, предоставляемым библиотекой Aspose.Tasks for .NET.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Теперь давайте разобьем каждый пример на несколько этапов и объясним их подробно.
## Шаг 1. Инициализация объекта проекта:
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
Здесь мы инициализируем новый экземпляр`Project` класс, указав путь к файлу Microsoft Project.
## Шаг 2: Установите дату статуса:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
На этом шаге датой статуса проекта устанавливается дата его начала.
## Шаг 3. Доступ к представлению диаграммы Ганта:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Мы получаем доступ к представлению проекта в виде диаграммы Ганта.
## Шаг 4. Прочтите строку прогресса:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
На этом шаге извлекается повторяющийся интервал для строк прогресса из представления диаграммы Ганта.
## Шаг 5: Отображение информации об интервале:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Здесь мы отображаем информацию об интервале, номере недели и днях недели.
## Шаг 6: Переопределите повторяющийся интервал:
```csharp
var newInterval = new RecurringInterval();
```
 Мы создаем новый экземпляр`RecurringInterval` переопределить повторяющийся интервал.
## Шаг 7. Установите ежемесячные линии прогресса:
```csharp
// Установите ежемесячные линии прогресса по дням.
interval.MonthlyDay = true;
// Установите количество дней ежемесячных линий прогресса.
interval.MonthlyDayDayNumber = 1;
// Установите номер месяца для ежемесячных строк прогресса.
interval.MonthlyDayMonthNumber = 1;
// Установите линии прогресса по первому или последнему заранее определенному дню.
interval.MonthlyFirstLast = true;
// Установите тип первого или последнего дня ежемесячных линий прогресса.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Установите ежемесячное количество строк прогресса.
interval.MonthlyFirstLastMonthNumber = 1;
```
Эти шаги настраивают ежемесячные линии прогресса в соответствии с указанными параметрами.
## Шаг 8. Обновление линий прогресса:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Мы обновляем линии прогресса в представлении диаграммы Ганта, используя вновь определенный повторяющийся интервал.
## Шаг 9. Сохраните проект в формате PDF:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Наконец, мы сохраняем проект с обновленным повторяющимся интервалом в виде файла PDF.

## Заключение
В заключение, управление повторяющимися интервалами в файлах Microsoft Project с помощью Aspose.Tasks for .NET упрощается благодаря комплексным функциям, предоставляемым библиотекой. Следуя пошаговому руководству, изложенному в этом руководстве, вы сможете эффективно управлять повторяющимися интервалами в своих проектах, повышая производительность и организованность.
### Часто задаваемые вопросы
### Могу ли я использовать Aspose.Tasks для .NET с другими языками программирования?
Да, Aspose.Tasks для .NET можно использовать с любым языком, поддерживаемым .NET, например C# и VB.NET.
### Доступна ли пробная версия Aspose.Tasks для .NET?
 Да, вы можете скачать бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).
### Как я могу получить поддержку Aspose.Tasks для .NET?
 Вы можете получить поддержку на форуме Aspose.Tasks.[здесь](https://forum.aspose.com/c/tasks/15).
### Могу ли я приобрести временную лицензию на Aspose.Tasks для .NET?
 Да, вы можете приобрести временную лицензию у[здесь](https://purchase.aspose.com/temporary-license/).
### Где я могу найти полную документацию по Aspose.Tasks для .NET?
 Полную документацию можно найти[здесь](https://reference.aspose.com/tasks/net/).