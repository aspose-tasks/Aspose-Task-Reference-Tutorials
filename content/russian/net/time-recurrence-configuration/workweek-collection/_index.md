---
title: Настройте рабочие недели в Aspose.Tasks
linktitle: Сбор рабочих недель в Aspose.Задачи
second_title: Aspose.Tasks .NET API
description: Узнайте, как настроить рабочие недели в Aspose.Tasks для .NET. Пошаговое руководство по созданию персонализированных календарей проектов. Скачать сейчас!
type: docs
weight: 17
url: /ru/net/time-recurrence-configuration/workweek-collection/
---
## Введение
Добро пожаловать в наше руководство по созданию индивидуальной рабочей недели с помощью Aspose.Tasks для .NET! В этом пошаговом руководстве мы покажем вам процесс определения персонализированной рабочей недели для календаря вашего проекта. Aspose.Tasks — это мощная библиотека, которая позволяет разработчикам эффективно работать с документами Microsoft Project в своих .NET-приложениях.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
1. Visual Studio: убедитесь, что на вашем компьютере установлена Visual Studio.
2.  Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks. Вы можете найти ссылку для скачивания[здесь](https://releases.aspose.com/tasks/net/).
3. Базовые знания C#: ознакомьтесь с основами языка программирования C#.
## Импортировать пространства имен
В своем проекте C# обязательно импортируйте необходимые пространства имен:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Шаг 1. Создайте проект и календарь
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Шаг 2. Определите индивидуальную рабочую неделю
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Шаг 3. Установите рабочие дни
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Шаг 4. Отображение информации о рабочих неделях
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Это подробное руководство поможет вам эффективно создавать собственные рабочие недели и управлять ими с помощью Aspose.Tasks for .NET.
## Заключение
В заключение, Aspose.Tasks for .NET предоставляет надежное решение для работы с календарями проектов с настраиваемыми рабочими неделями. Следуя этому руководству, вы научились создавать и отображать информацию о пользовательских рабочих неделях в своем проекте.
## Часто задаваемые вопросы
### Могу ли я выделить несколько рабочих недель в одном проекте?
Да, вы можете добавить в календарь проекта несколько пользовательских рабочих недель.
### Как я могу изменить существующие рабочие недели?
 Используйте предоставленный`WorkWeek` Свойства и методы для изменения существующих рабочих недель.
### Совместим ли Aspose.Tasks с .NET Core?
Да, Aspose.Tasks поддерживает .NET Core.
### Могу ли я экспортировать проект с настраиваемыми рабочими неделями в формат файла Microsoft Project?
Безусловно, Aspose.Tasks позволяет сохранять проект в различных форматах, включая Microsoft Project.
### Где я могу получить поддержку по запросам, связанным с Aspose.Tasks?
 Посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) за любую поддержку или помощь.