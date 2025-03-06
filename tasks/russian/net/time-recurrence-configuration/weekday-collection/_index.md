---
title: Освоение будней в Aspose.Tasks
linktitle: Коллекция будних дней в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Откройте для себя возможности Aspose.Tasks для .NET, позволяющие легко управлять буднями. Настраивайте рабочие дни, удаляйте выходные и с легкостью создавайте специализированные календари.
weight: 11
url: /ru/net/time-recurrence-configuration/weekday-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Освоение будней в Aspose.Tasks

## Введение
Aspose.Tasks для .NET — это мощная библиотека, которая облегчает эффективное манипулирование данными управления проектами. В этом уроке мы рассмотрим коллекцию дней недели в Aspose.Tasks, которая позволит вам настраивать рабочие дни, удалять выходные и создавать специализированные календари в соответствии с требованиями вашего проекта. Независимо от того, являетесь ли вы опытным разработчиком или новичком, это пошаговое руководство проведет вас через процесс работы с будними днями в Aspose.Tasks для .NET.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:
-  Установите библиотеку Aspose.Tasks для .NET. Вы можете скачать его с сайта[Страница загрузки Aspose.Tasks для .NET](https://releases.aspose.com/tasks/net/).
- Знание языка программирования C#.
- Интегрированная среда разработки (IDE), такая как Visual Studio.
## Импортировать пространства имен
Начните с импорта необходимых пространств имен в проект C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Шаг 1. Создайте экземпляр проекта
Инициализируйте новый проект Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Шаг 2. Доступ к календарю
Получите календарь проекта:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## Шаг 3. Настройте будние дни
Очистите существующие дни недели и установите рабочие дни по умолчанию:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Аналогично добавьте остальные дни недели...
```
## Шаг 4. Добавьте рабочее время
Добавьте рабочее время для определенных дней недели:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Шаг 5. Отображение информации календаря
Вывод данных календаря на консоль:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Отображение каждого дня недели и рабочего времени...
```
## Шаг 6: Удалите выходные
Удалить субботу и воскресенье из будних дней:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Шаг 7. Отображение обновленного рабочего времени
Вывод обновленного рабочего времени после удаления выходных:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Отображать каждый обновленный день недели и рабочее время...
```
## Шаг 8. Создайте 24-часовой календарь
Создайте 24-часовой календарь и скопируйте дни недели:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Заключение
В этом руководстве мы рассмотрели мощные возможности Aspose.Tasks для .NET по управлению днями недели в календарях проектов. Aspose.Tasks упрощает процесс, предлагая гибкость и контроль в управлении проектами: от настройки рабочих дней до создания специализированных 24-часовых календарей.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks для .NET с другими языками программирования?
О: Aspose.Tasks в основном поддерживает языки .NET, но также предлагает версии для Java.
### Вопрос: Существует ли бесплатная пробная версия Aspose.Tasks для .NET?
 О: Да, вы можете загрузить бесплатную пробную версию с сайта[Страница релизов Aspose.Tasks](https://releases.aspose.com/).
### Вопрос: Как я могу получить поддержку Aspose.Tasks для .NET?
 А: Посетите[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для поддержки сообщества или рассмотрите возможность приобретения плана поддержки.
### Вопрос: Где я могу найти подробную документацию по Aspose.Tasks для .NET?
 О: Обратитесь к[Документация Aspose.Tasks для .NET](https://reference.aspose.com/tasks/net/) для получения подробной информации.
### Вопрос: Как получить временную лицензию на Aspose.Tasks для .NET?
 О: Вы можете приобрести временную лицензию на сайте[страница временной лицензии](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
