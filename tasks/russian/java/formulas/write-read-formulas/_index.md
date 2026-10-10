---
date: 2026-10-10
description: Узнайте, как создать custom field aspose в Java, применить double task
  cost formula и сохранить project file с помощью Aspose.Tasks. Включает чтение формул
  MS Project.
keywords:
- create custom field aspose
- double task cost formula
- add custom field formula
- calculate task cost
lastmod: 2026-10-10
linktitle: Пример формулы Custom Field – Save Project File
og_description: Узнайте, как создать custom field aspose в Java, применить double
  task cost formula и сохранить project file с помощью Aspose.Tasks. Включает чтение
  формул MS Project.
og_image_alt: 'Guide: create custom field aspose and save project file with Aspose.Tasks
  Java'
og_title: Как создать custom field aspose и сохранить project file
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to create custom field aspose in Java, apply a double task
    cost formula, and save the project file using Aspose.Tasks. Includes reading MS
    Project formulas.
  headline: How to create custom field aspose and save project file
  type: TechArticle
- description: Learn how to create custom field aspose in Java, apply a double task
    cost formula, and save the project file using Aspose.Tasks. Includes reading MS
    Project formulas.
  name: How to create custom field aspose and save project file
  steps:
  - name: '**Java Development Kit (JDK)** – Java 8 or higher installed on your machine.'
    text: '**Java Development Kit (JDK)** – Java 8 or higher installed on your machine.'
  - name: '**Aspose.Tasks for Java** – Download and install from [Aspose.Tasks Java
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download and install from [Aspose.Tasks Java
      download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Integrated Development Environment (IDE)** – Choose your preferred IDE
      for Java development (IntelliJ IDEA, Eclipse, VS Code, etc.).'
    text: '**Integrated Development Environment (IDE)** – Choose your preferred IDE
      for Java development (IntelliJ IDEA, Eclipse, VS Code, etc.).'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of MS Project versions, from older
      .mpp formats to the latest releases, covering over 30 file format variations.
    question: Is Aspose.Tasks compatible with all versions of MS Project?
  - answer: Absolutely. The API is designed for seamless integration; just add the
      Aspose.Tasks JAR to your project’s classpath and start using the `Project` class.
    question: Can I integrate Aspose.Tasks into my existing Java project?
  - answer: The library supports most native MS Project formula syntax, including
      arithmetic, logical, and built‑in functions. Complex custom functions may require
      workarounds, but common calculations like **double task cost formula** work
      out of the box.
    question: Are there any limitations to the types of formulas I can create?
  - answer: Yes, the library runs on any platform that supports Java, including Windows,
      Linux, and macOS, and can handle projects up to 2 GB without loading the entire
      file into memory.
    question: Does Aspose.Tasks support multi‑platform deployment?
  - answer: Visit the [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)
      for community help, or open a support ticket if you have a commercial license.
    question: How can I get technical support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- custom field
- Aspose.Tasks
- Java project automation
title: Как создать custom field aspose и сохранить project file
url: /ru/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать пользовательское поле aspose и сохранить файл проекта

## Введение
В этом руководстве вы увидите **custom field formula example**, который показывает, как **save a project file**, писать и читать формулы MS Project и применять **double task cost formula** с использованием Aspose.Tasks for Java. К концу вы поймёте, почему пользовательские поля мощны, как встраивать вычисления непосредственно в проект и как сохранять эти изменения для последующей отчётности. Основное внимание уделено **create custom field aspose**, чтобы вы могли автоматизировать расчёт стоимости в любом рабочем процессе, основанном на MS Project.

## Быстрые ответы
- **What does “save project file” do?** Он записывает все изменения в памяти обратно в файл .mpp на диске.  
- **Can I add custom field formulas?** Да — вы можете создать пользовательское поле и назначить формулу, например “double task cost”.  
- **Do I need a license to run the code?** Бесплатная пробная версия подходит для оценки; для продакшна требуется коммерческая лицензия.  
- **Which IDE works best?** Любая Java IDE (IntelliJ IDEA, Eclipse, VS Code) скомпилирует пример.  
- **Is the API compatible with the latest MS Project version?** Aspose.Tasks поддерживает все последние форматы .mpp.

## Что такое “save project file” в Aspose.Tasks?
Сохранение файла проекта означает сохранение текущего состояния объекта `Project` — включая задачи, ресурсы и любые пользовательские формулы — в физический файл Microsoft Project (`.mpp`). Эта операция необходима после изменения данных, например после добавления пользовательского поля или изменения стоимости задач. Вызов `save` записывает полную структуру проекта на диск, делая изменения доступными для downstream‑инструментов отчётности.

## Зачем добавлять пользовательское поле и создавать формулу пользовательского поля?
Вы добавляете пользовательское поле, когда нужно хранить информацию, которую не покрывают встроенные поля. Привязка формулы — например **double task cost** — автоматизирует расчёты, устраняет ручные обновления и гарантирует, что каждый раз при изменении базовой стоимости производное значение обновляется мгновенно. Такой подход уменьшает ошибки и поддерживает согласованность данных расписания между командами.

## Предварительные требования
1. **Java Development Kit (JDK)** – Java 8 или выше, установленный на вашем компьютере.  
2. **Aspose.Tasks for Java** – Скачайте и установите со страницы [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Выберите предпочитаемую IDE для разработки на Java (IntelliJ IDEA, Eclipse, VS Code и т.д.).  

## Импорт пакетов
Классы `Project`, `ExtendedAttribute` и связанные находятся в пространстве имён `com.aspose.tasks`. Импортируйте их в начале вашего исходного файла, чтобы компилятор мог разрешить типы.

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Шаг 1: настройка каталога данных
Определите папку, где хранятся ваши файлы MS Project. Здесь вы загрузите исходный файл и позже **save project file**.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

## Шаг 2: загрузка файла проекта
Класс `Project` представляет файл Microsoft Project в памяти, предоставляя доступ к задачам, ресурсам и пользовательским полям. Загрузка файла даёт вам манипулируемую объектную модель.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Шаг 3: добавление пользовательского поля и создание формулы пользовательского поля
На этом этапе мы **add a custom field** “Double Costs” и **create a custom field formula**, которая умножает `[Cost]` задачи на 2, эффективно реализуя **double task cost formula**. Метод `setFormula` встраивает вычисление непосредственно в файл проекта.

```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```

## Шаг 4: добавление задачи и установка стоимости
Создайте новую задачу, затем задайте базовую стоимость `100`. При сохранении проекта пользовательское поле автоматически отобразит `200` благодаря ранее определённой формуле.

```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```

## Шаг 5: сохранение файла проекта
Метод `save` записывает обновлённый проект, включая новое пользовательское поле и его вычисленные значения, в `saved.mpp`. Это сохраняет изменения **create custom field aspose** для любых downstream‑потребителей.

```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|----------|----------|
| **Formula not applied** | Пользовательское поле не добавлено в коллекцию `ExtendedAttributes` проекта. | Убедитесь, что `project.getExtendedAttributes().add(attr);` выполнен перед сохранением. |
| **File not found** | Неправильный путь `dataDir`. | Проверьте, что строка каталога заканчивается разделителем пути (`/` или `\\`). |
| **Cost appears as 0** | Стоимость задачи не установлена перед сохранением. | Вызовите `task.set(Tsk.COST, ...)` перед `project.save`. |

## Часто задаваемые вопросы
**Q: Is Aspose.Tasks compatible with all versions of MS Project?**  
A: Да, Aspose.Tasks поддерживает широкий спектр версий MS Project, от старых форматов .mpp до последних релизов, охватывая более 30 вариантов форматов файлов.

**Q: Can I integrate Aspose.Tasks into my existing Java project?**  
A: Абсолютно. API спроектирован для бесшовной интеграции; просто добавьте Aspose.Tasks JAR в classpath вашего проекта и начните использовать класс `Project`.

**Q: Are there any limitations to the types of formulas I can create?**  
A: Библиотека поддерживает большинство нативных синтаксисов формул MS Project, включая арифметические, логические и встроенные функции. Сложные пользовательские функции могут потребовать обходных решений, но обычные расчёты, такие как **double task cost formula**, работают из коробки.

**Q: Does Aspose.Tasks support multi‑platform deployment?**  
A: Да, библиотека работает на любой платформе, поддерживающей Java, включая Windows, Linux и macOS, и может обрабатывать проекты до 2 GB без загрузки полного файла в память.

**Q: How can I get technical support for Aspose.Tasks?**  
A: Посетите [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15) для помощи сообщества или откройте тикет поддержки, если у вас коммерческая лицензия.

## Заключение
В этом **custom field formula example** мы рассмотрели, как **save project file**, **add a custom field** и **create a double task cost formula**, автоматически удваивающую стоимость задачи. Следуя этим шагам, вы можете автоматизировать расчёты, обогатить данные проекта и гарантировать, что все изменения сохраняются для будущей отчётности и анализа. Техника **create custom field aspose** — мощный способ расширить MS Project без ручной работы в таблицах.

---

**Последнее обновление:** 2026-10-10  
**Тестировано с:** Aspose.Tasks for Java 24.12  
**Автор:** Aspose

## Связанные руководства

- [Как создать файл MPP – создать и сохранить пустой проект в формате MPP с Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Как создать проект aspose.tasks – установить новые атрибуты задачи](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Чтение расширенных атрибутов задачи с Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}