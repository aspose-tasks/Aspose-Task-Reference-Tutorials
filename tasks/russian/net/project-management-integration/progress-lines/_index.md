---
title: Обработка линий выполнения проекта MS с помощью Aspose.Tasks
linktitle: Обработка линий прогресса в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как управлять линиями выполнения в файлах MS Project с помощью Aspose.Tasks для .NET, улучшая визуализацию проекта и управление им.
weight: 15
url: /ru/net/project-management-integration/progress-lines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Обработка линий выполнения проекта MS с помощью Aspose.Tasks

## Введение
Microsoft Project (MS Project) — мощный инструмент управления проектами, позволяющий пользователям отслеживать различные аспекты своих проектов. Одной из важнейших особенностей MS Project является возможность визуализировать линии прогресса, что помогает заинтересованным сторонам понять состояние и траекторию проекта. В этом уроке мы рассмотрим, как обрабатывать линии выполнения в MS Project с помощью библиотеки Aspose.Tasks для .NET.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1. Visual Studio: установите Visual Studio или любую другую предпочтительную среду разработки .NET.
2.  Aspose.Tasks для .NET: Загрузите и установите Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/tasks/net/).
3. Базовые знания C#: Знакомство с языком программирования C# будет преимуществом.

## Импорт пространств имен
Для начала импортируем необходимые пространства имен:
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
Теперь давайте разберем каждый шаг в обработке линий прогресса:
## Шаг 1. Загрузите файл проекта
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 Здесь мы загружаем файл MS Project`Project2.mpp` и установите дату его статуса.
## Шаг 2. Определите представление диаграммы Ганта
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Мы преобразуем представление проекта в представление диаграммы Ганта для дальнейших манипуляций.
## Шаг 3: Определите линии прогресса
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
Мы инициализируем линии прогресса для представления диаграммы Ганта.
## Шаг 4. Настройте параметры линии прогресса
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
Здесь мы устанавливаем различные свойства для линий прогресса, такие как цвет линии, узор, шрифт и т. д.
## Шаг 5. Проверьте конфигурацию линий прогресса
```csharp
// Настройки линий выполнения вывода
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// Вывод других настроек...
```
Выводим настроенные настройки линий прогресса на проверку.
## Шаг 6. Сохраните файл проекта.
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
Наконец, мы сохраняем измененный файл проекта со строками выполнения.

## Заключение
В этом уроке мы узнали, как обрабатывать линии выполнения MS Project с помощью Aspose.Tasks для .NET. Выполнив эти шаги, вы сможете эффективно программно настраивать и визуализировать линии выполнения в файлах MS Project.
## Часто задаваемые вопросы
### Вопрос: Могу ли я дополнительно настроить внешний вид линий прогресса?
О: Да, вы можете настроить различные свойства, такие как цвет линий, узор и шрифт, в соответствии с вашими требованиями.
### Вопрос: Поддерживает ли Aspose.Tasks другие функции управления проектами?
О: Да, Aspose.Tasks предоставляет обширную поддержку для управления различными аспектами файлов MS Project, включая задачи, ресурсы и календари.
### Вопрос: Могу ли я интегрировать Aspose.Tasks с другими библиотеками .NET?
О: Конечно, Aspose.Tasks спроектирован так, чтобы легко интегрироваться с другими библиотеками .NET, что позволяет вам еще больше улучшить ваши приложения для управления проектами.
### Вопрос: Существует ли форум сообщества для поддержки Aspose.Tasks?
 О: Да, вы можете найти полезные ресурсы и обратиться за помощью на форуме Aspose.Tasks.[здесь](https://forum.aspose.com/c/tasks/15).
### Вопрос: Предлагает ли Aspose.Tasks временные лицензии для ознакомительных целей?
 О: Да, вы можете получить временную лицензию для ознакомления на сайте[здесь](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
