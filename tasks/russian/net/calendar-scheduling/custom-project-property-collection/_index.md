---
date: 2026-10-15
description: Узнайте, как добавить custom property и управлять custom project properties
  в Aspose.Tasks для .NET, улучшая контроль над project metadata.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Управление Custom Project Property Collection в Aspose.Tasks
og_description: Добавьте custom property в ваши project files с помощью Aspose.Tasks
  для .NET. Это руководство покажет, как управлять custom properties, читать их и
  эффективно добавлять boolean или string значения.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Добавьте custom property с помощью Aspose.Tasks .NET API для проектов
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Как добавить custom property в Aspose.Tasks для .NET
url: /ru/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить пользовательское свойство в Aspose.Tasks для .NET

## Введение

Поддержка пользовательских свойств позволяет хранить метаданные проекта, которые не покрываются встроенными полями. В этом руководстве вы узнаете, как **добавить пользовательское свойство**, прочитать его и управлять всей коллекцией пользовательских свойств с помощью Aspose.Tasks для .NET. К концу вы сможете настраивать файлы проектов с значениями Boolean, DateTime, Double и String, соответствующими вашим бизнес‑правилам.

## Быстрые ответы
- **Можно ли добавить Boolean‑свойство?** Да – используйте `CustomPropertyType.Boolean`.
- **Сколько типов пользовательских свойств поддерживается?** Четыре: Boolean, DateTime, Double, String.
- **Является ли коллекция пользовательских свойств только для чтения?** Она может быть только для чтения, если проект загружен из источника с правами только для чтения.
- **Нужна ли лицензия для использования этой функции?** Временная лицензия подходит для оценки; полная лицензия требуется для продакшн‑использования.
- **Какие версии .NET совместимы?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое пользовательское свойство?

Пользовательское свойство — это определяемое пользователем поле метаданных, которое вы привязываете к объекту Project. Оно позволяет хранить дополнительную информацию, такую как «Уровень риска», «ID клиента» или любой Boolean‑флаг, не покрытый стандартными полями MS‑Project.

## Почему стоит добавлять пользовательские свойства в Aspose.Tasks?

Aspose.Tasks поддерживает **более 50 форматов ввода и вывода** и может работать с проектами, содержащими **до 10 000 задач**, без загрузки всего файла в память. Добавление пользовательских свойств позволяет внедрять бизнес‑критичные данные непосредственно в файл проекта, исключая необходимость внешних баз данных и гарантируя, что данные перемещаются вместе с проектом.

## Требования

- Visual Studio (любая современная версия), установленная на вашем компьютере.  
- Aspose.Tasks for .NET — загрузите его по [ссылке для скачивания](https://releases.aspose.com/tasks/net/).  
- Базовые знания синтаксиса C# и структуры .NET‑проекта.

## Подключение пространств имён

Следующие пространства имён дают доступ к основной модели проекта и API пользовательских свойств.

```csharp
using Aspose.Tasks;
using System;


```

## Как добавить пользовательское свойство в Aspose.Tasks?

Чтобы добавить пользовательское свойство, сначала загрузите проект, затем создайте объект `CustomProperty`, задайте его имя, тип и значение, и наконец добавьте его в коллекцию `CustomProperties` проекта. Эта операция встраивает метаданные непосредственно в файл проекта, а изменения сохраняются при вызове `project.Save(...)`.  

`CustomProperty` представляет собой отдельное определяемое пользователем поле, привязанное к проекту.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Шаг 1: инициализировать проект

`Project` — основной класс, представляющий файл проекта в Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Шаг 2: проверить готовность коллекции пользовательских свойств

`CustomProperties` — коллекция, содержащая все объекты пользовательских свойств проекта.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Шаг 3: добавить пользовательские свойства

Метод `Add` вставляет новое пользовательское свойство в коллекцию проекта.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Шаг 4: доступ к пользовательским свойствам

Коллекция `CustomProperties` реализует `IEnumerable`, позволяя перебрать каждый `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Шаг 5: получить значение пользовательского свойства

Метод `Get` возвращает значение пользовательского свойства по его имени.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Шаг 6: перебрать имена пользовательских свойств

Свойство `Names` предоставляет список всех имен пользовательских свойств в коллекции.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Шаг 7: удалить или очистить пользовательские свойства

Метод `Remove` удаляет конкретное свойство, а `Clear` очищает всю коллекцию.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Распространённые подводные камни и устранение неполадок

- **Коллекция только для чтения** – Если `project.CustomProperties.IsReadOnly` возвращает `true`, убедитесь, что исходный файл не открыт с эксклюзивным доступом только для чтения, либо скопируйте его в место с правами записи перед редактированием.  
- **Несоответствие типов** – Присвоение значения, не соответствующего объявленному `CustomPropertyType`, вызывает `ArgumentException`. Всегда задавайте `Value` после установки правильного `Type`.  
- **Сохранение изменений** – После добавления или удаления свойств вызовите `project.Save("output.mpp")`, чтобы зафиксировать изменения; иначе они останутся только в памяти.

## Часто задаваемые вопросы

**В: Можно ли добавить пользовательские свойства любого типа данных в мой проект с помощью Aspose.Tasks для .NET?**  
О: Да, можно добавлять пользовательские свойства типов Boolean, DateTime, Double и String.

**В: Можно ли перебрать имена пользовательских свойств в Aspose.Tasks для .NET?**  
О: Конечно, вы можете перебрать имена с помощью свойства `Names`.

**В: Как удалить конкретное пользовательское свойство из проекта?**  
О: Вы можете удалить пользовательское свойство по имени, используя метод `Remove`.

**В: Предоставляет ли Aspose.Tasks для .NET поддержку временных лицензий?**  
О: Да, временную лицензию можно получить на сайте Aspose для целей оценки.

**В: Где можно получить поддержку или дополнительную помощь по Aspose.Tasks для .NET?**  
О: Посетите форум Aspose.Tasks [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) для любых вопросов или помощи.

---

**Последнее обновление:** 2026-10-15  
**Тестировано с:** Aspose.Tasks 24.11 для .NET  
**Автор:** Aspose

## Связанные руководства

- [Как читать встроенные свойства проекта с помощью Aspose.Tasks для .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Управление коллекцией атрибутов MS Project в Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Типы пользовательских полей Aspose.Tasks – Календарь и планирование](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}