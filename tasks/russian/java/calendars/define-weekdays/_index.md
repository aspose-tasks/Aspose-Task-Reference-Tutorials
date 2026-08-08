---
date: 2026-08-08
description: Узнайте, как настроить календарь MS Project, установить ежедневные рабочие
  часы и добавить рабочие дни в выходные, используя Aspose.Tasks для Java. Сохраните
  проект в формате XML всего за несколько строк кода.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Как настроить календарь MS Project и определить рабочие дни недели
og_description: Настройте календарь MS Project, определите рабочие дни недели и добавьте
  рабочие дни в выходные с помощью Aspose.Tasks для Java. Следуйте пошаговому руководству
  и сохраните в XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Настройка календаря MS Project с Aspose.Tasks – руководство по Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Как настроить календарь MS Project и определить рабочие дни недели
url: /ru/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить календарь ms project и определить рабочие дни

В этом руководстве вы узнаете **how to set calendar ms project** программно, определите рабочие дни недели и настроите пользовательские рабочие дни с помощью библиотеки Aspose.Tasks для Java. Независимо от того, создаёте ли вы движок планирования, интегрируетесь с ERP‑системами или просто нужно сгенерировать план проекта без открытия Microsoft Project, ниже приведённые шаги покажут, как создать календарь, задать ежедневные рабочие часы и добавить рабочие дни выходных в несколько строк кода.

## Быстрые ответы
- **Какая библиотека требуется?** Aspose.Tasks for Java.  
- **Могу ли я добавить рабочие дни выходных?** Да — просто пометьте субботу и воскресенье как рабочие дни.  
- **Как сохранить проект?** Вызовите `prj.save(..., SaveFileFormat.Xml)`.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для оценки; для использования в продакшене требуется лицензия.  
- **Какая версия Java поддерживается?** Java 8 или выше.

## Что такое set calendar ms project?
Установка календаря в MS Project определяет, какие дни считаются рабочими, количество рабочих часов в каждый день и любые специальные исключения, такие как праздники или общекорпоративные закрытия. Эта информация управляет планированием задач, распределением ресурсов и общими сроками проекта, обеспечивая, что расчёты учитывают реальные рабочие паттерны организации.

## Почему использовать Aspose.Tasks для работы с календарём?
Aspose.Tasks предоставляет программный контроль над календарями без запуска пользовательского интерфейса Microsoft Project. Он работает на любой ОС, поддерживающей Java, поддерживает более 50 форматов ввода и вывода и может обрабатывать проекты в сотни страниц без загрузки всего файла в память, что делает его идеальным для серверной автоматизации.

## Предварительные требования
- **Java Development Kit (JDK) 8+** – загрузите с [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – получите последнюю JAR с [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
- IDE или система сборки (Maven/Gradle) для добавления JAR Aspose.Tasks в classpath.

## Импорт пакетов
Импортируйте классы, предоставляющие доступ к проектам, календарям и объектам рабочего времени.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Пошаговое руководство

### Шаг 1: создать экземпляр проекта
Создайте объект `Project`, который представляет файл MS Project, с которым вы будете работать.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Шаг 2: определить новый календарь
`Calendar` представляет набор рабочих часов, исключений и праздников для проекта.  

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Шаг 3: добавить стандартные рабочие дни (понедельник‑четверг)
`WeekDay` определяет рабочее время для конкретного дня недели.  

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Шаг 4: добавить рабочие дни выходных
Если ваш проект работает в выходные, добавьте субботу и воскресенье как обычные рабочие дни. Это демонстрирует **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Шаг 5: задать пользовательский короткий рабочий день (пятница)
Настройте пятницу с утренней сменой (9 – 12) и послеобеденной сменой (13 – 16), чтобы продемонстрировать **set daily working hours** и пользовательский короткий рабочий день.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Шаг 6: сохранить проект в формате XML
`SaveFileFormat` перечисляет поддерживаемые форматы файлов при сохранении проекта, такие как XML или MPP.  

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Распространённые проблемы и решения
| Issue | Solution |
|-------|----------|
| **Working times not applied** | Убедитесь, что `setDayWorking(true)` вызывается для каждого пользовательского `WeekDay`. |
| **File not found when saving** | Проверьте, что `dataDir` указывает на существующую папку и приложение имеет права записи. |
| **Calendar not reflected in tasks** | Назначьте только что созданный календарь ресурсам или задачам с помощью `task.setCalendar(cal)`. |

## Часто задаваемые вопросы

**Q: Могу ли я определить пользовательские нерабочие дни с помощью Aspose.Tasks for Java?**  
A: Да. Установите свойство `DayWorking` в `false` для любого `WeekDay`, который вы хотите сделать нерабочим.

**Q: Как добавить праздники или общекорпоративные исключения?**  
A: Создайте объекты `CalendarException`, укажите даты исключений и добавьте их в `cal.getExceptions()`.

**Q: Совместима ли библиотека со старыми версиями MS Project?**  
A: Абсолютно. Aspose.Tasks поддерживает форматы MPP, MPT и XML для разных версий Project.

**Q: Могу ли я изменить существующий календарь в импортированном проекте?**  
A: Загрузите проект с помощью `new Project("existing.mpp")`, получите нужный календарь, внесите изменения и сохраните.

**Q: Обрабатывает ли Aspose.Tasks также повторяющиеся задачи?**  
A: Да, вы можете создавать и редактировать повторяющиеся задачи с помощью класса `RecurringTask`.

## Заключение
Теперь вы знаете **how to set calendar ms project**, как определить рабочие дни недели, добавить рабочие дни выходных и настроить короткий график на пятницу — всё с помощью Aspose.Tasks for Java. Сохраните результат в формате XML и интегрируйте логику календаря в любое Java‑основанное решение для управления проектами.

---

**Последнее обновление:** 2026-08-08  
**Тестировано с:** Aspose.Tasks for Java 24.11  
**Автор:** Aspose

## Связанные руководства

- [Добавить календарь в проект с Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Определить рабочие дни и часы с Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Добавить праздники в календарь и сохранить как MPP с Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}