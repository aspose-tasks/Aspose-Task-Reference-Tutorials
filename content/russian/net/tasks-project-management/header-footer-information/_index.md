---
title: Извлеките информацию верхнего и нижнего колонтитула с помощью Aspose.Tasks
linktitle: Информация верхнего и нижнего колонтитула в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Научитесь извлекать информацию верхнего и нижнего колонтитула из файлов MS Project с помощью Aspose.Tasks для .NET. Простое, эффективное и удобное для разработчиков решение.
type: docs
weight: 29
url: /ru/net/tasks-project-management/header-footer-information/
---
## Введение
Aspose.Tasks для .NET — это мощная библиотека, которая позволяет разработчикам с легкостью манипулировать файлами Microsoft Project. В этом уроке мы научимся получать информацию верхнего и нижнего колонтитула из файлов MS Project с помощью Aspose.Tasks.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1. Visual Studio: установите Visual Studio в свою систему.
2.  Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/tasks/net/).
3. Базовые знания C#: Знакомство с языком программирования C#.

## Импортировать пространства имен
Сначала вам необходимо импортировать необходимые пространства имен в ваш проект C#. Это позволит вам получить доступ к классам и методам, предоставляемым библиотекой Aspose.Tasks.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Шаг 1. Инициализация объекта проекта
 Для начала вам необходимо инициализировать`Project` объект, загрузив существующий файл MS Project.
```csharp
// Путь к каталогу документов.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Шаг 2. Получение информации верхнего и нижнего колонтитула
 После загрузки файла проекта вы можете получить информацию верхнего и нижнего колонтитула, используя команду`PageInfo` свойство.
```csharp
var info = project.DefaultView.PageInfo;
// Информация в заголовке
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Информация в нижнем колонтитуле
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Следуя этим простым шагам, вы можете легко получить информацию верхнего и нижнего колонтитула из файлов MS Project с помощью Aspose.Tasks для .NET.

## Заключение
В этом уроке мы рассмотрели, как извлечь информацию верхнего и нижнего колонтитула из файлов MS Project с помощью Aspose.Tasks для .NET. Эта мощная библиотека упрощает задачу работы с файлами Project в приложениях C#, предоставляя разработчикам надежные инструменты для манипуляций.
### Часто задаваемые вопросы
### Могу ли я изменить информацию верхнего и нижнего колонтитула с помощью Aspose.Tasks?
Да, вы можете изменить информацию верхнего и нижнего колонтитула программно, используя Aspose.Tasks для .NET.
### Поддерживает ли Aspose.Tasks другие форматы файлов проекта, кроме MS Project?
Да, Aspose.Tasks поддерживает различные форматы файлов проектов, включая MPP, XML и MPX.
### Доступна ли бесплатная пробная версия Aspose.Tasks?
 Да, вы можете скачать бесплатную пробную версию Aspose.[здесь](https://releases.aspose.com/).
### Где я могу найти документацию для Aspose.Tasks?
 Вы можете найти документацию для Aspose.Tasks.[здесь](https://reference.aspose.com/tasks/net/).
### Как я могу получить поддержку для Aspose.Tasks?
 Вы можете получить поддержку Aspose.Tasks, посетив[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).