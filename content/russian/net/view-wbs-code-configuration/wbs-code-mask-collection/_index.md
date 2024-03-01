---
title: Освоение масок кода WBS с помощью Aspose.Tasks для .NET
linktitle: Коллекция масок кода WBS в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Улучшите управление проектами с помощью Aspose.Tasks для .NET. В этом подробном руководстве вы научитесь легко создавать, управлять и передавать маски кода WBS.
type: docs
weight: 15
url: /ru/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## Введение
В динамичном мире управления проектами эффективная организация задач имеет решающее значение. Aspose.Tasks для .NET предоставляет мощное решение для простого управления кодами структуры декомпозиции работ проекта (WBS). В этом уроке мы углубимся в коллекцию масок кода WBS, выясним, как их реализовывать и манипулировать ими с помощью Aspose.Tasks для .NET.
## Предварительные условия
Прежде чем мы приступим к этому путешествию по программированию, убедитесь, что у вас есть следующие предварительные условия:
- Практические знания языка программирования C#.
-  Aspose.Tasks для .NET установлен в вашей среде разработки. Если нет, скачайте его[здесь](https://releases.aspose.com/tasks/net/).
- Редактор кода, такой как Visual Studio, для удобного написания кода.
## Импортировать пространства имен
Для начала импортируем необходимые пространства имен:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Инициализация проекта и определение кода WBS.
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Определите маски кода WBS.
Очистите все существующие маски кода и добавьте новые:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Отображение информации о масках кода
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Добавьте задачи в проект
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Получить информацию о задаче
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Манипулирование масками кода
Удалите маску кода и убедитесь, что она удалена:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Скопируйте маски кода в другой проект
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Отображение масок кода в другом проекте
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Добавьте задачи в другой проект
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Отображение кодов WBS в другом проекте
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Заключение
С Aspose.Tasks для .NET управление кодами WBS становится легкой задачей. В этом руководстве рассматриваются создание, манипулирование и передача масок кода WBS, предоставляя вам подробное руководство по улучшению вашего опыта управления проектами.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks для .NET с другими языками программирования?
О: Aspose.Tasks в основном поддерживает языки .NET, но вы можете изучить варианты взаимодействия с другими языками.
### Вопрос: Доступна ли пробная версия Aspose.Tasks для .NET?
 О: Да, вы можете скачать пробную версию.[здесь](https://releases.aspose.com/).
### Вопрос: Как мне обратиться за помощью или сообщить о проблемах с Aspose.Tasks for .NET?
 А: Посетите[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) за поддержку и обсуждения.
### Вопрос: Какова цель кодов WBS в управлении проектами?
Ответ: Коды WBS помогают организовать и структурировать задачи проекта иерархически, обеспечивая системный подход к планированию проекта.
### Вопрос: Могу ли я настроить формат кодов WBS в Aspose.Tasks для .NET?
О: Конечно, вы имеете полный контроль над форматом и структурой кодов WBS, используя Aspose.Tasks для .NET.