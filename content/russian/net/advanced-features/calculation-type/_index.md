---
title: Тип расчета в Aspose.
linktitle: Тип расчета в Aspose.
second_title: Aspose.Tasks .NET API
description: Узнайте, как настроить вычисления значений в проектах .NET с помощью типа расчета в библиотеке Aspose.Tasks.
type: docs
weight: 30
url: /ru/net/advanced-features/calculation-type/
---
## Введение

В этом руководстве мы рассмотрим функцию типа расчета в Aspose.Tasks для .NET. Aspose.Tasks — это мощная библиотека, которая позволяет .NET-разработчикам работать с файлами Microsoft Project без необходимости установки Microsoft Project в их системах. Тип расчета позволяет нам определить, как рассчитываются значения для задач и суммарных задач в рамках проекта.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

1. Базовые знания C# и .NET framework.
2. Visual Studio установлена в вашей системе.
3.  Установлена библиотека Aspose.Tasks для .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/tasks/net/).
4.  Доступен доступ к документации Aspose.Tasks для .NET для справки.[здесь](https://reference.aspose.com/tasks/net/).

## Импортировать пространства имен

Прежде чем углубляться в пример, обязательно импортируйте необходимые пространства имен:

```csharp
using Aspose.Tasks;
using System;


```

## Шаг 1. Создайте новый проект.

Сначала давайте создадим новый объект проекта:

```csharp
var project = new Project();
```

## Шаг 2. Добавьте задачу

Теперь добавим задачу в наш проект:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Шаг 3. Определите тип расчета для расширенного атрибута

Мы создадим расширенное определение атрибута с типом расчета, установленным на «Формула»:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Шаг 4. Определите тип расчета для строк сводки

Далее мы создадим еще одно расширенное определение атрибута, в котором значения для суммарных задач рассчитываются с использованием типа сведения «Среднее»:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Заключение

В этом уроке мы рассмотрели, как работать с типом расчета в Aspose.Tasks для .NET. Определив типы расчета для расширенных атрибутов, мы можем настроить способ расчета значений для задач и сводных задач в рамках проекта, обеспечивая большую гибкость и контроль.

## Часто задаваемые вопросы

### Вопрос 1. Что такое тип расчета в Aspose.Tasks?

A1: Тип расчета в Aspose.Tasks определяет, как рассчитываются значения для задач и суммарных задач в рамках проекта, предлагая такие параметры, как формула и сведение.

### Вопрос 2. Как установить тип расчета для расширенного атрибута?

A2: Вы можете установить тип расчета для расширенного атрибута, соответствующим образом определив его свойство CalculationType.

### Вопрос 3. Могу ли я настроить тип расчета для строк сводки в проекте?

О3: Да, Aspose.Tasks позволяет вам указать тип расчета для строк сводки, что позволяет вам адаптировать расчеты значений в соответствии с вашими требованиями.

### Вопрос 4. Существуют ли различные типы сведения для расчетов сводных задач?

A4: Да, Aspose.Tasks предоставляет различные типы сводных данных, такие как «Среднее», «Сумма» и «Количество», для расчета значений суммарных задач.

### Вопрос 5: Где я могу найти дополнительные ресурсы по Aspose.Tasks для .NET?

 О5: Вы можете изучить документацию и форумы поддержки сообщества, доступные на[Aspose.Tasks для .NET](https://reference.aspose.com/tasks/net/) за всестороннее руководство и помощь.