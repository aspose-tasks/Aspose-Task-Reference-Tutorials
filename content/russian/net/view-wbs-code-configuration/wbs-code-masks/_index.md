---
title: Пошаговая настройка кода WBS в Aspose.Tasks .NET
linktitle: Настройка масок кода WBS в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Изучите пошаговую настройку масок кода WBS в проектах .NET с помощью Aspose.Tasks. Расширьте возможности управления проектами без особых усилий.
type: docs
weight: 14
url: /ru/net/view-wbs-code-configuration/wbs-code-masks/
---
## Введение
Aspose.Tasks для .NET — это мощная библиотека, которая позволяет разработчикам эффективно манипулировать данными управления проектами в приложениях .NET. В этом уроке мы рассмотрим процесс настройки масок кода Work Breakdown Structure (WBS) с помощью Aspose.Tasks.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
-  Aspose.Tasks для библиотеки .NET: загрузите и установите библиотеку с сайта[Документация Aspose.Tasks для .NET](https://reference.aspose.com/tasks/net/).
- Среда разработки: убедитесь, что у вас настроена работающая среда разработки .NET.
- Каталог документов: выберите каталог в вашей системе для хранения файлов проекта.
## Импортировать пространства имен
В свой .NET-проект включите необходимые пространства имен для работы с Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Шаг 1. Создайте экземпляр проекта
Начните с создания нового экземпляра проекта:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Шаг 2. Определите определение кода WBS
Настройте определение кода WBS для своего проекта:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Шаг 3. Добавьте маски кода WBS
Определите маски кода WBS и добавьте их в проект:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Шаг 4. Создайте задачи
Добавьте задачи в проект:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Шаг 5: Пересчитать
Пересчитайте проект, чтобы убедиться, что коды WBS применяются правильно:
```csharp
project.Recalculate();
```
## Шаг 6. Отображение информации о маске WBS
Вывести информацию о масках WBS в консоль:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Шаг 7: Сохраните проект
Сохраните проект с добавленными кодами WBS:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Поздравляем! Вы успешно настроили маски кода WBS в своем проекте Aspose.Tasks.
## Заключение
В этом руководстве мы рассмотрели пошаговый процесс настройки масок кода WBS с использованием Aspose.Tasks для .NET. Эта мощная библиотека предоставляет разработчикам простой способ расширить возможности управления проектами в своих .NET-приложениях.

## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Tasks бесплатно?
 Aspose.Tasks предлагает бесплатную пробную версию, которую вы можете скачать.[здесь](https://releases.aspose.com/).
### Где я могу найти дополнительную поддержку?
 Посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для поддержки сообщества.
### Как получить временную лицензию?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Есть ли подробная документация?
 Да, полная документация доступна[здесь](https://reference.aspose.com/tasks/net/).
### Где я могу приобрести Aspose.Tasks?
 Купить Aspose.Tasks[здесь](https://purchase.aspose.com/buy).