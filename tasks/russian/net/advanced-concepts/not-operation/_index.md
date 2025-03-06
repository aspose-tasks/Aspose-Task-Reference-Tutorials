---
title: Работа с операцией NOT в Aspose.Tasks
linktitle: Работа с операцией NOT в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как использовать операцию NOT в Aspose.Tasks для .NET для эффективной фильтрации задач. Расширьте свои возможности управления проектами прямо сейчас.
weight: 20
url: /ru/net/advanced-concepts/not-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Работа с операцией NOT в Aspose.Tasks

## Введение

В этом уроке мы рассмотрим, как использовать операцию NOT в Aspose.Tasks для .NET. Операция НЕ позволяет нам отменить условие фильтра, что позволяет нам выбирать элементы, которые не соответствуют указанным критериям.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1. Visual Studio: вам понадобится работающая установка Visual Studio, чтобы следовать примерам кода.
2.  Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks для .NET из[Веб-сайт](https://releases.aspose.com/tasks/net/).
3. Базовое понимание C#: Знакомство с языком программирования C# будет полезно для понимания примеров кода.

## Импортировать пространства имен

Сначала давайте импортируем необходимые пространства имен для нашего кода:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1. Настройка проекта и задач

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 Начнем с загрузки файла проекта с именем «Project2.mpp», используя`Project` класс, предоставленный Aspose.Tasks. Убедитесь, что файл проекта существует в указанном каталоге.

## Шаг 2. Соберите задачи проекта

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Здесь мы создаем`ChildTasksCollector` объект для сбора всех задач в рамках проекта. Затем мы используем`TaskUtils.Apply` метод для перемещения по иерархии задач проекта и сбора всех дочерних задач.

## Шаг 3: Определите условие фильтра

```csharp
var filter = new NullCondition();
```

 Мы определяем условие фильтра, используя собственный класс с именем`NullCondition`. Это условие выбирает задачи, имеющие нулевое значение.

## Шаг 4. Примените операцию NOT.

```csharp
var condition = new Not<Task>(filter);
```

 Мы применяем операцию НЕ к условию фильтра, используя оператор`Not<T>`класс, предоставленный Aspose.Tasks. Это изменит условие фильтра, выбрав задачи, которые не имеют нулевого значения.

## Шаг 5. Фильтрация задач

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 Фильтруем собранные задачи по примененному условию с помощью пользовательского`Filter` метод. Этот метод принимает перечислимую коллекцию задач и условие фильтра в качестве входных параметров и возвращает список задач, удовлетворяющих этому условию.

## Шаг 6. Обработка отфильтрованных задач

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Работа с другими объектами...
}
```

Наконец, мы перебираем отфильтрованные задачи и выполняем любые желаемые операции. В этом примере мы просто выводим названия задач в консоль.

## Заключение

В этом уроке мы узнали, как работать с операцией NOT в Aspose.Tasks для .NET. Обратив условия фильтра, мы можем выборочно выбирать элементы, которые не соответствуют заданным критериям, что повышает нашу гибкость в манипулировании задачами в проектах.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.Tasks с другими платформами .NET?

О: Да, Aspose.Tasks поддерживает различные платформы .NET, включая .NET Core, .NET Standard и .NET Framework.

### Вопрос 2. Доступна ли бесплатная пробная версия Aspose.Tasks?

 О: Да, вы можете загрузить бесплатную пробную версию с сайта[Веб-сайт](https://releases.aspose.com/).

### В3: Как я могу получить поддержку Aspose.Tasks?

 О: Вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для любых вопросов поддержки или технической помощи.

### В4: Могу ли я приобрести временную лицензию для Aspose.Tasks?

 О: Да, вы можете приобрести временную лицензию на сайте[страница покупки](https://purchase.aspose.com/temporary-license/).

### Вопрос 5: Где я могу найти подробную документацию по Aspose.Tasks?

 О: Вы можете получить доступ к полной документации на[Страница документации Aspose.Tasks](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
