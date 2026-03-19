---
date: 2026-03-19
description: Узнайте, как установить базовый план проекта и эффективно управлять базовыми
  планами назначений с помощью Aspose.Tasks для .NET, обеспечивая точный контроль
  хода проекта.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Установить базовый план проекта – Управление базовым планом назначения в Aspose.Tasks
url: /ru/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Установка базовой линии проекта – Управление базовыми линиями назначений в Aspose.Tasks

## Введение

При работе над задачами управления проектами **установка базовой линии проекта** необходима для измерения фактического прогресса относительно исходного плана. Aspose.Tasks для .NET позволяет не только **установить базовую линию проекта**, но и предоставляет полный контроль над базовыми линиями назначений, обеспечивая точный мониторинг выполнения. В этом руководстве мы пройдем весь процесс — загрузку проекта, установку базовой линии, чтение данных базовой линии назначений и сравнение базовых линий — чтобы вы могли уверенно отслеживать свои проекты.

## Краткие ответы
- **Что означает «установить базовую линию проекта»?** Это фиксирует исходные данные о расписании и стоимости для последующего сравнения с фактическими результатами.  
- **Какой метод API устанавливает базовую линию?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Требуются ли отдельные вызовы для базовых линий назначений?** Нет, они сохраняются автоматически при установке базовой линии проекта.  
- **Какие форматы поддерживаются?** MPP, XML, MPX и другие через Aspose.Tasks.  
- **Нужна ли лицензия для продакшн‑использования?** Да, коммерческая лицензия требуется для использования не в режиме пробной версии.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

- Базовые знания программирования на C#.  
- Visual Studio (любая современная версия).  
- Библиотека Aspose.Tasks для .NET, добавленная в ваш проект. Скачать её можно [здесь](https://releases.aspose.com/tasks/net/).  
- Доступ к файлу проекта в формате MPP (например, `AssignmentBaseline2007.mpp`).

## Импорт пространств имён

Добавьте необходимые пространства имён в начало вашего C#‑файла, чтобы компилятор знал, где находятся классы Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
```

## Шаг 1: Загрузка проекта и установка базовой линии проекта

Сначала загрузите существующий файл MPP, а затем вызовите `SetBaseline`, чтобы **установить базовую линию проекта** для всего проекта.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Шаг 2: Чтение информации о базовой линии назначения

После установки базовой линии каждый ресурсный назначение содержит свои собственные записи базовой линии. Ниже приведён цикл, который извлекает и выводит эти детали, включая даты начала/окончания, стоимость, работу и любые данные с фазированием во времени.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Шаг 3: Сравнение базовых линий назначений

Вы можете сравнивать базовые линии разных назначений, используя встроенные операторы равенства и сравнения. Это удобно, когда необходимо обнаружить сдвиги расписания или перерасходы стоимости между задачами.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Распространённые проблемы и решения

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **Данные базовой линии пусты** | Файл проекта открыт в режиме только для чтения или базовая линия никогда не была установлена. | Вызовите `project.SetBaseline(BaselineType.Baseline)` перед чтением базовых линий назначений. |
| **`NullReferenceException` на `TimephasedData`** | Не все базовые линии содержат записи с фазированием во времени. | Всегда проверяйте `baseline.TimephasedData != null` (как показано в коде). |
| **Неправильное получение UID** | Значения UID различаются между версиями файлов. | Используйте `ResourceAssignments.GetByUid` с правильным UID или перебирайте назначения, чтобы найти нужное. |

## Часто задаваемые вопросы

**В: Может ли Aspose.Tasks обрабатывать несколько базовых линий для одного назначения?**  
О: Да, Aspose.Tasks поддерживает несколько базовых линий для каждого назначения, что позволяет вести комплексный учёт прогресса проекта во времени.

**В: Совместим ли Aspose.Tasks с различными форматами файлов проектов, кроме MPP?**  
О: Да, Aspose.Tasks поддерживает широкий спектр форматов файлов проектов, включая XML, MPX и MPP, обеспечивая совместимость с различными инструментами управления проектами.

**В: Можно ли программно изменять информацию о базовой линии с помощью Aspose.Tasks?**  
О: Абсолютно, Aspose.Tasks предоставляет обширный набор API для динамического изменения информации о базовой линии в соответствии с требованиями проекта, предоставляя гибкость и контроль над процессами управления проектом.

**В: Предоставляет ли Aspose.Tasks документацию и ресурсы поддержки для разработчиков?**  
О: Да, разработчики могут получить доступ к полной документации, руководствам и форумам на сайте Aspose.Tasks, что облегчает интеграцию и решение проблем.

**В: Есть ли пробная версия Aspose.Tasks для .NET?**  
О: Да, разработчики могут скачать бесплатную пробную версию Aspose.Tasks для .NET [здесь](https://releases.aspose.com/), чтобы оценить её возможности перед принятием решения о покупке.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

---