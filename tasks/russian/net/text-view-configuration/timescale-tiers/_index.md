---
title: Настройка уровней шкалы времени диаграммы Ганта в Aspose.Tasks
linktitle: Настройка уровней шкалы времени в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Изучите Aspose.Tasks для .NET, чтобы настроить уровни временной шкалы в представлении диаграммы Ганта для точной визуализации временной шкалы проекта. #Aspose.Tasks #MS Project
weight: 16
url: /ru/net/text-view-configuration/timescale-tiers/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Настройка уровней шкалы времени диаграммы Ганта в Aspose.Tasks

## Введение
В динамичной среде управления проектами эффективная визуализация имеет решающее значение для понимания сроков и сроков. Aspose.Tasks для .NET предоставляет мощный набор инструментов, и в этом руководстве мы рассмотрим, как настроить уровни шкалы времени для оптимального представления в представлении диаграммы Ганта. Следуйте этим пошаговым инструкциям, чтобы улучшить визуализацию вашего проекта.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующее:
- Базовые знания C# и .NET.
-  Установлена библиотека Aspose.Tasks для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/tasks/net/).
- Среда разработки, предназначенная для разработки приложений .NET.
## Импортировать пространства имен
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Теперь давайте разберем каждый шаг представленного примера.
## Шаг 1. Инициализируйте проект и добавьте ссылки на задачи
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Здесь мы создаем проект и устанавливаем связи задач между «Задачей 1» и «Задачей 2».
## Шаг 2. Настройка представления диаграммы Ганта
```csharp
var view = (GanttChartView)project.DefaultView;
```
Откройте представление диаграммы Ганта для настройки.
## Шаг 3. Настройте средний уровень шкалы времени
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Настройте средний уровень шкалы времени для отображения недель с определенными метками и выравниванием.
## Шаг 4. Добавьте верхний уровень шкалы времени
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Добавьте верхний уровень шкалы времени для обозначения месяцев.
## Шаг 5. Настройте даты среднего уровня
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Персонализируйте метки месяцев для лучшей визуализации.
## Шаг 6: Установите временной масштаб проекта
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Определите временной график проекта, чтобы контролировать общий график.
## Шаг 7. Сохраните проект с настроенной шкалой времени.
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Сохраните проект с заданными настройками шкалы времени.
## Заключение
В заключение отметим, что настройка уровней шкалы времени в Aspose.Tasks для .NET позволяет обеспечить более индивидуальное и визуально привлекательное представление сроков проекта. Эти шаги позволят вам создать представление диаграммы Ганта, которое точно соответствует вашим потребностям в управлении проектами.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Tasks с другими библиотеками .NET?
Да, Aspose.Tasks легко интегрируется с другими библиотеками .NET, обеспечивая гибкость в вашем стеке разработки.
### Доступна ли временная лицензия для целей тестирования?
 Да, вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/) для оценки.
### Существуют ли дополнительные параметры настройки представления диаграммы Ганта?
Безусловно, Aspose.Tasks предоставляет широкие возможности настройки представления диаграммы Ганта в соответствии с разнообразными требованиями проекта.
### Могу ли я отображать временные шкалы в разных форматах?
Конечно, вы можете изучить различные форматы и стили представления шкалы времени, чтобы лучше всего соответствовать контексту вашего проекта.
### Есть ли форум сообщества для поддержки Aspose.Tasks?
 Да, посетите[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) за поддержку сообщества и обсуждения.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
