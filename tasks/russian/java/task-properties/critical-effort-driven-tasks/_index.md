---
date: 2026-09-30
description: Управляйте critical tasks в Java‑проектах с помощью Aspose.Tasks. Узнайте,
  как работать с critical и effort‑driven tasks, скачайте библиотеку и улучшите ваш
  workflow управления проектами.
keywords:
- manage critical tasks java
- effort‑driven tasks Aspose.Tasks
- Java project management
lastmod: 2026-09-30
linktitle: Управление Critical и Effort-Driven Tasks в Aspose.Tasks
og_description: Управляйте critical tasks, с которыми сталкиваются Java‑разработчики,
  с помощью Aspose.Tasks. Это руководство показывает пошаговое выполнение critical
  и effort‑driven tasks в Java‑проектах (150‑160 символов).
og_image_alt: Screenshot of Aspose.Tasks Java API managing critical and effort‑driven
  tasks
og_title: Как управлять critical tasks в Java с помощью Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Manage critical tasks Java projects with Aspose.Tasks. Learn to handle
    critical and effort‑driven tasks, download the library and boost your project
    management workflow.
  headline: How to manage critical tasks in Java using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is platform‑independent and runs on Windows,
      Linux, and macOS.
    question: Can I use Aspose.Tasks for Java in both Windows and Linux environments?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java on the [Aspose.Tasks
      free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find support for Aspose.Tasks for Java?
  - answer: You can acquire a temporary license on the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: You can purchase Aspose.Tasks for Java from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- critical tasks
- effort‑driven tasks
- Aspose.Tasks
- Java
- project management
title: Как управлять critical tasks в Java с помощью Aspose.Tasks
url: /ru/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Управление критическими и задачами, основанными на усилиях, в Java с Aspose.Tasks

В современном управлении проектами **manage critical tasks java** является ежедневным вызовом для разработчиков, которым необходимо поддерживать графики в срок, одновременно работая с задачами, управляемыми усилием. Aspose.Tasks for Java предоставляет чистый программный способ идентифицировать, проверять и обновлять критические и задачи, управляемые усилием, без ручного обращения с электронными таблицами.

## Быстрые ответы
- **В чем основное преимущество?** Automatically flags critical tasks and adjusts effort‑driven scheduling in one API call.  
- **Нужна ли лицензия?** A free trial works for development; a commercial license is required for production.  
- **Какие версии Java поддерживаются?** Java 8 through 17, both OpenJDK and Oracle distributions.  
- **Можно ли обрабатывать крупные проекты?** Yes – Aspose.Tasks handles projects with up to 10 000 tasks efficiently.  
- **Это кроссплатформенное решение?** The library runs on Windows, Linux, and macOS without native dependencies.

## Как управлять критическими и задачами, основанными на усилиях, в Aspose.Tasks для Java?
Загрузите ваш файл проекта с помощью класса `Project`, используйте `ChildTasksCollector` для сбора всех задач, а затем проверьте свойства `Critical` и `EffortDriven` каждой задачи. Перебирая собранный список, вы можете создать отчет о статусе или автоматически изменить правила планирования, используя всего несколько строк кода Java, которые выполняются за секунды.

Aspose.Tasks for Java поддерживает **более 30 форматов ввода и вывода проектов** (включая Microsoft Project 2019, 2022 и Primavera P6) и может обрабатывать файлы с **до 10 000 задач**, при этом потребление памяти остаётся ниже 200 MB на типичном сервере. Такие измеримые возможности делают его подходящим для планирования корпоративного масштаба.

## Требования
- **Aspose.Tasks for Java** library – скачайте её из [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/).  
- **Java Development Kit (JDK)** – версия 8 или новее, установленная на вашем компьютере.  
- **IDE** по вашему выбору (IntelliJ IDEA, Eclipse, VS Code и т.д.).  
- Пример файла проекта в формате XML (или .mpp), который вы будете использовать для демонстрации.

## Импорт пакетов
Добавьте необходимые пространства имён в ваш Java‑файл:

```java
import com.aspose.tasks.*;
import java.util.*;
```

Эти импорты предоставляют доступ к основным классам управления задачами, таким как `Project`, `Task`, и вспомогательным утилитам.

## Что такое критическая задача?
**Критическая задача** — это любое действие, задержка которого напрямую продлевает дату завершения проекта, то есть она находится на критическом пути расписания. В Aspose.Tasks можно определить, является ли задача критической, вызвав метод `Task.isCritical()`, который возвращает `true`, когда задача влияет на общее время завершения проекта.

## Что такое задача, основанная на усилиях?
**Задача, основанная на усилиях** автоматически перераспределяет оставшуюся работу каждый раз, когда меняется её длительность, обеспечивая постоянный общий объём усилий в течение всего расписания. Такое поведение полезно для ресурсов, работающих с фиксированной скоростью. В Aspose.Tasks свойство `Task.isEffortDriven()` возвращает `true` для задач, обладающих этой характеристикой.

## Шаг 1: собрать задачи с помощью ChildTasksCollector
Класс `ChildTasksCollector` собирает каждую задачу, находящуюся под заданным родительским элементом.  

`ChildTasksCollector` — вспомогательный класс, который проходит по иерархии задач и возвращает плоский список объектов `Task`.

```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector);
List<Task> allTasks = collector.getTasks();
```

## Шаг 2: перебрать собранные задачи
Пройдитесь по списку и выведите статус критичности и основанности на усилиях каждой задачи.

```java
for (Task t : allTasks) {
    boolean isCritical = t.get(Tsk.Critical);
    boolean isEffortDriven = t.get(Tsk.EffortDriven);
    System.out.println("Task ID " + t.get(Tsk.Id) + 
        ": critical=" + isCritical + ", effortDriven=" + isEffortDriven);
}
```

Этот простой двухшаговый шаблон предоставляет полное представление о состоянии расписания проекта.

## Распространённые проблемы и их устранение
- **NullPointerException при доступе к свойствам задачи** – Убедитесь, что файл проекта полностью загружен перед доступом к задачам (`project = new Project("file.mpp")`).  
- **Некорректный флаг критичности** – Проверьте, что режим расчётов проекта установлен в `CalculationMode.Automatic`, чтобы Aspose.Tasks мог пересчитать критический путь после изменений.  
- **Большие файлы вызывают замедление** – Используйте `Project.set(Prj.ReadOnly, true)`, чтобы открыть файл в режиме только для чтения, что уменьшает нагрузку на память при анализе только для чтения.

## Часто задаваемые вопросы

**Q: Могу ли я использовать Aspose.Tasks for Java как в Windows, так и в Linux?**  
A: Да, Aspose.Tasks for Java независим от платформы и работает на Windows, Linux и macOS.

**Q: Доступна ли бесплатная пробная версия Aspose.Tasks for Java?**  
A: Да, вы можете получить бесплатную пробную версию Aspose.Tasks for Java на странице [Aspose.Tasks free trial download page](https://releases.aspose.com/).

**Q: Где я могу найти поддержку Aspose.Tasks for Java?**  
A: Посетите [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) для поддержки сообщества и обсуждений.

**Q: Как я могу получить временную лицензию для Aspose.Tasks for Java?**  
A: Вы можете получить временную лицензию на странице [temporary license request page](https://purchase.aspose.com/temporary-license/).

**Q: Где я могу приобрести Aspose.Tasks for Java?**  
A: Вы можете приобрести Aspose.Tasks for Java на [purchase page](https://purchase.aspose.com/buy).

**Последнее обновление:** 2026-09-30  
**Тестировано с:** Aspose.Tasks for Java 24.11  
**Автор:** Aspose  

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

## Связанные руководства

- [Критический путь MS Project – руководство Aspose.Tasks Java](/tasks/java/project-management/critical-path/)
- [Создание зависимостей задач управления проектом в Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Управление проектами Java: процент завершения задачи с использованием Aspose.Tasks](/tasks/java/task-properties/percentage-complete-calculations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}