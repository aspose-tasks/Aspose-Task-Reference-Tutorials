---
title: Коллекция MS Project Outline Codes в Aspose.Tasks
linktitle: Коллекция структурных кодов в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как собирать структурные коды Microsoft Project с помощью Aspose.Tasks для .NET. Это подробное руководство содержит пошаговые инструкции.
weight: 11
url: /ru/net/outline-code-page-settings/outline-code-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Коллекция MS Project Outline Codes в Aspose.Tasks

## Введение
В этом руководстве мы рассмотрим, как собирать структурные коды Microsoft Project с помощью Aspose.Tasks для .NET. Мы разобьем процесс на пошаговые инструкции, чтобы обеспечить ясность и понимание.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1. Visual Studio: установите Visual Studio в свою систему.
2.  Aspose.Tasks для .NET: Загрузите и установите Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/tasks/net/).
3. Базовое понимание программирования на C#: Знакомство с C# будет полезным.

## Импортировать пространства имен
Во-первых, импортируйте необходимые пространства имен для доступа к функциональности Aspose.Tasks в вашем проекте C#.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Шаг 1. Загрузите файл проекта
 Начните с загрузки файла Microsoft Project с помощью`Project` сорт.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Шаг 2. Соберите коды структуры
Создайте сборщик для сбора структурных кодов задач проекта.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Шаг 3. Перебор задач и кодов структуры
Перебирайте собранные задачи и структурируйте коды, распечатывая их детали.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Шаг 4. Добавьте определение пользовательского кода структуры
Добавьте в проект определение пользовательского кода структуры.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Шаг 5. Создайте и вставьте код структуры
Создайте структурный код и вставьте его в задачу.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Шаг 6: Манипулируйте структурными кодами
При необходимости манипулируйте структурными кодами, например вставляйте, удаляйте или очищайте их.
```csharp
// Пример манипуляции
// ...
// Вставьте код с цифрой 2 в правой позиции
task.OutlineCodes.Insert(2, code2);
// Проверьте, был ли введен код
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Заключение
В этом руководстве мы узнали, как собирать структурные коды Microsoft Project с помощью Aspose.Tasks для .NET. Следуя этим шагам, вы сможете эффективно управлять структурными кодами в своих проектах, повышая организованность и ясность.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks для .NET с другими языками программирования?
О: Да, Aspose.Tasks for .NET в первую очередь ориентирован на платформу .NET, но также обеспечивает поддержку других языков программирования через Aspose.Tasks for Cloud.
### Вопрос: Существуют ли какие-либо ограничения на размер файлов проекта, которые может обрабатывать Aspose.Tasks for .NET?
О: Aspose.Tasks for .NET может эффективно обрабатывать большие файлы Project, но производительность может варьироваться в зависимости от сложности и размера файла.
### Вопрос: Совместим ли Aspose.Tasks для .NET с последними версиями Microsoft Project?
О: Да, Aspose.Tasks for .NET поддерживает различные версии Microsoft Project, включая самые последние.
### Вопрос: Могу ли я настроить формат вывода при работе с Aspose.Tasks для .NET?
О: Конечно, Aspose.Tasks для .NET предоставляет широкие возможности для настройки формата вывода в соответствии с вашими требованиями.
### Вопрос: Где я могу найти дополнительную поддержку или ресурсы для Aspose.Tasks для .NET?
 О: Вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для любой помощи или вопросов, касающихся Aspose.Tasks для .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
