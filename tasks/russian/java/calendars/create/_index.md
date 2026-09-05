---
date: 2026-08-03
description: Узнайте, как создать календарь ms project, добавить календарь в проект
  и сохранить проект в формате XML с помощью Aspose.Tasks для Java.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Добавить календарь в проект с использованием Aspose.Tasks
og_description: Программно создавайте календарь ms project с помощью Aspose.Tasks
  для Java. Добавляйте календари, настраивайте расписания и экспортируйте в XML за
  считанные минуты.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Создание календаря ms project с помощью Aspose.Tasks для Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Создание календаря ms project с помощью Aspose.Tasks для Java
url: /ru/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать календарь MS Project с Aspose.Tasks для Java

## Введение
В современных рабочих процессах управления проектами возможность **создавать календарь MS Project** программно может сэкономить часы ручного редактирования. Aspose.Tasks for Java предоставляет чистый, типобезопасный API для работы с файлами Microsoft Project без необходимости открывать настольный клиент. В этом руководстве вы узнаете, как добавить календарь, как создать календарь MS Project и как сохранить проект в формате XML — всё это с помощью всего нескольких строк кода на Java.

## Быстрые ответы
- **Что означает “create ms project calendar”?**  
  Это означает вставку нового определения рабочего времени (календаря) в файл Microsoft Project с помощью кода.  
- **Какая библиотека обрабатывает это?**  
  Aspose.Tasks for Java предоставляет класс `Calendar` и контейнер `Project` для управления календарями.  
- **Нужна ли лицензия?**  
  Временная оценочная лицензия подходит для тестирования; полная лицензия требуется для использования в продакшене.  
- **Можно ли сохранить файл в формате XML?**  
  Да — используйте `SaveFileFormat.Xml` для экспорта проекта в XML.  
- **Каковы предварительные требования?**  
  Java JDK 8+ и JAR‑файл Aspose.Tasks for Java в вашем classpath.

## Что такое создание календаря MS Project?
Создание календаря MS Project означает программное добавление нового определения календаря в файл проекта, указание рабочих дней, исключений и ежедневных рабочих часов, а затем назначение этого календаря задачам, ресурсам или всему проекту, чтобы расчёты расписания учитывали определённое рабочее время.

## Почему стоит использовать Aspose.Tasks for Java для добавления календаря в проект?
Вам следует использовать Aspose.Tasks for Java, потому что он предоставляет полностью типобезопасный API, который работает без установленного Microsoft Project, поддерживает все основные версии Project (2007‑2021, более 5 выпусков) и может экспортировать в XML, MPP и **10+** других форматов, позволяя автоматически создавать календари в больших объёмах на любом сервере.

## Предварительные требования
- **Java Development Kit (JDK) 8 или новее** установлен и настроен.  
- **Aspose.Tasks for Java** библиотека — скачайте с [официального сайта](https://releases.aspose.com/tasks/java/) и добавьте JAR в classpath вашего проекта.  
- Любая IDE или система сборки (Maven/Gradle) по вашему выбору.

## Пошаговое руководство

### Шаг 1: импортировать необходимый пакет Aspose.Tasks
Сначала импортируйте классы Aspose.Tasks, чтобы иметь возможность работать с проектами и календарями.

```java
import com.aspose.tasks.*;
```

### Шаг 2: установить путь к каталогу данных
Укажите, куда будет записан сгенерированный файл проекта. Замените заполнитель абсолютным или относительным путём на вашей машине.

```java
String dataDir = "Your Data Directory";
```

### Шаг 3: создать новый экземпляр Project
`Project` — основной класс, представляющий файл Microsoft Project в памяти.

```java
Project prj = new Project();
```

### Шаг 4: определить календари, которые вы хотите добавить
`Calendar` определяет расписание с рабочими днями, исключениями и рабочими часами для проекта.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Полезный совет:** После добавления календаря вы можете настроить его рабочие дни с помощью `cal1.getWeekDays().add(...)` и установить ежедневные рабочие часы, используя `cal1.getBaseCalendar().setWorkingTime(...)`.

### Шаг 5: сохранить проект (сохранить проект в формате XML)
`SaveFileFormat.Xml` указывает Aspose.Tasks записать проект в формате XML.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Шаг 6: вывести сообщение о завершении
Сообщите пользователю, что операция завершилась успешно.

```java
System.out.println("Process completed Successfully");
```

Следуя этим шести кратким шагам, вы успешно **добавили календарь в проект** и сохранили результат в виде XML‑файла.

## Распространённые проблемы и решения
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` на `prj.getCalendars()`** | Объект проекта не инициализирован корректно. | Убедитесь, что `new Project()` вызывается перед доступом к календарям. |
| **Файл не найден при сохранении** | `dataDir` указывает на несуществующую папку. | Создайте каталог сначала или используйте абсолютный путь. |
| **Имя календаря отображается как “no info”** | В примере использовались имена-заполнители. | Замените их на осмысленные имена, отражающие расписание (например, “US Holiday Calendar”). |
| **Сохранённый XML нельзя открыть в MS Project** | Используется устаревшая версия Aspose.Tasks. | Обновите до последней версии Aspose.Tasks for Java. |

## Часто задаваемые вопросы

**В: Может ли Aspose.Tasks работать со сложными календарями с множеством исключений?**  
A: Да — после добавления календаря вы можете определять исключения, рабочие часы и нерабочие дни, используя классы `WeekDay` и `Exception`.

**В: Можно ли назначить новый календарь конкретным задачам?**  
A: Конечно. Получите задачу через `prj.getRootTask().getChildren().add("Task Name")` и установите `task.set(Tsk.CALENDAR, cal3);`.

**В: Поддерживает ли библиотека сохранение в других форматах, например MPP?**  
A: Да. Замените `SaveFileFormat.Xml` на `SaveFileFormat.Mpp` или `SaveFileFormat.P6` при необходимости; Aspose.Tasks поддерживает **12** форматов вывода.

**В: Нужна ли лицензия для сборок разработки?**  
A: Временная оценочная лицензия достаточна для тестирования; полная лицензия требуется для продакшн‑развёртываний.

**В: Где можно получить помощь, если возникнут проблемы?**  
A: Сообщество форума Aspose.Tasks — отличный ресурс: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Последнее обновление:** 2026-08-03  
**Тестировано с:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как определить будние дни в календарях MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Как установить календарь проекта в Java с Aspose.Tasks](/tasks/java/calendars/properties/)
- [Создание пользовательских исключений календаря с Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}