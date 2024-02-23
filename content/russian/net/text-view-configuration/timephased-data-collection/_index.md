---
title: Освоение повременного сбора данных в Aspose.Tasks
linktitle: Сбор повременных данных в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Изучите повременный сбор данных в Aspose.Tasks для .NET. Пошаговое руководство, часто задаваемые вопросы и многое другое. Расширьте свои возможности управления проектами уже сегодня!
type: docs
weight: 15
url: /ru/net/text-view-configuration/timephased-data-collection/
---
## Введение
Вы хотите использовать возможности поэтапных данных в своих .NET-приложениях с помощью Aspose.Tasks? Не смотрите дальше! Это подробное руководство проведет вас через процесс поэтапного сбора данных с помощью Aspose.Tasks для .NET, гарантируя, что вы максимально эффективно используете эту мощную библиотеку.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
1.  Aspose.Tasks для библиотеки .NET: загрузите и установите библиотеку с сайта[Документация Aspose.Tasks .NET](https://reference.aspose.com/tasks/net/).
2. Среда разработки .NET. Убедитесь, что у вас настроена работающая среда разработки .NET.
3. Каталог ваших документов. Замените заполнитель «Каталог ваших документов» во фрагментах кода на путь к каталогу ваших документов.
## Импортировать пространства имен
В вашем проекте .NET начните с импорта необходимых пространств имен для использования функций Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Создайте проект и ресурсы.
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Добавьте задачи в проект
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Установить свойства задачи...
var task2 = project.RootTask.Children.Add("Task 2");
// Установить свойства задачи 2...
```
## 3. Назначьте ресурсы задачам
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Установить свойства назначения...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// Установить свойства назначения 2...
```
## 4. Работа с поэтапными данными
```csharp
// Установить контурный рабочий контур
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Проверьте, доступен ли поэтапный сбор данных только для чтения.
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Очистить сгенерированные повременные данные
assignment.TimephasedData.Clear();
// Создание и добавление повременных данных
var td = new TimephasedData
{
    // Установить свойства поэтапных данных...
};
assignment.TimephasedData.Add(td);
// Добавить список повременных данных
var list = new List<TimephasedData>();
// Добавьте в список дополнительные элементы повременных данных...
assignment.TimephasedData.AddRange(list);
// Фильтрация повременных данных по типу и диапазону дат
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Печать отфильтрованных повременных данных...
```
## 5. Манипулируйте поэтапными данными
```csharp
//Добавьте неправильный элемент данных с фазовой разбивкой, а затем удалите его.
var td4 = new TimephasedData
{
    // Установите неправильные свойства повременных данных...
};
assignment.TimephasedData.Add(td4);
// Удалить неправильный элемент данных с повременной разбивкой
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Перебрать все поэтапные элементы
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Распечатать детали поэтапного элемента...
}
```
## 6. Копирование повременных данных в другое задание
```csharp
// Копирование повременных данных в другое задание
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Преобразование коллекции в простой список
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Удаляйте поэтапные элементы данных один за другим
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Заключение
В заключение, в этом руководстве представлено подробное описание поэтапного сбора данных с использованием Aspose.Tasks для .NET. Следуя этим шагам, вы сможете легко интегрировать эту функцию в свои проекты, обеспечивая эффективный учет времени и управление ресурсами.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Tasks для .NET с другими инструментами управления проектами?
Да, Aspose.Tasks for .NET предназначен для работы с популярными инструментами управления проектами и поддерживает различные форматы файлов.
### Есть ли ограничение на количество ресурсов и задач, которыми я могу управлять с помощью Aspose.Tasks?
Aspose.Tasks обрабатывает проекты разного размера, и нет строгих ограничений на количество ресурсов и задач.
### Как я могу получить поддержку по любым вопросам или вопросам, связанным с Aspose.Tasks для .NET?
 Для получения поддержки посетите[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) Чтобы связаться с сообществом и получить помощь.
### Могу ли я попробовать Aspose.Tasks для .NET перед его покупкой?
 Да, вы можете изучить возможности Aspose.Tasks для .NET, открыв[бесплатная пробная версия](https://releases.aspose.com/).
### Где я могу приобрести лицензию на Aspose.Tasks для .NET?
 Вы можете приобрести лицензию на Aspose.Tasks для .NET.[здесь](https://purchase.aspose.com/buy).