---
date: 2026-08-29
description: Узнайте, как установить baseline duration и отслеживать project progress
  с помощью Aspose.Tasks for Java. Это пошаговое руководство поможет эффективно управлять
  task baselines.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Как установить Baseline Duration в Aspose.Tasks for Java
og_description: Узнайте, как установить baseline duration и отслеживать project progress
  с помощью Aspose.Tasks for Java. Следуйте этому подробному руководству, чтобы эффективно
  управлять task baselines.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Как установить baseline duration для отслеживания project progress
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Как установить baseline duration для отслеживания project progress
url: /ru/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить продолжительность базовой линии для отслеживания прогресса проекта

## Введение
Отслеживание прогресса проекта начинается с надёжной базовой линии. В этом руководстве вы узнаете **как установить продолжительность базовой линии** для задач в файлах Microsoft Project с использованием библиотеки Aspose.Tasks для Java и поймёте, почему раннее установление базовой линии помогает контролировать отклонения расписания, отклонения стоимости и перераспределение ресурсов на протяжении всего жизненного цикла проекта.

## Быстрые ответы
- **Что означает “set baseline”?** Он фиксирует оригинальные дату начала, завершения и продолжительность задачи, чтобы вы могли сравнивать будущие изменения.  
- **Какой класс Aspose.Tasks создаёт проект?** Класс `Project` — вы также узнаете, как правильно **создать экземпляр проекта**.  
- **Нужна ли лицензия для выполнения кода?** Бесплатная оценочная лицензия подходит для тестирования; для продакшн‑использования требуется коммерческая лицензия.  
- **Можно ли получить промежуточные базовые линии?** Да, Aspose.Tasks позволяет запрашивать промежуточные базовые линии и их фиксированные затраты.  
- **Какая версия Java требуется?** Рекомендуется Java 8 или новее.  
- **Как это помогает отслеживать прогресс проекта?** После установки базовой линии вы можете мгновенно сравнивать фактические даты с оригинальным планом, используя встроенные функции отчётности.

## Что такое базовая линия задачи и зачем её устанавливать?
Базовая линия задачи фиксирует запланированное расписание (дату начала, дату завершения и продолжительность) в определённый момент времени. Устанавливая базовую линию, вы создаёте точку отсчёта, которая упрощает выявление отклонений расписания, перерасхода бюджета и перераспределения ресурсов по мере развития проекта.

## Почему использовать Aspose.Tasks для управления базовыми линиями?
Aspose.Tasks обеспечивает **полную совместимость с .mpp** — вы можете читать и записывать нативные файлы Microsoft Project без необходимости установки Microsoft Office. API предоставляет программный доступ к **более 50 форматам ввода и вывода**, поддерживает **промежуточные базовые линии 1‑10** и может работать с **многосотенными проектами** без загрузки всего файла в память, что важно для высокопроизводительной пакетной обработки.

## Предварительные требования
1. **Среда разработки Java** — установлен и настроен JDK 8+.  
2. **Aspose.Tasks for Java** — загрузите библиотеку со [страницы загрузки Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **IDE или система сборки** — Maven, Gradle или любой предпочитаемый IDE.

## Импорт пакетов
Следующие импорты подключают основные классы Aspose.Tasks, необходимые для работы с проектами, задачами, базовыми линиями и данными с учётом времени.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Шаг 1: создать экземпляр проекта
Класс `Project` представляет файл Microsoft Project в памяти и служит точкой входа для всех операций.

```java
Project project = new Project();
```

## Шаг 2: создать базовую линию задачи
`TaskBaseline` хранит запланированные дату начала, завершения и продолжительность для конкретной задачи.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Шаг 3: отобразить информацию о базовой линии задачи
Метод `getBaselines()` возвращает коллекцию базовых линий, связанных с задачей.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Шаг 4: проверить промежуточную базовую линию и фиксированную стоимость
`BaselineType` перечисляет основные и промежуточные базовые линии (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Шаг 5: вывести данные с учётом времени
`TimephasedData` представляет часть информации о расписании для конкретного временного интервала.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Следуя этим шагам, вы сможете **установить продолжительность базовой линии** для любой задачи и получить подробную информацию о базовой линии с помощью Aspose.Tasks for Java, что предоставит надёжный способ **отслеживать прогресс проекта** на протяжении всего жизненного цикла проекта.

## Распространённые проблемы и решения
- **Базовая линия не отображается в MS Project:** Убедитесь, что вы вызвали `project.setBaseline(BaselineType.Baseline)` **после** добавления задачи.  
- **NullPointerException при вызове `getBaselines()`:** Проверьте, что задача была добавлена в проект до установки базовой линии.  
- **Несоответствие единицы времени:** Используйте `TimeUnitType` для правильного форматирования продолжительности, особенно при работе с пользовательскими календарями.

## Часто задаваемые вопросы
### Что такое базовая линия задачи в MS Project?
Базовая линия задачи в MS Project — это снимок первоначального запланированного расписания задачи, включающий её дату начала, дату завершения и продолжительность.

### Почему важно управлять базовыми линиями задач?
Управление базовыми линиями задач помогает сравнивать запланированное расписание с фактическим прогрессом проекта, способствуя более эффективному отслеживанию и принятию решений.

### Можно ли изменить базовую линию задачи после её установки?
Да, вы можете изменять базовые линии задач в MS Project, чтобы отразить изменения в плане проекта. Однако важно документировать любые отклонения от оригинальной базовой линии.

### Поддерживает ли Aspose.Tasks другие функции управления проектами?
Да, Aspose.Tasks предоставляет широкий набор функций для управления проектами, включая планирование задач, распределение ресурсов и генерацию диаграмм Ганта.

### Где можно получить поддержку Aspose.Tasks?
Поддержку Aspose.Tasks можно найти на [форуме Aspose.Tasks](https://forum.aspose.com/c/tasks/15), где вы можете задавать вопросы и общаться с другими пользователями.

## Дополнительные часто задаваемые вопросы
**Q: Нужно ли вызывать `setBaseline` для каждой задачи отдельно?**  
A: Нет. Вызов `project.setBaseline(BaselineType.Baseline)` фиксирует базовую линию для всех задач проекта одновременно.

**Q: Как установить промежуточную базовую линию для конкретной задачи?**  
A: Используйте `project.setBaseline(BaselineType.Baseline1)` (или Baseline2‑Baseline10) после обновления расписания задачи.

**Q: Можно ли экспортировать данные базовой линии в CSV?**  
A: Да. Пройдитесь по `task.getBaselines()` и запишите нужные поля в CSV‑файл, используя стандартный ввод‑вывод Java.

**Q: Можно ли прочитать существующий файл .mpp, уже содержащий базовые линии?**  
A: Конечно. Загрузите файл с помощью `new Project("myproject.mpp")`, а затем получайте базовые линии каждой задачи, как показано выше.

**Q: Обрабатывает ли Aspose.Tasks файлы с несколькими проектами?**  
A: Aspose.Tasks работает с одно‑проектными файлами .mpp. Для сценариев с несколькими проектами объединяйте проекты программно.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Связанные руководства

- [Создать список задач Java – базовая линия MS Project с использованием Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Создать проект MPP Java – изменить прогресс задачи с Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Базовая линия управления проектом – планирование задач с Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}