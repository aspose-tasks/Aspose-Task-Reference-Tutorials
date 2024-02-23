---
title: Сохранение файлов проекта MS в различных форматах в Aspose.Tasks
linktitle: Сохранение файлов в различных форматах в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как сохранять файлы MS Project в различных форматах с помощью Aspose.Tasks для .NET. Простые шаги для эффективного управления проектами.
type: docs
weight: 17
url: /ru/net/rate-recurring-tasks/save-file-formats/
---
## Введение
В этом уроке мы рассмотрим, как сохранять файлы Microsoft Project в различных форматах с помощью Aspose.Tasks для .NET. Aspose.Tasks — это мощный API, который позволяет разработчикам программно манипулировать файлами проекта и управлять ими.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1.  Aspose.Tasks для .NET: Загрузите и установите Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/tasks/net/).
2. Среда разработки: настройте среду разработки .NET, например Visual Studio.
3. Базовое понимание C#: Знакомство с языком программирования C# будет полезным.

## Импортировать пространства имен
Обязательно импортируйте необходимые пространства имен в начало файла C#:
```csharp

using Aspose.Tasks.Saving;
```
## Шаг 1. Создайте объект проекта
Сначала создайте объект Project и загрузите файл Microsoft Project.
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Шаг 2. Сохраните проект в формате CSV.
Теперь сохраним проект в формате CSV. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Шаг 3. Изучите другие форматы
 Aspose.Tasks поддерживает различные форматы сохранения файлов проекта, такие как XML, PDF, XLSX и другие. Вы можете изучить эти форматы, просто изменив`SaveFileFormat` параметр в`Save` метод.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Следуя этим шагам, вы сможете легко сохранять файлы Microsoft Project в различных форматах с помощью Aspose.Tasks для .NET.

## Заключение
В этом уроке мы узнали, как сохранять файлы MS Project в разных форматах с помощью Aspose.Tasks для .NET. Aspose.Tasks упрощает процесс программного управления файлами проекта, предлагая разработчикам гибкость и эффективность.
## Часто задаваемые вопросы
### Вопрос: Совместим ли Aspose.Tasks со всеми версиями Microsoft Project?
О: Aspose.Tasks поддерживает форматы Microsoft Project 2003 XML, Microsoft Project 2007 MPP и Microsoft Project 2010 MPP.
### Вопрос: Могу ли я попробовать Aspose.Tasks перед покупкой?
 О: Да, вы можете загрузить бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).
### Вопрос: Как я могу получить поддержку Aspose.Tasks?
 О: Вы можете получить поддержку на форуме сообщества Aspose.Tasks.[здесь](https://forum.aspose.com/c/tasks/15).
### Вопрос: Доступны ли временные лицензии для Aspose.Tasks?
 О: Да, временные лицензии доступны для ознакомительных целей. Вы можете получить один[здесь](https://purchase.aspose.com/temporary-license/).
### Вопрос: Какова цена Aspose.Tasks?
 О: Информацию о ценах можно найти на странице покупки Aspose.Tasks.[здесь](https://purchase.aspose.com/buy).