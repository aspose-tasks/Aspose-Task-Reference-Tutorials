---
title: Настройте столбцы диаграммы Ганта с помощью Aspose.Tasks
linktitle: Столбцы диаграммы Ганта в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как настроить столбцы диаграммы Ганта в Aspose.Tasks для .NET для эффективного отображения информации о конкретной задаче.
type: docs
weight: 21
url: /ru/net/tasks-project-management/gantt-chart-columns/
---
## Введение
Диаграммы Ганта — это фундаментальный инструмент управления проектами, обеспечивающий визуальное представление задач, сроков и ресурсов. Aspose.Tasks для .NET предлагает мощные возможности для управления диаграммами Ганта, включая настройку столбцов для отображения конкретной информации о задаче. В этом уроке мы рассмотрим, как работать со столбцами диаграммы Ганта с помощью Aspose.Tasks для .NET.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1.  Установка: Aspose.Tasks для .NET установлен в вашей системе. Если нет, скачайте и установите его с[здесь](https://releases.aspose.com/tasks/net/).
2. Среда разработки .NET: практические знания C# и .NET framework.
3. Образец файла проекта: возьмите образец файла Microsoft Project (`.mpp`) удобно экспериментировать. Если у вас его нет, вы можете создать простой проект в MS Project и сохранить его.

## Импортировать пространства имен
Во-первых, вам необходимо импортировать необходимые пространства имен для работы с Aspose.Tasks for .NET:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Шаг 1. Загрузите файл проекта
 Загрузите файл проекта, используя`Project` класс, предоставленный Aspose.Tasks:
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Шаг 2. Определите столбцы диаграммы Ганта
Определите столбцы, которые вы хотите отображать на диаграмме Ганта. Вы можете указать встроенные поля или создать собственные:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## Шаг 3. Перебор столбцов
Перебирайте определенные столбцы, чтобы получить доступ к их свойствам и отобразить информацию:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## Шаг 4. Сохраните диаграмму Ганта в CSV
Сохраните диаграмму Ганта с определенными столбцами в файл CSV:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Следуя этим шагам, вы сможете эффективно работать со столбцами диаграммы Ганта в Aspose.Tasks для .NET, что позволит вам настраивать и отображать информацию о задачах по мере необходимости.

## Заключение
Освоение манипуляций со столбцами диаграммы Ганта в Aspose.Tasks для .NET открывает безграничные возможности для адаптации визуальных элементов управления проектами к вашим конкретным потребностям. Следуя шагам, описанным в этом руководстве, вы сможете эффективно обрабатывать информацию о задачах и повысить ясность и организацию проекта.
## Часто задаваемые вопросы
### Вопрос: Могу ли я создавать собственные столбцы в Aspose.Tasks для .NET?
О: Да, вы можете определить настраиваемые столбцы для отображения определенных атрибутов задачи в соответствии с требованиями вашего проекта.
### Вопрос: Совместим ли Aspose.Tasks для .NET со всеми версиями файлов Microsoft Project?
О: Aspose.Tasks for .NET поддерживает различные версии файлов Microsoft Project, обеспечивая совместимость в различных средах проектов.
### Вопрос: Как я могу обрабатывать сложные структуры проектов с помощью Aspose.Tasks для .NET?
О: Aspose.Tasks for .NET предоставляет комплексные API и функции для управления сложными структурами проектов, обеспечивая гибкость и масштабируемость.
### Вопрос: Существуют ли какие-либо ограничения на количество столбцов, которые я могу добавить в диаграмму Ганта?
О: Aspose.Tasks for .NET предлагает широкие возможности настройки, позволяющие добавлять значительное количество столбцов в диаграммы Ганта без ограничений.
### Вопрос: Где я могу найти дополнительную поддержку и ресурсы для Aspose.Tasks для .NET?
О: Вы можете изучить документацию, форумы сообщества и каналы поддержки, предоставляемые Aspose.Tasks для .NET, чтобы получить доступ к обширным ресурсам и помощи.