---
date: 2026-04-13
description: Узнайте, как задавать рабочие часы и управлять коллекциями календарей
  в Aspose.Tasks для .NET. Импортируйте календари из Microsoft Project, удаляйте календарь
  проекта и легко получайте календарь по имени.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Управление коллекцией календарей в Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Установить рабочие часы в коллекции календарей Aspose.Tasks
url: /ru/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Установить рабочие часы в коллекции календарей Aspose.Tasks

В этом руководстве вы узнаете, как **установить рабочие часы** и управлять коллекциями календарей с помощью Aspose.Tasks для .NET. Календари определяют рабочие дни, праздники и исключения, поэтому их освоение позволяет точно контролировать графики проектов. Мы также покажем, как импортировать календари из Microsoft Project, удалить календарь из проекта и получить календарь по имени.

## Быстрые ответы
- **Какой основной класс для календарей?** `Project.Calendars` collection.
- **Как установить рабочие часы?** Create or modify a `Calendar` object and define its `WorkingTime`.
- **Можно ли импортировать календари из Microsoft Project?** Yes – load an MPP file and access its calendars.
- **Как удалить календарь из проекта?** Use `Project.Calendars.Remove(calendar)`.
- **Как получить календарь по имени?** Call `Project.Calendars.GetByName("YourCalendar")`.

## Предварительные требования

1. Visual Studio: Установите Visual Studio или любую другую совместимую IDE для разработки на .NET.  
2. Aspose.Tasks for .NET: Скачайте и установите Aspose.Tasks for .NET с [here](https://releases.aspose.com/tasks/net/).  
3. Базовые знания C#: Знание языка программирования C# будет полезным.

## Импорт пространств имён

Сначала импортируем необходимые пространства имён для работы с Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Создание нового календаря

### Шаг 1: Инициализировать новый объект `Project`.
```csharp
var project = new Project();
```

### Шаг 2: Добавить календари в коллекцию календарей проекта.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Шаг 3: Перебрать календари и вывести их имена.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Как установить рабочие часы для календаря?

Чтобы **установить рабочие часы**, вы изменяете коллекцию `WorkingTime` объекта `Calendar`.  
Например, можно задать стандартный рабочий день с 9 ч. до 17 ч. или добавить пользовательские исключения.  
Код для этого идентичен примерам, показанным позже, когда мы создаём стандартный календарь.

## Замена календаря новым календарем

### Шаг 1: Загрузить существующий проект.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Шаг 2: Удалить существующий календарь (если он существует).  
Это демонстрирует сценарий **remove calendar project**.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Шаг 3: Добавить новый календарь.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Получение календаря по имени или ID

### Шаг 1: Загрузить проект.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Шаг 2: Получить календари по имени или UID.  
Это иллюстрирует операцию **get calendar by name**.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Шаг 3: Показать детали календаря.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Перебор календарей

### Шаг 1: Загрузить проект.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Шаг 2: Получить количество календарей.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Шаг 3: Перебрать коллекцию календарей и вывести их имена.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Создание стандартного календаря

### Шаг 1: Инициализировать новый проект.
```csharp
var project = new Project();
```

### Шаг 2: Определить новый календарь и сделать его стандартным.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Шаг 3: Сохранить проект.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Распространённые проблемы и решения

- **Calendar not found when using `GetByName`** – Убедитесь, что точное имя совпадает с регистром, использованным при добавлении календаря.  
- **Working hours not applied** – После установки `WorkingTime` не забудьте сохранить проект; иначе изменения останутся только в памяти.  
- **Importing calendars from an MPP file fails** – Убедитесь, что исходный файл является действительным файлом Microsoft Project и у вас есть права на чтение.

## Часто задаваемые вопросы

### Q1: Могу ли я создать пользовательские рабочие дни в Aspose.Tasks?
A1: Да, вы можете создать пользовательские рабочие дни, добавив исключения в календари.

### Q2: Можно ли импортировать календари из файлов Microsoft Project?
A2: Конечно, Aspose.Tasks поддерживает импорт календарей из файлов Microsoft Project.

### Q3: Как удалить конкретный календарь из проекта?
A3: Вы можете удалить календарь, получив его из коллекции, а затем вызвав метод `Remove`.

### Q4: Поддерживает ли Aspose.Tasks экспорт календарей в разные форматы?
A4: Да, Aspose.Tasks позволяет экспортировать календари в различные форматы, такие как XML, MPP и т.д.

### Q5: Могу ли я настроить рабочие часы для конкретных дней в календаре?
A5: Конечно, вы можете задать рабочие часы для отдельных дней, используя исключения в календаре.

## Часто задаваемые вопросы

**Q: Как лучше всего установить календарь 24‑часовой смены?**  
A: Создайте новый календарь, очистите существующие записи `WorkingTime` и добавьте один диапазон `WorkingTime` с 00:00 до 24:00 для каждого буднего дня.

**Q: Можно ли скопировать календарь из одного проекта в другой?**  
A: Да — экспортируйте календарь в XML с помощью `project.Save`, а затем импортируйте его в другой проект с помощью `new Project(xmlPath)`.

**Q: Как программно импортировать календари из Microsoft Project?**  
A: Загрузите файл MPP с помощью `new Project("source.mpp")`; календари станут доступны через `project.Calendars`.

**Q: Есть ли ограничение на количество календарей в проекте?**  
A: Практически нет; коллекция может содержать столько календарей, сколько позволяет память, но рекомендуется держать список управляемым для производительности.

**Q: Обновляются ли задачи автоматически при изменении календаря?**  
A: Да — задачи, связанные с календарём, отражают обновлённые рабочие часы после сохранения проекта.

---

**Последнее обновление:** 2026-04-13  
**Тестировано с:** Aspose.Tasks 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}