---
title: Управление коллекцией атрибутов MS Project в Aspose.Tasks
linktitle: Управление расширенной коллекцией атрибутов в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно управлять расширенными атрибутами MS Project с помощью Aspose.Tasks для .NET. Легко манипулируйте атрибутами задач с помощью пошаговых инструкций.
type: docs
weight: 12
url: /ru/net/tasks-project-management/extended-attribute-collection/
---
## Введение
Вы хотите эффективно управлять расширенными атрибутами MS Project с помощью Aspose.Tasks для .NET? В этом уроке мы шаг за шагом проведем вас через этот процесс. Давайте погрузимся!
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1. Visual Studio: установите Visual Studio в свою систему.
2.  Aspose.Tasks для .NET: Загрузите и установите Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/tasks/net/).
3. Базовые знания C#: ознакомьтесь с основами языка программирования C#.

## Импортировать пространства имен
Начните с импорта необходимых пространств имен в ваш проект:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Шаг 1. Загрузите файл проекта
Сначала загрузите файл MS Project, используя следующий фрагмент кода:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Шаг 2. Доступ к задаче и расширенным атрибутам
Доступ к конкретной задаче и ее расширенным атрибутам:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Шаг 3. Очистите расширенные атрибуты
При необходимости очистите существующие расширенные атрибуты:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Шаг 4. Создайте расширенные определения атрибутов
Создайте определения для новых расширенных атрибутов:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Шаг 5. Перебор расширенных атрибутов задачи
Перебрать расширенные атрибуты задачи:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Шаг 6. Добавьте расширенные атрибуты
Добавьте в задачу новые расширенные атрибуты:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Шаг 7. Работа с расширенными атрибутами
При необходимости выполните операции с расширенными атрибутами.
## Шаг 8. Удаление расширенных атрибутов
Удалить расширенные атрибуты по индексу или условно:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Шаг 9. Скопируйте атрибуты в другую задачу
Скопируйте атрибуты в другую задачу в том же или другом проекте:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Заключение
Управление расширенными коллекциями атрибутов MS Project становится проще с помощью Aspose.Tasks для .NET. Следуя шагам, описанным в этом руководстве, вы сможете эффективно обрабатывать расширенные атрибуты, расширяя свои возможности управления проектами.
## Часто задаваемые вопросы
### Вопрос: Могу ли я управлять расширенными атрибутами в нескольких проектах?
О: Да, вы можете копировать расширенные атрибуты между задачами в разных проектах, используя Aspose.Tasks for .NET.
### Вопрос: Существуют ли ограничения на количество расширенных атрибутов для каждой задачи?
О: Aspose.Tasks for .NET не накладывает никаких ограничений на количество расширенных атрибутов для каждой задачи.
### Вопрос: Могу ли я создавать собственные поля расширенных атрибутов?
А: Абсолютно! Aspose.Tasks для .NET позволяет вам определять собственные расширенные поля атрибутов, адаптированные к требованиям вашего проекта.
### Вопрос: Поддерживает ли Aspose.Tasks для .NET чтение и запись в файлы MS Project различных версий?
О: Да, Aspose.Tasks для .NET поддерживает форматы файлов MS Project в разных версиях.
### Вопрос: Доступна ли пробная версия Aspose.Tasks для .NET?
 О: Да, вы можете загрузить бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).