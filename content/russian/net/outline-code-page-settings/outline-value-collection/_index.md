---
title: Управляйте значениями структуры проекта MS с помощью Aspose.Tasks
linktitle: Сбор значений Outline в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как управлять значениями структуры в файлах Microsoft Project с помощью Aspose.Tasks для .NET. Пошаговое руководство с примерами кода.
type: docs
weight: 17
url: /ru/net/outline-code-page-settings/outline-value-collection/
---
## Введение
Aspose.Tasks для .NET предоставляет полный набор функций для взаимодействия с файлами Microsoft Project. Одной из таких функций является возможность управлять контурными значениями внутри проекта. В этом уроке мы рассмотрим, как собирать и манипулировать значениями структуры с помощью Aspose.Tasks для .NET.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1.  Aspose.Tasks для .NET: Вы можете скачать библиотеку с сайта[здесь](https://releases.aspose.com/tasks/net/).
2. Среда разработки: убедитесь, что у вас установлена подходящая IDE, например Visual Studio.
3. Базовые знания C#: Знакомство с языком программирования C# будет преимуществом.
## Импортировать пространства имен
В файл кода C# импортируйте необходимые пространства имен для доступа к классам и методам Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

```
Разобьем приведенный пример на несколько этапов:
## Шаг 1. Загрузите файл проекта
 Во-первых, инициализируйте`Project` объект, загрузив существующий файл Microsoft Project:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Шаг 2. Очистите существующие значения структуры
Затем удалите все существующие значения контура из проекта:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Шаг 3. Определите новый код структуры
Теперь определите новый код структуры с описанием и значением:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Шаг 4. Обновите значение структуры
Обновите значение кода структуры:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Шаг 5. Перебор значений структуры
Переберите значения контура и распечатайте их детали:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Шаг 6. Манипулируйте значениями структуры
Выполняйте такие операции, как удаление, вставка и копирование значений структуры по мере необходимости:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Заключение
В этом уроке мы узнали, как работать со значениями структуры в файлах Microsoft Project с помощью Aspose.Tasks для .NET. Следуя предоставленным шагам, вы сможете эффективно управлять контурными значениями в своих проектах, обеспечивая больший контроль и гибкость.
## Часто задаваемые вопросы
### Вопрос: Могу ли я одновременно манипулировать несколькими структурными кодами?
О: Да, вы можете определять и манипулировать несколькими структурными кодами в рамках проекта с помощью Aspose.Tasks.
### Вопрос: Совместим ли Aspose.Tasks с различными версиями файлов Microsoft Project?
О: Да, Aspose.Tasks поддерживает различные версии файлов Microsoft Project, включая форматы MPP и XML.
### Вопрос: Как обрабатывать ошибки при работе со значениями структуры?
О: Вы можете реализовать механизмы обработки ошибок, такие как блоки try-catch, чтобы корректно управлять исключениями.
### Вопрос: Могу ли я настроить внешний вид контурных значений в своем проекте?
О: Да, Aspose.Tasks предоставляет обширные API для настройки внешнего вида и поведения контурных значений в соответствии с вашими требованиями.
### Вопрос: Где я могу найти дополнительные ресурсы и поддержку для Aspose.Tasks?
 О: Вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) за поддержку сообщества и изучить[документация](https://reference.aspose.com/tasks/net/) для получения подробной информации об API и функциях.