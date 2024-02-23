---
title: Настройте столбцы представления ресурсов MS Project в Aspose.Tasks
linktitle: Настройка столбцов представления ресурсов в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно настраивать столбцы представления ресурсов MS Project с помощью Aspose.Tasks для .NET. Создавайте индивидуальные представления для лучшего управления проектами.
type: docs
weight: 17
url: /ru/net/resource-risk-analysis/resource-view-columns/
---
## Введение
Aspose.Tasks для .NET — это мощный API, который позволяет разработчикам программно работать с файлами Microsoft Project. Одной из распространенных задач управления проектами является настройка представлений для отображения конкретной информации. В этом уроке мы рассмотрим, как настроить столбцы представления ресурсов MS Project с помощью Aspose.Tasks для .NET.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1.  Aspose.Tasks для библиотеки .NET: вы можете скачать его с сайта[здесь](https://releases.aspose.com/tasks/net/).
2. Файл Microsoft Project: подготовьте образец файла MS Project для тестирования.
3. Среда разработки: среда разработки, созданная с использованием .NET Framework.
## Импортировать пространства имен
Для начала давайте импортируем необходимые пространства имен в наш проект:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Шаг 1. Загрузите файл проекта
Загрузите файл MS Project с помощью API Aspose.Tasks:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Шаг 2. Получите ресурс и определите параметры
Затем получите ресурс, столбцы представления которого вы хотите настроить, и определите параметры сохранения PDF:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Шаг 3. Определите пользовательские столбцы
Теперь определите пользовательские столбцы для представления ресурсов. Вы можете указать различные поля и даже использовать делегаты для пользовательских вычислений:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Шаг 4. Перебор столбцов
Перейдите по определенным столбцам и отобразите их свойства:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Шаг 5. Сохраните настроенное представление
Наконец, установите собственный вид и сохраните его как файл PDF:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Выполнив эти шаги, вы сможете эффективно настроить столбцы представления ресурсов MS Project с помощью Aspose.Tasks для .NET.
## Заключение
Настройка столбцов представления ресурсов MS Project необходима для отображения соответствующей информации, соответствующей потребностям вашего проекта. С Aspose.Tasks для .NET эта задача становится простой и эффективной, позволяя вам без особых усилий создавать индивидуальные представления.
## Часто задаваемые вопросы
### Могу ли я настроить представления для других элементов, помимо ресурсов?
Да, Aspose.Tasks также позволяет настраивать задачи, задания и другие элементы проекта.
### Поддерживает ли Aspose.Tasks сохранение представлений в форматах, отличных от PDF?
Да, вы можете сохранять представления в различных форматах, таких как XLSX, HTML и изображения.
### Можно ли применить форматирование к пользовательскому представлению?
Безусловно, Aspose.Tasks предоставляет широкие возможности форматирования для улучшения внешнего вида ваших индивидуальных представлений.
### Могу ли я динамически обновлять пользовательское представление в зависимости от изменения данных проекта?
Да, вы можете обновлять и повторно создавать пользовательское представление при каждом изменении базовых данных проекта.
### Поддерживает ли Aspose.Tasks кроссплатформенную разработку?
Aspose.Tasks для .NET в первую очередь ориентирован на платформы .NET, но существуют также версии для Java и других платформ.