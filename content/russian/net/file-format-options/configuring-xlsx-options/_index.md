---
title: Настройте параметры MS Project XLSX в Aspose.Tasks для .NET
linktitle: Настройка параметров XLSX в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как настроить параметры MS Project XLSX в Aspose.Tasks для .NET. Настраивайте столбцы, кодировку и многое другое без особых усилий.
type: docs
weight: 11
url: /ru/net/file-format-options/configuring-xlsx-options/
---
## Введение
Microsoft Project (MS Project) — мощный инструмент для управления проектами, а Aspose.Tasks для .NET обеспечивает бесшовную интеграцию для программной работы с файлами MS Project. В этом руководстве мы рассмотрим процесс настройки параметров MS Project XLSX с использованием Aspose.Tasks для .NET.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
### 1. Установлен Aspose.Tasks для .NET.
 Убедитесь, что в вашей среде разработки установлен Aspose.Tasks for .NET. Если нет, вы можете скачать его с сайта[Страница загрузки Aspose.Tasks для .NET](https://releases.aspose.com/tasks/net/).
### 2. Базовое понимание C# и .NET Framework.
Для изучения этого руководства необходимо знание языка программирования C# и платформы .NET.
### 3. Файл проекта Microsoft.
Подготовьте файл Microsoft Project (MPP), который вы хотите настроить и сохранить как файл XLSX.

## Импорт пространств имен
Для начала импортируйте необходимые пространства имен:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Шаг 1. Загрузите проект
```csharp
var project = new Project("YourProjectFile.mpp");
```
Загрузите файл Microsoft Project, который хотите настроить.
## Шаг 2. Определите XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Создайте экземпляр`XlsxOptions` чтобы настроить параметры сохранения в формате XLSX.
## Шаг 3. Добавьте столбцы диаграммы Ганта
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Добавьте в параметры нужные столбцы диаграммы Ганта.
## Шаг 4. Добавьте столбцы представления ресурсов
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Включите в параметры нужные столбцы для представления ресурсов.
## Шаг 5. Добавьте столбцы представления назначений
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Добавьте нужные столбцы для представления назначения в параметрах.
## Шаг 6: Установите кодировку
```csharp
options.Encoding = Encoding.Unicode;
```
Установите кодировку выходного файла.
## Шаг 7. Сохраните проект в формате XLSX.
```csharp
project.Save("OutputFile.xlsx", options);
```
Сохраните проект с настроенными параметрами в виде файла XLSX.

## Заключение
В этом руководстве мы узнали, как настроить параметры MS Project XLSX с помощью Aspose.Tasks для .NET. Выполнив эти шаги, вы сможете настроить выходной формат в соответствии со своими требованиями, повысив гибкость и удобство рабочего процесса управления проектами.
## Часто задаваемые вопросы

### Вопрос: Могу ли я отдельно настроить разные столбцы для диаграммы Ганта, представления ресурсов и представления назначений?

О: Да, вы можете настроить столбцы независимо для каждого представления, используя Aspose.Tasks для .NET.

### Вопрос: Доступна ли пробная версия перед покупкой Aspose.Tasks для .NET?

 О: Да, вы можете загрузить бесплатную пробную версию с сайта[Страница выпусков Aspose.Tasks для .NET](https://releases.aspose.com/).

### Вопрос: Как я могу получить поддержку, если у меня возникнут какие-либо проблемы или вопросы во время внедрения?

 О: Вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) за помощь сообщества и команды поддержки Aspose.

### Вопрос: Могу ли я создавать файлы XLSX с помощью Aspose.Tasks для .NET на платформах, отличных от Windows?

О: Aspose.Tasks for .NET в первую очередь разработан для платформ Windows, но вы можете изучить варианты совместимости для других платформ.

### Вопрос: Существуют ли какие-либо варианты временной лицензии для целей тестирования?

 О: Да, вы можете получить временную лицензию в[Страница временной лицензии Aspose.Tasks](https://purchase.aspose.com/temporary-license/).