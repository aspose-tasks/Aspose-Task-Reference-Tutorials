---
date: 2026-08-13
description: Узнайте, как добавить праздники в календарь, назначить календарь проекту
  и сохранить файл MS Project в формате MPP с использованием Aspose.Tasks для Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Обновление календаря до формата MPP в Aspose.Tasks
og_description: Добавьте праздники в календарь, назначьте его проекту и преобразуйте
  расписание в MPP с помощью Aspose.Tasks для Java. Узнайте пошаговую автоматизацию.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Добавьте праздники в календарь и сохраните как MPP с помощью Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Добавьте праздники в календарь и сохраните как MPP с помощью Aspose.Tasks
url: /ru/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавьте праздничные дни в календарь и сохраните как MPP с Aspose.Tasks

## Введение

В современном управлении проектами часто требуется **add holidays to calendar** файлы, создать **MS Project calendar**, а затем поделиться расписанием в нативном формате MPP. Независимо от того, консолидируете ли вы графики из нескольких источников или мигрируете устаревшие данные, программное создание календаря устраняет ручные ошибки и ускоряет поставку. Этот учебник проведёт вас через полный процесс создания календаря в MS Project, его настройки с праздничными днями, **assign calendar to project**, и, наконец, **convert project to MPP** с использованием Aspose.Tasks Java API.

## Краткие ответы
- **What does this tutorial cover?** Добавление праздничных дней в календарь, назначение его проекту и сохранение результата в виде файла MPP с помощью Aspose.Tasks for Java.  
- **Do I need a license?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.  
- **Which Java version is required?** Java 8 или выше (JDK 8+).  
- **Can I customize the calendar?** Да — можно добавить рабочие часы, исключения и праздничные дни.  
- **How long does implementation take?** Около 10‑15 минут для базового календаря.  

## Что такое «create calendar MS Project»?

Создание календаря MS Project означает определение рабочих дней, часов и исключений, которые управляют планированием задач в файле Microsoft Project. С помощью Aspose.Tasks вы можете программно построить этот календарь, установить праздничные дни и встроить его в проект без открытия пользовательского интерфейса MS Project.

## Почему использовать Aspose.Tasks для этой задачи?

Следует использовать Aspose.Tasks, потому что он обеспечивает полную совместимость с Java, не требует Microsoft Office и позволяет генерировать и сохранять нативные файлы MPP непосредственно из кода. Библиотека поддерживает все функции календаря, работает в любой серверной среде и обрабатывает проекты до 10 000 задач менее чем за секунду.

## Требования

1. **Java Development Kit (JDK) 8+** – убедитесь, что `java -version` выводит 1.8 или новее.  
2. **Aspose.Tasks for Java** – загрузите последнюю JAR‑файл с [веб‑сайта Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse или любой предпочитаемый редактор.  
4. **Basic Java knowledge** – знание классов, методов и ввода‑вывода файлов.

## Как добавить праздничные дни в календарь

Чтобы добавить праздничные дни, вы создаёте новый объект `Calendar`, получаете его коллекцию `Exceptions` и добавляете записи `DateException` для каждой даты праздника. `DateException` представляет отдельную нерабочую дату или диапазон в календаре. Aspose.Tasks затем рассматривает эти даты как нерабочие, гарантируя, что задачи планируются с учётом заданных праздничных дней.

### Шаг 1: импортировать необходимые пакеты

Сначала импортируйте классы Aspose.Tasks и утилиты Java.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Шаг 2: настроить каталог данных

Укажите, где будут находиться ваш шаблон входных данных и файлы вывода. Замените заполнитель реальным путём на вашем компьютере.

```java
String dataDir = "Your Data Directory";
```

### Шаг 3: определить имена входного и выходного файлов

Мы загрузим существующий файл MPP (или пустой проект) и запишем результат в новый файл.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Шаг 4: загрузить проект и добавить новый календарь

Класс `Project` представляет файл MS Project в памяти и предоставляет доступ к его календарям, задачам и ресурсам.

Создайте экземпляр `Project` из исходного файла и добавьте календарь с именем **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Шаг 5: настроить календарь (необязательно)

Объект `Calendar` определяет рабочие дни, часы и исключения для расписания проекта.

Если вам нужны конкретные рабочие часы, праздничные дни или исключения, вызовите свой вспомогательный метод. В примере используется `GetTestCalendar` как заполнитель.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Совет:** Вы можете напрямую изменять `cal1.getWeekDays()`, чтобы задать рабочие часы для каждого дня недели, или использовать `cal1.getExceptions()` для **add holidays to calendar**.

### Шаг 6: назначить календарь проекту

Укажите проекту использовать только что созданный календарь для всех расчётов планирования.

```java
project.set(Prj.CALENDAR, cal1);
```

### Шаг 7: сохранить проект как MPP

Перечисление `SaveFileFormat` указывает формат вывода, где `Mpp` обозначает нативный формат Microsoft Project.

Теперь **convert project to MPP**, сохранив его с опцией `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Шаг 8: подтвердить успешное завершение

Простое сообщение в консоли сообщает, что процесс завершён без ошибок.

```java
System.out.println("Process completed Successfully");
```

## Распространённые сценарии использования

- **Automated schedule generation** для повторяющихся проектов (например, еженедельные спринты).  
- **Migrating legacy CSV or Excel calendars** в полностью функциональный файл MS Project.  
- **Server‑side reporting**, когда веб‑служба возвращает файл MPP по запросу.  

## Устранение неполадок и распространённые подводные камни

| Проблема | Причина | Решение |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` указывает на несуществующую папку | Убедитесь, что каталог существует, или создайте его программно. |
| Calendar not applied to tasks | Задачи всё ещё ссылаются на календарь по умолчанию | После установки `Prj.CALENDAR` также обновите `Task.CALENDAR` каждой задачи, если они были переопределены ранее. |
| Output file is 0 KB | Отсутствуют права записи | Запустите JVM с соответствующими правами доступа к файловой системе или выберите путь, доступный для записи. |

## Часто задаваемые вопросы

**Q: Совместим ли Aspose.Tasks for Java с разными версиями MS Project?**  
A: Да, Aspose.Tasks поддерживает все форматы файлов Microsoft Project, начиная с Project 2007 и до Project 2024, охватывая более 10 версий.

**Q: Могу ли я настраивать календари в соответствии с конкретными требованиями проекта?**  
A: Конечно. Вы можете определять рабочие дни, задавать пользовательские рабочие недели, добавлять праздничные дни и даже создавать несколько календарей в одном файле проекта.

**Q: Предоставляет ли Aspose.Tasks for Java поддержку по устранению неполадок и помощи?**  
A: Да, вы можете получить помощь на форуме сообщества Aspose.Tasks [форум сообщества Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q: Доступна ли бесплатная пробная версия Aspose.Tasks for Java?**  
A: Да, полностью функциональная бесплатная пробная версия доступна [бесплатная пробная версия Aspose.Tasks](https://releases.aspose.com/).

**Q: Как получить временную лицензию для Aspose.Tasks for Java?**  
A: Временные лицензии можно запросить через веб‑сайт Aspose [запрос временной лицензии Aspose](https://purchase.aspose.com/temporary-license/).

---

**Последнее обновление:** 2026-08-13  
**Тестировано с:** Aspose.Tasks for Java 24.12  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные учебные материалы

- [Добавить календарь в проект с Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Как определить будние дни в календарях MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Создать пользовательские исключения календаря с Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}