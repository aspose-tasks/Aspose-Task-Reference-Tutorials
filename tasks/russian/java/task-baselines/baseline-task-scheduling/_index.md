---
date: 2026-08-29
description: Узнайте, как считывать данные базовой линии и планировать задачи с помощью
  Aspose.Tasks для Java, чтобы эффективно сравнивать запланированный и фактический
  прогресс.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Планирование задач по базовой линии в Aspose.Tasks
og_description: Узнайте, как считывать данные базовой линии и планировать задачи с
  помощью Aspose.Tasks для Java, обеспечивая точное сравнение запланированного и фактического
  прогресса.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Как считывать базовую линию и планировать задачи с Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Как считывать базовую линию и планировать задачи с Aspose.Tasks
url: /ru/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как читать базовую линию и планировать задачи с Aspose.Tasks

В этом руководстве вы узнаете **как читать информацию о базовой линии** и программно планировать задачи с помощью Aspose.Tasks для Java. К концу урока вы сможете зафиксировать исходный план проекта, сравнить его с фактическим прогрессом и создать отчёты о отклонениях — без необходимости установки Microsoft Project.

## Введение в базовую линию управления проектом
Управление **базовой линией управления проектом** является краеугольным камнем эффективного управления проектом. Это позволяет зафиксировать исходный план и позже сравнить **запланированный и фактический прогресс**, чтобы раннее выявлять отклонения. В этом руководстве мы пройдёмся по процессу планирования базовых линий задач с помощью Aspose.Tasks для Java, предоставив вам инструменты для **управления базовыми линиями проекта** с уверенностью и поддержания ваших проектов в графике.

## Быстрые ответы
- **Что представляет собой базовая линия управления проектом?**  
  Она фиксирует утверждённый график, стоимость и объём работ в начале проекта, предоставляя основу для анализа отклонений.  
- **Какая библиотека обрабатывает планирование базовых линий в Java?**  
  Aspose.Tasks for Java предлагает чистый Java API, поддерживающий более 45 форматов ввода и вывода и проекты до 100 000 задач.  
- **Нужна ли лицензия для выполнения кода?**  
  Бесплатная пробная версия подходит для тестирования; для использования в продакшене требуется коммерческая лицензия.  
- **Каковы основные предварительные требования?**  
  Java Development Kit (JDK) 11+ и библиотека Aspose.Tasks for Java.  
- **Можно ли просмотреть даты базовой линии после их установки?**  
  Да — используйте объект `TaskBaseline` для чтения значений начала, окончания и продолжительности.

## Что такое базовая линия управления проектом?
Базовая линия управления проектом фиксирует утверждённый график, бюджет и объём работ в начале выполнения. Она служит точкой отсчёта для измерения эффективности и выявления отклонений на протяжении жизненного цикла проекта. В неё входят запланированные даты начала и окончания, общая стоимость и детали объёма, предоставляя полную картину для будущих сравнений.

## Почему использовать Aspose.Tasks для планирования базовых линий?
Aspose.Tasks предоставляет чистый Java API, который работает без установки Microsoft Project. Он поддерживает **более 45 форматов ввода и вывода**, может обрабатывать проекты с **до 100 000 задач** в режиме экономии памяти и предлагает встроенные методы для чтения и записи данных базовой линии — что упрощает автоматическую генерацию отчётов и интеграцию.

## Предварительные требования
- **Java Development Kit (JDK)** – установите JDK 11 или новее. Вы можете скачать его с [веб‑сайта](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java library** – скачайте последнюю версию со [страницы загрузки](https://releases.aspose.com/tasks/java/) и добавьте JAR в classpath вашего проекта.

## Импорт пакетов
Классы `Project`, `Task` и `TaskBaseline` находятся в пространстве имён `com.aspose.tasks`. Импортируйте их в начале вашего исходного файла:

Класс `Project` — это объект верхнего уровня Aspose.Tasks, представляющий один файл проекта в памяти. Он предоставляет доступ к задачам, ресурсам и коллекциям базовых линий.

## Как прочитать базовую линию?
Загрузите проект, затем запросите коллекцию `TaskBaseline` для каждой задачи. Объект `TaskBaseline` возвращает начало, окончание и продолжительность базовой линии, зафиксированные при вызове `setBaseline`. Такой прямой подход позволяет читать значения базовой линии без парсинга XML или бинарных файлов.

## Шаг 1: создать новый экземпляр проекта
Класс `Project` представляет весь файл проекта в памяти.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## Шаг 2: определить задачу и установить базовую линию
`Task` представляет отдельный элемент работы, а `setBaseline` фиксирует его текущий график как базовую линию.
```java
Project project = new Project();
```

## Шаг 3: получить информацию о базовой линии
`TaskBaseline` хранит сохранённые значения начала, окончания и продолжительности базовой линии.
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Шаг 4: отобразить продолжительность базовой линии
`Duration` представляет длительность задачи или базовой линии.
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Шаг 5: отобразить дату начала базовой линии
`Start` — это запланированная дата начала базовой линии.
```java
System.out.println(baseline.getDuration().toString());
```

## Шаг 6: отобразить дату окончания базовой линии
`Finish` — это запланированная дата завершения базовой линии.
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Распространённые проблемы и решения
- **Базовая линия не установлена:** Убедитесь, что вызываете `project.setBaseline(BaselineType.Baseline)` **после** добавления задач; иначе коллекция базовых линий будет пустой.  
- **Null‑значения:** Если `task.getBaselines()` возвращает пустой список, проверьте, что задача была добавлена в иерархию проекта перед установкой базовой линии.  
- **Формат даты:** Методы `getStart()` и `getFinish()` возвращают объекты `java.util.Date`. Используйте `SimpleDateFormat`, если нужен пользовательский формат отображения.

## Часто задаваемые вопросы

**В: Как создать новый экземпляр проекта в Aspose.Tasks?**  
О: Создайте объект класса `Project` (`Project project = new Project();`). Это создаёт новый файл проекта, готовый к задачам и базовым линиям.

**В: В чём разница между `BaselineType.Baseline` и другими типами базовых линий?**  
О: `BaselineType.Baseline` относится к основной базовой линии (Baseline 1). Aspose.Tasks также поддерживает Baseline 2‑10 для дополнительных снимков.

**В: Можно ли экспортировать данные базовой линии в Excel или CSV?**  
О: Да, можно перебрать объекты `TaskBaseline` и записать их значения в CSV‑файл, используя стандартный Java I/O.

**В: Влияет ли установка базовой линии на существующие даты задач?**  
О: Установка базовой линии фиксирует текущие даты, но не изменяет активный график задачи. Вы всё равно можете корректировать даты начала/окончания после установки базовой линии.

**В: Можно ли программно сравнивать несколько базовых линий?**  
О: Конечно. Получайте каждую базовую линию через `task.getBaselines().get(index)` и сравнивайте их свойства `Start`, `Finish` и `Duration`.

---

**Последнее обновление:** 2026-08-29  
**Тестировано с:** Aspose.Tasks for Java 24.12  
**Автор:** Aspose  








```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Связанные руководства

- [Создать список задач Java – базовая линия MS Project с использованием Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Как установить продолжительность базовой линии в Aspose.Tasks для Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Создать MPP проект Java – изменить прогресс задачи с Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}