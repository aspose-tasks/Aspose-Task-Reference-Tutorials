---
title: Обработка логических значений, допускающих значение NULL, в Aspose.Tasks
linktitle: Обработка логических значений, допускающих значение NULL, в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как эффективно обрабатывать логические значения, допускающие значение NULL, в Aspose.Tasks для .NET с помощью этого подробного руководства. Освойте использование класса NullableBool и улучшите свою разработку .NET.
type: docs
weight: 21
url: /ru/net/advanced-concepts/nullable-booleans/
---
## Введение

В этом уроке мы углубимся в работу с логическими значениями, допускающими значение NULL, в Aspose.Tasks для .NET. Логические значения, допускающие значение NULL, обеспечивают гибкость в представлении логических значений, допуская возможность неопределенности. Мы рассмотрим, как использовать`NullableBool` класс, его конструкторы, свойства и методы.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

1. Visual Studio: установите Visual Studio или любую другую интегрированную среду разработки для разработки .NET.
2.  Aspose.Tasks для .NET: Загрузите и установите Aspose.Tasks для .NET с сайта[здесь](https://releases.aspose.com/tasks/net/).

## Импортировать пространства имен

Во-первых, обязательно импортируйте необходимые пространства имен в свой код:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Теперь давайте разобьем каждый пример на несколько этапов.

##  Работать с`NullableBool`

###  Шаг 1. Создайте новый`Project` instance.

```csharp
var project = new Project();
```

###  Шаг 2. Создайте экземпляр`NullableBool` object with specified values.

```csharp
var actualsInSync = new NullableBool(false, false);
```

###  Шаг 3: Проверьте значение и определенный статус`NullableBool` object.

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

###  Шаг 4: Используйте`NullableBool` instance by setting it in the project.

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

###  Шаг 5: Создайте экземпляр другого`NullableBool` object with a single value.

```csharp
var honorConstraints = new NullableBool(true);
```

###  Шаг 6. Отобразите строковое представление`NullableBool` object.

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

###  Шаг 7: Используйте`NullableBool` instance by setting it in the project.

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

##  Сравнивая`NullableBool` Instances

###  Шаг 1. Создайте второй экземпляр`NullableBool` objects.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

###  Шаг 2. Проверьте строковое представление каждого`NullableBool` object.

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

###  Шаг 3. Проверьте неявное преобразование в`bool` and print the result.

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

###  Шаг 4: Сравните два`NullableBool` objects for equality.

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

##  Получение хэш-кода`NullableBool`

###  Шаг 1. Создайте второй экземпляр`NullableBool` objects.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Шаг 2. Распечатайте хеш-код для каждого`NullableBool` object.

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## Заключение

 В этом уроке мы рассмотрели, как обрабатывать логические значения, допускающие значение NULL, в Aspose.Tasks для .NET. Используя`NullableBool` и его методы, вы можете эффективно управлять логическими значениями с дополнительной гибкостью, допускающей значение NULL.

## Часто задаваемые вопросы

### Вопрос 1. Что такое логическое значение, допускающее значение NULL?

A1: Логическое значение, допускающее значение NULL, — это тип, который может представлять истину, ложь или быть неопределенным.

### Вопрос 2. Зачем использовать логические значения, допускающие значение NULL?

A2. Логические значения, допускающие значение NULL, обеспечивают гибкость в сценариях, где логическое значение не всегда может быть определено.

### Вопрос 3. Как сравниваются логические значения, допускающие значение NULL, на равенство?

A3: Логические значения, допускающие значение NULL, сравниваются на основе их определенного статуса и значений.

### Вопрос 4. Могу ли я установить неопределенное логическое значение, допускающее значение NULL?

A4: Да, вы можете установить логическое значение, допускающее значение NULL, которое будет неопределенным при создании.

### Вопрос 5: Где я могу найти дополнительную документацию по Aspose.Tasks для .NET?

 A5: Вы можете найти подробную документацию[здесь](https://reference.aspose.com/tasks/net/).