---
date: 2026-09-25
description: Узнайте, как создать расписание проекта в Java с использованием Aspose.Tasks.
  Это руководство показывает, как добавить summary tasks, управлять project hierarchy
  и эффективно установить document directory.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Создать задачи в Aspose.Tasks
og_description: Узнайте, как создать расписание проекта в Java с использованием Aspose.Tasks.
  Следуйте пошаговым инструкциям, чтобы добавить summary tasks, управлять hierarchy
  и установить document directory.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Как создать расписание проекта с Aspose.Tasks для Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Как создать расписание проекта с Aspose.Tasks для Java
url: /ru/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать график проекта с помощью Aspose.Tasks для Java

## Введение
В этом руководстве вы узнаете, как **создать график проекта** в Java‑приложении с использованием Aspose.Tasks. Независимо от того, создаёте ли вы простой список дел или сложный корпоративный планировщик, нижеописанные шаги покажут, как добавить сводные задачи, управлять иерархией проекта и задать каталог документов — все с понятными, исполняемыми фрагментами кода. К концу вы получите полностью структурированный график, готовый к дальнейшему использованию или экспорту.

## Быстрые ответы
- **Что управляет Aspose.Tasks?** Он обрабатывает иерархии задач, ресурсы, календари и форматы файлов проектов (MS‑Project, Primavera и др.).  
- **Нужна ли лицензия для разработки?** Для оценки достаточно бесплатной временной лицензии; полная лицензия требуется для продакшн‑использования.  
- **Какая версия Java поддерживается?** Полностью поддерживаются Java 8 и новее.  
- **Можно ли добавить пользовательские поля к задачам?** Да, задачи можно расширять пользовательскими полями через API.  
- **Есть ли встроенная поддержка диаграмм Ганта?** Aspose.Tasks может экспортировать в PDF/HTML, включающие визуализацию Ганта.

## Что такое график проекта в Aspose.Tasks?
График проекта — это полный набор задач, зависимостей и сроков, определяющих порядок выполнения работы. Aspose.Tasks хранит эту информацию в объекте `Project`, который можно читать, изменять и сохранять в различных форматах. Он включает даты начала и окончания, ограничения и назначения ресурсов, обеспечивая всестороннее планирование и отчётность.

## Почему стоит использовать Aspose.Tasks для управления проектами на Java?
Aspose.Tasks поддерживает **более 30 форматов ввода и вывода** и может обрабатывать проекты с **до 10 000 задач** без загрузки всего файла в память, обеспечивая высокую производительность в масштабных сценариях управления проектами на Java.

## Требования
Прежде чем приступить к руководству, убедитесь, что у вас есть следующее:
- **Java Development Kit (JDK)** — установлен JDK 8 или новее.  
- **Библиотека Aspose.Tasks for Java** — скачайте и установите её с [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
- **Интегрированная среда разработки (IDE)** — используйте Eclipse, IntelliJ IDEA или любую другую удобную Java‑IDE.

## Импорт пакетов
`Project`, `Task` и связанные классы находятся в пространстве имён `com.aspose.tasks`. Импортируйте их в начале вашего Java‑файла:

Класс `Project` представляет собой полный график проекта и предоставляет методы для работы с задачами и ресурсами.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Класс `Project` является точкой входа для всех операций с файлом проекта.

## Как создать график проекта с помощью Aspose.Tasks?

Загрузите новый экземпляр `Project`, задайте каталог документов и начните добавлять задачи. Этот абзац‑ответ объясняет основной процесс: вы создаёте `Project`, настраиваете его `RootFolder` (каталог документов), затем добавляете сводную задачу и подзадачи. Все изменения находятся в памяти до вызова `save`, который сохраняет график в файл.

### Шаг 1: установить каталог документов
Определите, куда будет записан результирующий файл проекта. Установка каталога заранее гарантирует, что все последующие операции сохранения используют единый путь.

Свойство `RootFolder` указывает базовую папку, из которой читаются или в которую записываются файлы проекта.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Шаг 2: создать новый проект
Создайте новый объект `Project`, который будет хранить ваш график. При желании можно передать путь к уже существующему файлу, чтобы загрузить и изменить существующий график.

Конструктор `Project` создаёт пустой график, готовый к добавлению задач.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Шаг 3: добавить сводную задачу
Сводная задача группирует связанные подзадачи и отображается как сворачиваемый узел в диаграммах Ганта. Используйте класс `Task` и установите `IsSummary` в `true`.

Метод `addTask` создаёт новую задачу под указанным родителем и возвращает её идентификатор.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Шаг 4: добавить подзадачу
Подзадачи наследуют даты начала/окончания от своей сводной задачи, если их не переопределить. Добавление подзадачи сводится к повторному вызову `addTask` с указанием идентификатора родителя.

Вызов `addTask` с идентификатором родителя добавляет подзадачу под эту сводную задачу.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Продолжайте добавлять столько задач и подзадач, сколько необходимо для вашего проекта. Каждый шаг способствует построению структурированной иерархии проекта, которую можно экспортировать в MS‑Project, PDF или другие поддерживаемые форматы.

## Распространённые проблемы и решения
- **Проблема:** «Каталог документов не найден».  
  **Решение:** Убедитесь, что путь, указанный в `RootFolder`, существует в файловой системе и у вашего Java‑процесса есть права на запись.
- **Проблема:** Подзадачи не отображаются под сводной задачей.  
  **Решение:** Проверьте, что вы передаёте правильный идентификатор родительской задачи при вызове `addTask`. API требует идентификатор родителя во втором аргументе.
- **Проблема:** Большие проекты вызывают `OutOfMemoryError`.  
  **Решение:** Aspose.Tasks обрабатывает задачи в режиме потоковой передачи; увеличьте размер кучи JVM (`-Xmx2g`) или разбейте график на несколько файлов.

## Часто задаваемые вопросы
**В: Подходит ли Aspose.Tasks для небольших проектов?**  
О: Абсолютно. Библиотека масштабируется от одиночного списка задач до корпоративных графиков с тысячами задач.

**В: Где найти подробную документацию по Aspose.Tasks for Java?**  
О: Обратитесь к документации [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**В: Как получить временную лицензию для Aspose.Tasks?**  
О: Посетите страницу [temporary license request page](https://purchase.aspose.com/temporary-license/) для получения ограниченной по времени лицензии, подходящей для разработки и тестирования.

**В: Можно ли настраивать атрибуты задач с помощью Aspose.Tasks?**  
О: Да, задачи можно расширять пользовательскими полями, назначать ресурсы и программно изменять календари.

**В: Есть ли сообщество поддержки пользователей Aspose.Tasks?**  
О: Конечно! Присоединяйтесь к сообществу Aspose.Tasks на [the support forum](https://forum.aspose.com/c/tasks/15).

---

**Последнее обновление:** 2026-09-25  
**Тестировано с:** Aspose.Tasks 24.12 for Java  
**Автор:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Связанные руководства

- [Установить дату начала проекта в MS Project с помощью Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
- [Создать зависимости задач в Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Как добавить ресурс в проект и создать назначения ресурсов в Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}