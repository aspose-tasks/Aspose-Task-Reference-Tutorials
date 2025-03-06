---
title: Настройте параметры просмотра страницы MS Project в Aspose.Tasks
linktitle: Настройка параметров просмотра страниц в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как настроить параметры просмотра страниц в Aspose.Tasks для .NET, чтобы адаптировать формат печати документов Microsoft Project.
weight: 21
url: /ru/net/outline-code-page-settings/page-view-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Настройте параметры просмотра страницы MS Project в Aspose.Tasks

## Введение
Microsoft Project — мощный инструмент для управления проектами, но иногда вам необходимо настроить способ просмотра и печати вашего проекта. С помощью Aspose.Tasks для .NET вы можете легко настроить параметры просмотра страниц в соответствии с вашими конкретными требованиями. В этом уроке мы шаг за шагом проведем вас через этот процесс.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1.  Aspose.Tasks для .NET: убедитесь, что вы загрузили и установили библиотеку Aspose.Tasks для .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/tasks/net/).
2. Файл Microsoft Project: подготовьте файл Microsoft Project, для которого вы хотите настроить параметры просмотра страницы.

## Импортировать пространства имен
Во-первых, вам необходимо импортировать необходимые пространства имен для работы с Aspose.Tasks в вашем .NET-проекте.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Шаг 1. Загрузите файл проекта
 Начните с загрузки файла Microsoft Project в экземпляр`Project` сорт.
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Шаг 2. Установите количество первых столбцов
Укажите количество первых столбцов, которые будут напечатаны на всех страницах.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## Шаг 3. Распечатайте заметки
Выберите, печатать ли заметки вместе с проектом.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Шаг 4. Подгоните временную шкалу к концу страницы
Решите, следует ли размещать шкалу времени в конце страницы при печати.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Шаг 5. Распечатайте все столбцы листа
Укажите, следует ли печатать все столбцы листа представления.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Шаг 6. Распечатайте пустые страницы
Выберите, печатать ли пустые страницы представления.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Шаг 7. Распечатайте первые столбцы на всех страницах
Укажите, следует ли печатать указанное количество первых столбцов на всех страницах.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Шаг 8. Сохраните проект с настроенными настройками.
Наконец, сохраните проект с настроенными параметрами просмотра страницы, указав выходной формат, например PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## Заключение
Настройка параметров просмотра страниц Microsoft Project в Aspose.Tasks для .NET проста и позволяет настроить формат печати в соответствии с вашими потребностями. Следуя шагам, описанным в этом руководстве, вы можете быть уверены, что документы вашего проекта представлены именно так, как требуется.
## Часто задаваемые вопросы
### Вопрос: Могу ли я настроить параметры просмотра страниц для других форматов файлов, кроме PDF?
О: Да, Aspose.Tasks поддерживает различные форматы файлов для сохранения проектов, включая XLSX, MPP и HTML.
### Вопрос: Существуют ли какие-либо ограничения на количество столбцов, которые я могу напечатать?
О: Aspose.Tasks позволяет вам настроить количество печатаемых столбцов в соответствии с вашими требованиями.
### Вопрос: Могу ли я применить разные настройки просмотра страниц для разных проектов?
О: Да, вы можете настроить параметры просмотра страниц независимо для каждого файла проекта, с которым работаете.
### Вопрос: Совместим ли Aspose.Tasks со всеми версиями Microsoft Project?
О: Aspose.Tasks обеспечивает совместимость с Microsoft Project 2003 и более поздними версиями.
### Вопрос: Где я могу найти дополнительную помощь или поддержку для Aspose.Tasks?
 О: Вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для любых вопросов или проблем, с которыми вы столкнулись во время использования.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
