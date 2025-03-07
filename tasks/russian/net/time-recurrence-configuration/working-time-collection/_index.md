---
title: Управление рабочим временем в Aspose.Tasks
linktitle: Сбор рабочего времени в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Изучите возможности Aspose.Tasks for .NET для эффективного управления сроками проекта. Настраивайте календари, устанавливайте рабочее время и с легкостью оптимизируйте свои проекты.
weight: 14
url: /ru/net/time-recurrence-configuration/working-time-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Управление рабочим временем в Aspose.Tasks

## Введение
Вы хотите овладеть искусством управления рабочим временем в Aspose.Tasks для .NET? Не смотрите дальше! В этом пошаговом руководстве мы углубимся в тонкости сбора рабочего времени с помощью Aspose.Tasks, что позволит вам эффективно управлять пользовательскими календарями и оптимизировать сроки вашего проекта.
## Предварительные условия
Прежде чем мы отправимся в это путешествие, убедитесь, что у вас есть следующие предварительные условия:
-  Библиотека Aspose.Tasks для .NET: загрузите и установите библиотеку Aspose.Tasks для .NET из[Страница релиза Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- Рабочая среда: настройте подходящую среду разработки, желательно с использованием .NET-совместимой IDE.
## Импортировать пространства имен
Импортируйте в свой проект необходимые пространства имен для доступа к функциям Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Теперь давайте разобьем руководство на несколько этапов, чтобы обеспечить плавное обучение.
## Шаг 1. Создайте собственный календарь
Начните с создания нового проекта и добавления в него пользовательского календаря:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Шаг 2. Определите рабочие дни
Установите рабочие дни по умолчанию с понедельника по пятницу:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Шаг 3. Настройте рабочее время по субботам
Укажите время работы по субботам:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Шаг 4. Распечатайте субботние рабочие периоды
Распечатайте настроенное рабочее время на субботу:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Шаг 5. Настройте рабочее время воскресенья
Определите рабочее время для воскресенья:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Шаг 6. Распечатайте воскресные рабочие периоды
Распечатайте настроенное рабочее время для воскресенья:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Шаг 7. Добавьте пользовательские дни в календарь
Включите в календарь настроенные субботу и воскресенье:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Шаг 8: Просмотрите рабочее время
Просмотрите рабочее время и отобразите его для каждого дня в календаре:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Теперь, когда вы успешно прошли все этапы, вы готовы использовать возможности Aspose.Tasks для .NET для эффективного управления рабочим временем.
## Заключение
Освоение сбора рабочего времени в Aspose.Tasks дает вам возможность настраивать календари проектов, обеспечивая точное планирование и эффективное использование ресурсов. Погрузитесь в свои проекты с уверенностью, вооружившись знаниями, полученными из этого подробного руководства.
## Часто задаваемые вопросы
### Подходит ли Aspose.Tasks для управления крупномасштабными проектами?
Да, Aspose.Tasks предназначен для работы с проектами разного размера и предоставляет надежные функции для эффективного управления проектами.
### Могу ли я интегрировать Aspose.Tasks с другими библиотеками .NET?
Конечно! Aspose.Tasks легко интегрируется с другими библиотеками .NET, повышая его универсальность и совместимость.
### Как часто обновляется Aspose.Tasks?
 Aspose.Tasks регулярно обновляется, включая новые функции, улучшения и улучшения совместимости. Проверить[страница выпуска](https://releases.aspose.com/tasks/net/) для получения последних обновлений.
### Доступна ли бесплатная пробная версия Aspose.Tasks?
 Да, вы можете изучить Aspose.Tasks с помощью бесплатной пробной версии, посетив[эта ссылка](https://releases.aspose.com/).
### Где я могу получить поддержку для Aspose.Tasks?
 По любым вопросам или помощи посетите[Форум поддержки Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
