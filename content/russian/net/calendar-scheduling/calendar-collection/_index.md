---
title: Управление коллекцией календарей в Aspose.
linktitle: Управление коллекцией календарей в Aspose.
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно управлять коллекциями календарей в Aspose.Tasks для .NET. С легкостью создавайте, изменяйте и манипулируйте календарями.
type: docs
weight: 11
url: /ru/net/calendar-scheduling/calendar-collection/
---
## Введение

В этом уроке мы рассмотрим, как управлять коллекциями календарей в Aspose.Tasks для .NET. Календари играют решающую роль в управлении проектами, определяя рабочие дни, праздники и исключения. Aspose.Tasks предоставляет надежную функциональность для управления календарями в ваших проектах.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1. Visual Studio: установите Visual Studio или любую другую совместимую интегрированную среду разработки для разработки .NET.
2.  Aspose.Tasks для .NET: Загрузите и установите Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/tasks/net/).
3. Базовое понимание C#: Знакомство с языком программирования C# будет полезным.

## Импортировать пространства имен

Для начала давайте импортируем необходимые пространства имен для работы с Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Создание нового календаря

###  Шаг 1. Инициализируйте новый`Project` object.
```csharp
var project = new Project();
```

### Шаг 2. Добавьте календари в коллекцию календарей проекта.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Шаг 3. Перейдите по календарям и отобразите их названия.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Замена календаря новым календарем

### Шаг 1: Загрузите существующий проект.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Шаг 2. Удалите существующий календарь (если он существует).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Шаг 3. Добавьте новый календарь.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Получение календаря по имени или идентификатору

### Шаг 1: Загрузите проект.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Шаг 2. Получите календари по названию или UID.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Шаг 3. Отобразите сведения о календаре.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Перебор календарей

### Шаг 1: Загрузите проект.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Шаг 2. Получите количество календарей.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Шаг 3. Переберите коллекцию календарей и отображаемые имена.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Создание стандартного календаря

### Шаг 1: Инициализируйте новый проект.
```csharp
var project = new Project();
```

### Шаг 2. Определите новый календарь и сделайте его стандартным.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Шаг 3: Сохраните проект.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Заключение

Управление коллекциями календарей в Aspose.Tasks для .NET необходимо для эффективного управления проектами. Благодаря предоставленным функциям вы можете эффективно создавать, изменять и манипулировать календарями в соответствии с требованиями вашего проекта.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я создавать собственные рабочие дни в Aspose.Tasks?

О1: Да, вы можете создавать собственные рабочие дни, добавляя исключения в календари.

### Вопрос 2. Можно ли импортировать календари из файлов Microsoft Project?

О2: Абсолютно, Aspose.Tasks поддерживает импорт календарей из файлов Microsoft Project.

### Вопрос 3. Как удалить из проекта определенный календарь?

О3: Вы можете удалить календарь, получив его из коллекции, а затем вызвав`Remove` метод.

### Вопрос 4: Поддерживает ли Aspose.Tasks экспорт календарей в разные форматы?

О4: Да, Aspose.Tasks позволяет экспортировать календари в различные форматы, такие как XML, MPP и т. д.

### Вопрос 5. Могу ли я настроить рабочее время для определенных дней в календаре?

О5: Конечно, вы можете определить рабочее время для отдельных дней, используя исключения в календаре.