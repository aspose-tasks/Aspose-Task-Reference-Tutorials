---
date: 2026-03-08
description: Узнайте, как настроить отображение меток и изменить метку дня в управлении
  проектами с помощью Aspose.Tasks для .NET, улучшая читаемость и ясность.
linktitle: Displaying Labels in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Как установить отображение метки в Aspose.Tasks для .NET
url: /ru/net/advanced-concepts/label-display/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить отображение меток в Aspose.Tasks для .NET

## Введение

Когда вы создаёте решение для управления проектами с **Aspose.Tasks for .NET**, возможность **как установить метку** является ключевой для того, чтобы графики были легко читаемыми. Независимо от того, нужна ли вам точность до минуты или общий годовой обзор, настройка отображения меток позволяет представить временную шкалу именно так, как ожидают ваши заинтересованные стороны. В этом руководстве мы пошагово рассмотрим процесс установки отображения меток для минут, часов, дней, недель, месяцев и лет, а также покажем, как **настроить метку дня** для максимальной ясности.

## Быстрые ответы
- **Что означает “how to set label”?** Это относится к настройке свойств `DisplayOptions`, которые управляют тем, как единицы времени отображаются в файле проекта.  
- **Какую метку я могу изменить?** Минуты, часы, дни, недели, месяцы и годы — все они настраиваемы.  
- **Нужна ли лицензия?** Для использования в продакшене требуется действующая лицензия Aspose.Tasks; бесплатная trial‑версия подходит для тестирования.  
- **Поддерживается ли это в .NET Core?** Да, API работает с .NET Core, .NET 5/6 и полной версией .NET Framework.  
- **Можно ли изменить метку во время выполнения?** Конечно — вы можете изменять параметры отображения в любой момент до сохранения проекта.

## Что такое отображение меток в Aspose.Tasks?

Отображение меток определяет текстовое представление единиц времени (минута, час, день и т.д.) на диаграмме Ганта и шкале времени. Установив соответствующее свойство `DisplayOptions`, вы указываете Aspose.Tasks, как отображать эти единицы, что может существенно повысить читаемость проекта.

## Зачем настраивать отображение меток?

- **Повышенная читаемость:** Заинтересованные стороны мгновенно понимают детализацию расписания.  
- **Последовательная отчетность:** Выравнивает визуальный вывод с корпоративными стандартами (например, использование “Mo” для месяцев).  
- **Гибкость:** Переключайтесь между детальными и общими представлениями без изменения исходных данных расписания.

## Требования

1. **Знание C#** – базовое знакомство с синтаксисом C# и структурой проекта .NET.  
2. **Aspose.Tasks for .NET** – скачайте и установите библиотеку по ссылке [here](https://releases.aspose.com/tasks/net/).  
3. **Среда разработки** – Visual Studio, VS Code или любой IDE, поддерживающий разработку на .NET.

## Импорт пространств имён

Перед началом импортируйте необходимые пространства имён:

```csharp
using Aspose.Tasks;
using Aspose.Tasks;
```

## Как установить отображение меток для минут

### 1. Отображение меток минут

Чтобы установить метку минут, используйте свойство `MinuteLabel`:

```csharp
public void WorkWithMinuteLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the minute label is displayed
    project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.M;
}
```

## Как установить отображение меток для часов

### 2. Отображение меток часов

```csharp
public void WorkWithHourLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the hour label is displayed
    project.DisplayOptions.HourLabel = HourLabelDisplay.H;
}
```

## Настройка отображения метки дня

### 3. Отображение меток дня

```csharp
public void WorkWithDayLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the day label is displayed
    project.DisplayOptions.DayLabel = DayLabelDisplay.D;
}
```

## Как установить отображение меток для недель

### 4. Отображение меток недель

```csharp
public void WorkWithWeekLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the week label is displayed
    project.DisplayOptions.WeekLabel = WeekLabelDisplay.W;
}
```

## Как установить отображение меток для месяцев

### 5. Отображение меток месяцев

```csharp
public void WorkWithMonthLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the month label is displayed
    project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mo;
}
```

## Как установить отображение меток для лет

### 6. Отображение меток лет

```csharp
public void WorkWithYearLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the year label is displayed
    project.DisplayOptions.YearLabel = YearLabelDisplay.Y;
}
```

## Распространённые подводные камни и советы

- **Совет:** Всегда задавайте отображение метки *до* сохранения проекта; изменения, сделанные после сохранения, не отразятся в файле.  
- **Подводный камень:** Использование неподдерживаемого значения enum вызовет `ArgumentException`. Используйте только предоставленные перечисления `*LabelDisplay`.  
- **Совет:** Если нужны разные стили меток для разных представлений, создайте отдельные экземпляры `Project` или клонируйте объект `DisplayOptions`.

## Заключение

Освоив **как установить метку** в Aspose.Tasks, вы получаете детальный контроль над визуальным представлением расписаний проекта. Будь то настройка метки дня для ежедневной доски Scrum или корректировка метки года для многолетней дорожной карты, эти параметры помогут вам предоставить более понятную и профессиональную проектную документацию.

## Часто задаваемые вопросы

### Q1: Могу ли я настроить отображение меток для конкретных разделов проекта?

A1: Да, Aspose.Tasks for .NET предоставляет детальный контроль над отображением меток, позволяя настраивать их для конкретных разделов проекта по необходимости.

### Q2: Совместим ли Aspose.Tasks с популярными .NET‑фреймворками?

A2: Да, Aspose.Tasks for .NET совместим с различными .NET‑фреймворками, включая .NET Core и .NET Framework.

### Q3: Могу ли я динамически менять отображение меток в зависимости от требований проекта?

A3: Абсолютно, гибкость Aspose.Tasks for .NET позволяет динамически менять отображение меток в соответствии с меняющимися требованиями проекта.

### Q4: Есть ли ограничения на настройку отображения меток?

A4: Aspose.Tasks for .NET предлагает широкие возможности настройки отображения меток с минимальными ограничениями, предоставляя пользователям большую гибкость.

### Q5: Поддерживает ли Aspose.Tasks интеграцию с другими инструментами управления проектами?

A5: Да, Aspose.Tasks обеспечивает бесшовную интеграцию, облегчая взаимодействие с другими инструментами и платформами управления проектами.

---

**Последнее обновление:** 2026-03-08  
**Тестировано с:** Aspose.Tasks 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}