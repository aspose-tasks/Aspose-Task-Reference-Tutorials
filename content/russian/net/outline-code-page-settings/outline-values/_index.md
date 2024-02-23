---
title: Освоение значений структуры проекта MS с помощью Aspose.Tasks
linktitle: Управление значениями Outline в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно управлять значениями структуры MS Project с помощью Aspose.Tasks для .NET. С легкостью настраивайте контуры проектов.
type: docs
weight: 16
url: /ru/net/outline-code-page-settings/outline-values/
---
## Введение
В этом руководстве мы рассмотрим, как управлять значениями структуры Microsoft Project с помощью библиотеки Aspose.Tasks для .NET. С помощью Aspose.Tasks вы можете легко манипулировать кодами структуры, создавать новые значения схемы и настраивать схемы проекта в соответствии с вашими требованиями.
## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующее:
1.  Установка Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/tasks/net/).
2. Среда разработки. Убедитесь, что у вас настроена среда разработки, например Visual Studio, с совместимостью с .NET Framework.
3. Базовое понимание программирования на C#: ознакомьтесь с основами языка программирования C#, поскольку мы будем использовать C# для работы с библиотекой Aspose.Tasks.

## Импортировать пространства имен
Начните с импорта необходимых пространств имен в ваш код C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Шаг 1. Загрузите файл проекта
```csharp
// Путь к каталогу документов.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
На этом шаге инициализируется новый объект Project и загружается файл Microsoft Project из указанного каталога.
## Шаг 2. Определите определения общего кода
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Здесь мы определяем два объекта OutlineCodeDefinition и добавляем их в коллекцию OutlineCodes проекта.
## Шаг 3: Определите контурную маску
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
На этом шаге устанавливается OutlineMask для определения структурного кода.
## Шаг 4. Создайте контурные значения
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
На этом этапе мы создаем два объекта OutlineValue и устанавливаем их свойства, такие как значение, идентификатор значения, тип, описание и состояние свертывания.

## Заключение
Управление значениями структуры MS Project с помощью Aspose.Tasks для .NET является простым благодаря предоставляемым функциям. Следуя шагам, описанным в этом руководстве, вы сможете эффективно манипулировать кодами и значениями структуры, чтобы настроить схемы проекта в соответствии с вашими потребностями.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks с другими платформами .NET?
О: Да, Aspose.Tasks совместим с различными платформами .NET, обеспечивая гибкость вашей среды разработки.
### Вопрос: Доступна ли пробная версия для Aspose.Tasks?
 О: Да, вы можете получить доступ к бесплатной пробной версии Aspose.Tasks по адресу[здесь](https://releases.aspose.com/).
### Вопрос: Как я могу получить поддержку Aspose.Tasks?
 О: Для поддержки и помощи вы можете посетить форум Aspose.Tasks.[здесь](https://forum.aspose.com/c/tasks/15).
### Вопрос: Могу ли я приобрести временную лицензию для Aspose.Tasks?
 О: Да, вы можете приобрести временную лицензию для Aspose.[здесь](https://purchase.aspose.com/temporary-license/).
### Вопрос: Где я могу найти подробную документацию по Aspose.Tasks?
 О: Вы можете обратиться к доступной подробной документации.[здесь](https://reference.aspose.com/tasks/net/).