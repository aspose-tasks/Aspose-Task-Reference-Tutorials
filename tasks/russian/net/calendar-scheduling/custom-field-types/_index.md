---
date: 2026-07-19
description: Узнайте, как добавить пользовательские типы полей в Aspose.Tasks для
  .NET с пошаговым кодом, предварительными требованиями и часто задаваемыми вопросами.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Пользовательские типы полей в Aspose.Tasks
og_description: Узнайте, как добавить пользовательские типы полей в Aspose.Tasks для
  .NET. Следуйте этому пошаговому руководству, чтобы эффективно создавать, определять
  и использовать расширенные атрибуты.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Как добавить пользовательские типы полей в Aspose.Tasks для .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Как добавить пользовательские типы полей в Aspose.Tasks для .NET
url: /ru/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить пользовательские типы полей в Aspose.Tasks

## Введение

В этом учебнике вы узнаете, **как добавить пользовательские поля** в файл Microsoft Project с помощью Aspose.Tasks для .NET. Пользовательские поля позволяют хранить дополнительную информацию — например, оценки риска, коды отделов или пользовательские заметки — непосредственно в задачах, ресурсах или самом проекте. Мы пройдём весь процесс, от настройки среды до определения, добавления и проверки пользовательского текстового поля.

## Быстрые ответы
- **Что такое пользовательское поле?** Пользовательский столбец, который может содержать текст, числа, даты или флаги в задачах/ресурсах.  
- **Какой класс определяет пользовательское поле?** `ExtendedAttributeDefinition`.  
- **Могу ли я добавить пользовательское поле в существующий проект?** Да — загрузите проект, создайте определение, затем добавьте его в коллекцию.  
- **Нужна ли лицензия для Aspose.Tasks?** Лицензия требуется для продакшн‑использования; бесплатная trial‑версия подходит для оценки.  
- **Поддерживаемые версии .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что означает «как добавить пользовательское поле» в Aspose.Tasks?
**How to add custom field** относится к процессу создания `ExtendedAttributeDefinition` и привязки его к коллекции `ExtendedAttributes` проекта. Это позволяет хранить дополнительный метаданные, которые не входят в стандартную схему Project. Их можно использовать для задач, ресурсов или самого проекта, позволяя фиксировать информацию, такую как уровни риска, коды отделов или пользовательские заметки, недоступные в полях по умолчанию.

## Зачем использовать пользовательские поля в управлении проектами?
Aspose.Tasks поддерживает **более 50 встроенных типов расширенных атрибутов** и позволяет определять **неограниченное количество пользовательских полей** без значительного увеличения размера файла. Используя пользовательские поля, вы можете:  
Эти поля отображаются как дополнительные столбцы в Microsoft Project и могут использоваться в формулах, отчётах и фильтрах. Они хранятся внутри файла проекта и перемещаются вместе с ним, обеспечивая сохранность пользовательских данных в последующих инструментах.

## Предварительные требования

### 1. Установлен Visual Studio
Убедитесь, что Visual Studio (2019 или новее) установлен на вашем компьютере. Вы можете скачать его с сайта Microsoft.

### 2. Aspose.Tasks для .NET
Добавьте пакет Aspose.Tasks NuGet в ваш проект. Скачайте последнюю версию по ссылке [here](https://releases.aspose.com/tasks/net/).

### 3. Базовые знания C#
Вы должны быть уверены в синтаксисе C#, классах и структуре .NET‑проекта.

## Импорт пространств имён

`Project`, `ExtendedAttributeDefinition` и связанные перечисления находятся в пространстве имён `Aspose.Tasks`. Импортируйте его в начале вашего файла:

Пространство имён `Aspose.Tasks` предоставляет все базовые типы для работы с файлами Microsoft Project.

```csharp

```

## Как добавить пользовательское поле в проект?

Загрузите существующий проект, создайте определение пользовательского поля и добавьте его в коллекцию расширенных атрибутов проекта — всё в три лаконичных шага. Этот шаблон работает для задач, ресурсов и самого проекта, гарантируя сохранение пользовательского поля при сохранении файла.

### Шаг 1: Создать объект Project
`Project` — это объект верхнего уровня Aspose.Tasks, представляющий один файл Project в памяти. При создании он загружает файл и предоставляет доступ к задачам, ресурсам и расширенным атрибутам.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Шаг 2: Определить пользовательское поле
`ExtendedAttributeDefinition` описывает новый столбец. В этом примере мы создаём пользовательское поле типа **Text** для задач и задаём ему псевдоним «MyText». Значение перечисления `ExtendedAttributeTask.Text1` указывает Aspose.Tasks, где хранить значение.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Шаг 3: Добавить определение пользовательского поля в проект
Коллекция `ExtendedAttributes` проекта содержит все определения пользовательских полей. Добавление определения делает его доступным для каждой задачи в проекте.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Распространённые проблемы и решения
- **Поле не отображается в интерфейсе MS Project** – Убедитесь, что установлено свойство `Alias`; MS Project отображает псевдоним как заголовок столбца.  
- **При сохранении возникает исключение** – Проверьте, что файл проекта не является только для чтения и у вас есть действительная лицензия.  
- **Значения пользовательского поля теряются после перезагрузки** – Убедитесь, что вызываете `project.Save("output.mpp")` после назначения значений задачам.

## Часто задаваемые вопросы

**В: Могу ли я использовать Aspose.Tasks с другими фреймворками .NET?**  
О: Да, Aspose.Tasks работает с .NET Framework, .NET Core и .NET 5/6/7.

**В: Подходит ли Aspose.Tasks для корпоративных приложений?**  
О: Абсолютно. Он поддерживает обработку проектов с **до 10 000 задач** и может работать в многопоточных серверных средах.

**В: Поддерживает ли Aspose.Tasks несколько форматов файлов проектов?**  
О: Да — Aspose.Tasks читает и записывает форматы MPP, XML, HTML и CSV, охватывая **все основные версии Microsoft Project**.

**В: Можно ли управлять данными ресурсов с помощью Aspose.Tasks?**  
О: Да, вы можете добавлять, обновлять и удалять ресурсы, а также назначать им пользовательские поля.

**В: Есть ли сообщество пользователей Aspose.Tasks?**  
О: Да, вы можете посетить [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15), чтобы общаться с другими пользователями и получать поддержку от команды Aspose.

---

**Последнее обновление:** 2026-07-19  
**Тестировано с:** Aspose.Tasks 24.12 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные учебные материалы

- [Мастер определения расширенных атрибутов MS Project в Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Работа с расширенными атрибутами MS Project с помощью Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Интеграция Field Helper MS Project в Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}