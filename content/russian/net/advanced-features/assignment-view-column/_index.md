---
title: Столбец просмотра пользовательских назначений в Aspose.Tasks
linktitle: Столбец просмотра пользовательских назначений в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как добавить столбцы представления настраиваемых назначений в Aspose.Tasks для .NET, чтобы расширить возможности управления проектами.
type: docs
weight: 16
url: /ru/net/advanced-features/assignment-view-column/
---
## Введение

В этом руководстве мы рассмотрим, как добавлять пользовательские столбцы для представлений назначений с помощью Aspose.Tasks для .NET. Пользовательские столбцы обеспечивают гибкость и позволяют отображать дополнительную информацию, соответствующую потребностям управления проектами.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1. Базовые знания языка программирования C#.
2.  Установлена библиотека Aspose.Tasks для .NET. Если нет, то вы можете скачать его[здесь](https://releases.aspose.com/tasks/net/).
3. Интегрированная среда разработки (IDE), например Visual Studio.

## Импортировать пространства имен

Сначала давайте импортируем необходимые пространства имен для доступа к классам и методам, необходимым для создания столбцов представления настраиваемых назначений:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Шаг 1. Загрузите проект

 Для начала загрузите файл проекта, используя`Project` сорт:

```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Шаг 2. Создайте параметры сохранения таблицы

 Далее создайте экземпляр`Spreadsheet2003SaveOptions` что позволяет нам настраивать столбцы представления назначений:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Шаг 3. Определите пользовательский столбец

 Теперь определите свой собственный столбец, создав экземпляр`AssignmentViewColumn`. Этому классу требуются имя столбца, ширина и функция делегата для преобразования данных назначения в текст столбца:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Шаг 4. Добавьте пользовательский столбец в параметры

Добавьте настраиваемый столбец в коллекцию столбцов представления назначения параметров сохранения:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Шаг 5. Повторение назначений

Выполните итерацию каждого назначения ресурсов в проекте и отобразите текст настраиваемого столбца:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## Шаг 6. Сохраните проект с настраиваемыми столбцами

Наконец, сохраните проект со столбцами представления настраиваемых назначений:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Заключение

В этом руководстве мы узнали, как добавлять столбцы представления настраиваемых назначений с помощью Aspose.Tasks для .NET. Пользовательские столбцы обеспечивают гибкость отображения дополнительной информации, адаптированной к требованиям вашего проекта, расширяя возможности управления проектами.

## Часто задаваемые вопросы

### Вопрос 1. Могу ли я добавить несколько настраиваемых столбцов в представление назначения?

 О1: Да, вы можете добавить несколько настраиваемых столбцов, создав дополнительные экземпляры`AssignmentViewColumn` и добавление их в`Columns` коллекция.

### Вопрос 2. Существуют ли предопределенные преобразователи для общих полей назначения?

О2: Да, Aspose.Tasks предоставляет предопределенные преобразователи для общих полей назначения, что упрощает извлечение данных для пользовательских столбцов.

### Вопрос 3. Могу ли я настроить внешний вид настраиваемых столбцов, например форматировать текст или применять стили?

О3: Да, вы можете настроить внешний вид настраиваемых столбцов, изменив такие свойства, как ширина, шрифт и выравнивание.

### Вопрос 4. Можно ли удалить столбцы по умолчанию из представления назначений?

 О4: Да, вы можете удалить столбцы по умолчанию, исключив их из списка.`Columns` коллекцию или установив их ширину в ноль.

### В5: Поддерживает ли Aspose.Tasks экспорт проектов в другие форматы, кроме электронных таблиц с настраиваемыми столбцами?

О5: Да, Aspose.Tasks поддерживает экспорт проектов в различные форматы, такие как PDF, HTML и XML, что обеспечивает универсальные варианты отчетности по проектам.