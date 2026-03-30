---
date: 2026-03-16
description: Узнайте, как комбинировать несколько условий и фильтровать задачи проекта,
  используя расширенную операцию И в Aspose.Tasks для .NET.
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: Как объединить несколько условий с помощью расширенной операции AND в Aspose.Tasks
url: /ru/net/advanced-features/advanced-and-operation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Продвинутая операция AND в Aspose.Tasks

## Introduction

В этом руководстве вы узнаете **как комбинировать несколько условий** с помощью *расширенной операции AND* в Aspose.Tasks для .NET. К концу руководства вы сможете **фильтровать задачи проекта** по нескольким критериям — это необходимо, когда нужно **как фильтровать задачи**, такие как элементы‑итоги, ненулевые записи или пользовательские флаги за один проход.

## Quick Answers
- **Что делает расширенная операция AND?** Она объединяет два или более условия фильтра, так что возвращаются только задачи, удовлетворяющие *всем* критериям.  
- **Какой класс объединяет условия?** `Util.And<T>` (в API доступен как `And<T>`).  
- **Нужна ли специальная лицензия?** Для использования в продакшене требуется обычная лицензия Aspose.Tasks; доступна бесплатная пробная версия.  
- **Можно ли связать более двух условий?** Да — `And<T>` принимает любое количество условий.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## What is “combine multiple conditions” in Aspose.Tasks?

Что означает «комбинировать несколько условий» в Aspose.Tasks?  
Комбинирование нескольких условий означает создание составного фильтра, который одновременно оценивает каждую задачу по нескольким правилам. Такой подход гораздо эффективнее, чем многократное перебирание списка задач, поскольку библиотека применяет логику за один проход.

## Why use the advanced AND operation?

- **Производительность:** Сокращает количество проходов по коллекции задач.  
- **Читаемость:** Делает логику фильтра декларативной и простой в поддержке.  
- **Гибкость:** Можно комбинировать встроенные условия (например, `SummaryCondition`) с пользовательскими предикатами.  

## Prerequisites

Прежде чем начать, убедитесь, что у вас есть:

1. Базовые знания программирования на C#.  
2. Установленный Aspose.Tasks для .NET. Если вы ещё не скачали его, получите его **[здесь](https://releases.aspose.com/tasks/net/)**.  
3. IDE, например Visual Studio (подойдёт любая редакция).  

## Import Namespaces

First, import the namespaces that provide the task model and utility classes:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## Step 1: Initialize Project and Collect Tasks

Мы создадим экземпляр `Project` и используем `ChildTasksCollector` для сбора всех задач в файле. Это демонстрирует **how to use collector** для получения плоского списка задач.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Step 2: Define Filter Conditions

Здесь мы определяем отдельные условия, которые хотим применить. В этом примере мы **filter summary tasks** и также гарантируем, что объект задачи не равен null.

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Step 3: Combine Conditions with AND Operation

Теперь мы **combine multiple conditions** с помощью класса `And<T>`. Это ядро **advanced AND operation**.

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Step 4: Apply Condition and Filter Tasks

С готовым составным условием вызываем `Filter`, чтобы **filter project tasks** на основе объединённой логики.

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Step 5: Output Filtered Tasks

Наконец, выводим задачи, которые удовлетворили **all** условиям. Вы можете заменить вызовы `Console.WriteLine` любой пользовательской обработкой, которая вам нужна.

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## Common Issues and Solutions

| Проблема | Почему происходит | Быстрое решение |
|----------|-------------------|-----------------|
| `Filter` метод не найден | Отсутствует `using Aspose.Tasks.Util;` | Убедитесь, что импортировано пространство имен Util (см. раздел Импорт пространств имен). |
| Задачи не возвращаются | Условия слишком ограничительные (например, фильтрация задач‑итогов, когда их нет) | Проверьте, что проект действительно содержит задачи‑итоги, или измените условия. |
| NullReferenceException | `coll.Tasks` содержит null‑элементы | Условие `NotNullCondition` уже защищает от этого; оставьте его в цепочке AND. |

## FAQ's

### Q1: Что такое Aspose.Tasks для .NET?

A: Aspose.Tasks for .NET — это мощный API, позволяющий разработчикам программно работать с файлами Microsoft Project в приложениях .NET.

### Q2: Можно ли применить более двух условий, используя Util.And?

A: Да, Util.And можно использовать для объединения любого количества условий, создавая сложные критерии фильтрации.

### Q3: Доступна ли бесплатная пробная версия Aspose.Tasks для .NET?

A: Да, вы можете скачать бесплатную пробную версию **[здесь](https://releases.aspose.com/)**.

### Q4: Где можно найти документацию по Aspose.Tasks для .NET?

A: Документацию можно найти **[здесь](https://reference.aspose.com/tasks/net/)**.

### Q5: Как получить поддержку по Aspose.Tasks для .NET?

A: Поддержку можно получить на форуме сообщества Aspose.Tasks **[здесь](https://forum.aspose.com/c/tasks/15)**.

**Additional Q&A**

**Q: Как я могу фильтровать задачи по значениям пользовательского поля?**  
A: Создайте `CustomFieldCondition` (или реализуйте `ICondition<Task>`) и добавьте его в цепочку `And<T>`.

**Q: Можно ли использовать тот же подход для фильтрации ресурсов?**  
A: Да — замените `Task` на `Resource` и используйте соответствующие классы условий.

## Conclusion

Следуя приведённым выше шагам, вы теперь знаете **как комбинировать несколько условий** с помощью **расширенной операции AND** в Aspose.Tasks для .NET. Эта техника позволяет **фильтровать задачи проекта** эффективно, независимо от того, нацелены ли вы на элементы‑итоги, ненулевые записи или любые пользовательские критерии, которые вы определяете.

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Tasks for .NET (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}