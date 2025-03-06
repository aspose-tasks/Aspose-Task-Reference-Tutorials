---
title: Освойте повременную обработку данных с помощью Aspose.Tasks для .NET
linktitle: Обработка повременных данных в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Изучите Aspose.Tasks для .NET, чтобы легко обрабатывать повременные данные, улучшать планирование проектов и оптимизировать управление ресурсами. #Aspose #Задачи #MS Project
weight: 14
url: /ru/net/text-view-configuration/timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Освойте повременную обработку данных с помощью Aspose.Tasks для .NET

## Введение
В мире управления проектами эффективная обработка повременных данных имеет решающее значение для распределения ресурсов, оценки затрат и общего планирования проекта. Aspose.Tasks для .NET предоставляет мощное решение для беспрепятственной работы с пользовательскими повременными данными. Это руководство проведет вас через процесс обработки повременных данных с помощью Aspose.Tasks, что позволит вам оптимизировать управление ресурсами в ваших проектах.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
- Базовое понимание концепций управления проектами.
-  Установлен Aspose.Tasks для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/tasks/net/).
- Редактор кода, например Visual Studio, для реализации предоставленных примеров.
## Импортировать пространства имен
В вашем проекте .NET обязательно импортируйте необходимые пространства имен для использования функций Aspose.Tasks. Добавьте следующие строки в начало файла кода:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Теперь давайте разобьем приведенный пример на несколько шагов, которые помогут вам обрабатывать повременные данные с помощью Aspose.Tasks:
## Шаг 1. Настройте проект
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Здесь мы инициализируем новый проект и устанавливаем для него режим расчета.
## Шаг 2. Определите ресурсы и задачи
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Создайте рабочие и стоимостные ресурсы, а также задачу для моделирования структуры проекта.
## Шаг 3. Назначьте ресурсы задаче
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Назначьте трудовые и стоимостные ресурсы для задачи.
## Шаг 4. Добавьте пользовательские повременные данные
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Аналогичные шаги для назначения затрат
costAssignment.TimephasedData.Clear();
```
Добавьте пользовательские повременные данные для назначений работ и затрат.
## Шаг 5. Отображение повременных данных
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Отображение соответствующей информации о каждой записи повременных данных.
    }
}
```
Наконец, отобразите повременные данные для каждого назначения.
#
## Заключение
Эффективная обработка повременных данных в Aspose.Tasks открывает новые возможности для детального планирования проектов и управления ресурсами. Следуя этому пошаговому руководству, вы научились манипулировать повременными данными для удовлетворения конкретных потребностей ваших проектов.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Tasks для .NET с другими инструментами управления проектами?
Aspose.Tasks в первую очередь предназначен для разработки .NET. Однако его функциональные возможности могут дополнять различные инструменты управления проектами.
### Доступна ли бесплатная пробная версия Aspose.Tasks для .NET?
 Да, вы можете изучить бесплатную пробную версию[здесь](https://releases.aspose.com/).
### Как я могу получить поддержку Aspose.Tasks для .NET?
 Посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для поддержки сообщества.
### Что такое временная лицензия и как ее получить?
 Узнайте о временных лицензиях[здесь](https://purchase.aspose.com/temporary-license/).
### Где я могу найти документацию по Aspose.Tasks для .NET?
 Обратитесь к комплексному[документация](https://reference.aspose.com/tasks/net/) для получения подробной информации.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
