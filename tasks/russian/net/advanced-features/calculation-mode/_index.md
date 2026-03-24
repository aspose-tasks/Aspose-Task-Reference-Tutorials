---
date: 2026-03-24
description: Узнайте, как установить режим расчёта в Aspose.Tasks для .NET, охватывающий
  автоматический, ручной режим расчёта и режим без расчёта для управления зависимостями
  задач.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Как установить режим расчёта в Aspose.Tasks для .NET
url: /ru/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить режим расчёта в Aspose.Tasks для .NET

## Введение

Aspose.Tasks for .NET — это мощный API, позволяющий программно работать с файлами Microsoft Project. Одной из самых важных настроек, с которой вы столкнётесь, является **calculation mode**, который контролирует, как обновляются даты задач и расписания проекта. В этом руководстве вы узнаете, **как установить режим расчёта**, изучите **automatic calculation mode**, **manual calculation mode** и **none calculation mode**, а также увидите, как эти варианты влияют на **manage task dependencies**, **create project start date** и **link tasks finish‑start** relationships.

## Быстрые ответы
- **Что такое calculation mode?** Он определяет, пересчитываются ли даты задач автоматически, вручную или вовсе нет.  
- **Зачем использовать manual calculation mode?** Чтобы полностью контролировать, когда расписание обновляется, что полезно при массовых изменениях.  
- **Какой режим по умолчанию?** Automatic calculation mode, который обновляет даты мгновенно после изменений.  
- **Можно ли изменить режим во время выполнения?** Да — просто установите свойство `CalculationMode` у объекта `Project`.  
- **Нужна ли лицензия?** Для использования в продакшене требуется действующая лицензия Aspose.Tasks.

## Что такое «как установить расчёт» в Aspose.Tasks?
Установка режима расчёта так же проста, как присвоить значение перечисления свойству `Project.CalculationMode`. Перечисление предоставляет три варианта: `Automatic`, `Manual` и `None`. Выбор правильного режима зависит от вашего рабочего процесса — хотите ли вы мгновенные обновления, пакетную обработку или полный контроль.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

1. **Visual Studio** — любая современная версия (2019, 2022 или новее).  
2. **Aspose.Tasks for .NET** — скачайте и установите библиотеку по ссылке [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** — вы должны уметь создавать консольные приложения и работать с пакетами NuGet.

## Импорт пространств имён

Прежде чем начать работу с Aspose.Tasks for .NET, импортируем необходимые пространства имён:

```csharp
using Aspose.Tasks;
using System;
```

## Как установить режим расчёта

Ниже вы найдёте пошаговые примеры для каждого режима расчёта. Блоки кода оставлены без изменений из оригинального руководства; пояснения вокруг них расширены для ясности.

### Применение Automatic Calculation Mode

Automatic mode пересчитывает даты мгновенно каждый раз, когда вы изменяете задачи или связи.

#### Шаг 1: Создайте новый экземпляр Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Шаг 2: Установите дату начала проекта и добавьте задачи

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Шаг 3: Свяжите задачи (finish‑to‑start)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Шаг 4: Проверьте пересчитанные даты

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Применение Manual Calculation Mode

Manual mode отключает автоматические обновления, предоставляя возможность пакетно обрабатывать изменения перед принудительным пересчётом.

#### Шаг 1: Создайте новый экземпляр Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Шаг 2: Установите дату начала проекта и добавьте задачи

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Шаг 3: Проверьте свойства задач

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Шаг 4: Свяжите задачи и проверьте даты (без автоматического пересчёта)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Применение None Calculation Mode

None mode отключает все внутренние расчёты. Используйте его, когда нужно только читать или экспортировать данные без изменений расписания.

#### Шаг 1: Создайте новый экземпляр Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Шаг 2: Добавьте новую задачу

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Шаг 3: Проверьте свойства задачи (без автоматических ID)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| Даты не обновляются после связывания задач | Проект находится в режиме **Manual** или **None** | Установите `project.CalculationMode = CalculationMode.Automatic` или вызовите `project.Calculate()` вручную |
| ID задач остаются 0 | Использование режима **None** препятствует генерации ID | Переключитесь в режим **Automatic** или **Manual**, затем выполните пересчёт |
| Связывание завершается ошибкой `ArgumentException` | Дата начала предшествующей задачи позже даты начала последующей при использовании режима **Manual** без пересчёта | Убедитесь в правильности дат начала или выполните пересчёт после добавления связей |

## Часто задаваемые вопросы

**Q1: Можно ли изменить режим расчёта динамически во время выполнения?**  
A1: Да, вы можете изменить свойство `CalculationMode` в любой точке вашего кода, а затем вызвать `project.Calculate()`, если требуется немедленное обновление.

**Q2: Поддерживает ли Aspose.Tasks другие форматы файлов управления проектами, помимо Microsoft Project?**  
A2: Aspose.Tasks в основном ориентирован на форматы Microsoft Project, но также поддерживает Primavera P6 XML, Primavera DB и Asta Powerproject XML.

**Q3: Подходит ли Aspose.Tasks как для небольших, так и для корпоративных проектов?**  
A3: Абсолютно. API масштабируется от простых списков задач до сложных, многоэтапных корпоративных расписаний.

**Q4: Могу ли я интегрировать Aspose.Tasks с другими библиотеками и фреймворками .NET?**  
A4: Да, вы можете комбинировать Aspose.Tasks с ASP.NET, WPF, Xamarin или любой другой технологией .NET для создания мощных решений по управлению проектами.

**Q5: Есть ли форум сообщества или канал поддержки для пользователей Aspose.Tasks?**  
A5: Да, вы можете посетить [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для получения поддержки от сообщества и обсуждений.

---

**Последнее обновление:** 2026-03-24  
**Тестировано с:** Aspose.Tasks 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}