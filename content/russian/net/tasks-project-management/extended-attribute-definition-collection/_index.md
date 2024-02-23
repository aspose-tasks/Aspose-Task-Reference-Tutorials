---
title: Мастер определений расширенных атрибутов MS Project в Aspose.Tasks
linktitle: Коллекция определений расширенных атрибутов в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как управлять определениями расширенных атрибутов в Microsoft Project с помощью Aspose.Tasks для .NET. Настраивайте и улучшайте данные вашего проекта без особых усилий.
type: docs
weight: 14
url: /ru/net/tasks-project-management/extended-attribute-definition-collection/
---
## Введение
В этом руководстве мы рассмотрим, как работать с расширенными определениями атрибутов в Microsoft Project с использованием Aspose.Tasks для .NET. Расширенные атрибуты предлагают гибкий способ настройки и улучшения данных проекта, позволяя пользователям добавлять дополнительные поля помимо стандартных, предусмотренных по умолчанию. С помощью Aspose.Tasks вы можете легко управлять этими расширенными атрибутами, чтобы адаптировать свои потребности в управлении проектами.
## Предварительные условия
Прежде чем продолжить, убедитесь, что у вас установлены следующие необходимые компоненты:
- [.NET Framework](https://dotnet.microsoft.com/download)
-  Aspose.Tasks для библиотеки .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/tasks/net/).

## Импортировать пространства имен
Во-первых, вам необходимо импортировать необходимые пространства имен для доступа к классам и методам Aspose.Tasks в вашем проекте .NET. Следуй этим шагам:
## Шаг 1. Откройте проект .NET.
Откройте проект .NET в предпочитаемой вами интегрированной среде разработки, например Visual Studio.
## Шаг 2. Добавьте пространство имен Aspose.Tasks
Добавьте следующую строку в начало файла кода, чтобы импортировать пространство имен Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Теперь давайте разобьем предоставленные примеры кода на несколько шагов для полного понимания:
## Шаг 1. Загрузите файл проекта.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Шаг 2. Очистите существующие определения расширенных атрибутов (необязательно).
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Шаг 3. Создайте и добавьте определение расширенного атрибута для задачи.
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Шаг 4. Перебор расширенных атрибутов задачи
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Шаг 5. Создайте и добавьте определение расширенного атрибута для ресурса.
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Шаг 6. Вставьте определение расширенного атрибута ресурса.
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Шаг 7. Удаление расширенного атрибута по индексу
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Заключение
В этом руководстве мы рассмотрели основы работы с расширенными определениями атрибутов в Microsoft Project с использованием Aspose.Tasks для .NET. Выполнив эти шаги, вы сможете эффективно управлять расширенными атрибутами и настраивать их в соответствии с требованиями управления проектами.
## Часто задаваемые вопросы
### Вопрос: Могу ли я изменить существующие определения расширенных атрибутов?
О: Да, вы можете изменить существующие определения расширенных атрибутов или создать новые в соответствии с вашими потребностями.
### Вопрос: Поддерживаются ли расширенные атрибуты во всех версиях Microsoft Project?
О: Да, расширенные атрибуты поддерживаются в большинстве версий Microsoft Project, включая последние.
### Вопрос: Могу ли я использовать расширенные атрибуты для расчета пользовательских полей?
О: Конечно, расширенные атрибуты можно использовать для расчета настраиваемых полей на основе определенных вами критериев.
### Вопрос: Совместим ли Aspose.Tasks с другими платформами .NET?
О: Aspose.Tasks совместим с различными платформами .NET, обеспечивая гибкость и простоту интеграции.
### Вопрос: Где я могу найти дополнительные ресурсы и поддержку для Aspose.Tasks?
 О: Вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для поддержки и изучения документации[здесь](https://reference.aspose.com/tasks/net/).