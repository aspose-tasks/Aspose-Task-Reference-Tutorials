---
date: 2026-07-29
description: Узнайте, как планировать нерабочие дни, создавая календарь проекта с
  Aspose.Tasks for Java, определяя исключения по будням и управляя расписанием праздников.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Планирование нерабочих дней – создание календаря проекта Aspose
og_description: Планируйте нерабочие дни с помощью Aspose.Tasks for Java. Узнайте,
  как определять будни, добавлять исключения в календаре и эффективно управлять расписанием
  праздников.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Планирование нерабочих дней – создание календаря проекта Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Планирование нерабочих дней – создание календаря проекта Aspose
url: /ru/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Планы нерабочих дней – Создание календаря проекта Aspose

### Введение
Когда вам нужно **планировать нерабочие дни** для проекта, вы должны иметь возможность моделировать праздники, специальные смены или временные закрытия непосредственно в плане проекта. Aspose.Tasks for Java предоставляет вам полный контроль над определениями календаря, позволяя добавлять исключения, отражающие реальные графики. В этом руководстве мы пройдем точные шаги по определению будних дней для исключений календаря, чтобы графики вашего проекта оставались точными и надежными. К концу вы также увидите, как это вписывается в более широкую стратегию **расписания нерабочих дней** для любого корпоративного проекта.

## Быстрые ответы
- **Что означает «планировать нерабочие дни»?**  
  Это означает использование Aspose.Tasks для создания календаря, который помечает определённые даты как нерабочие, автоматически влияя на даты задач.  
- **Нужна ли лицензия для запуска примера?**  
  Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.  
- **Какие IDE поддерживаются?**  
  IntelliJ IDEA, Eclipse, NetBeans, или любая IDE, поддерживающая Java 8+.  
- **Можно ли добавить несколько исключений в один календарь?**  
  Да — вы можете добавить столько объектов `CalendarException`, сколько потребуется.  
- **В какие форматы файлов можно сохранить проект?**  
  XML, MPP и несколько других форматов, поддерживаемых Aspose.Tasks.  

## Что такое календарь проекта в Aspose.Tasks?
**Календарь проекта** — это объект верхнего уровня Aspose.Tasks, определяющий рабочие дни и часы для проекта. Он напрямую влияет на даты начала/завершения задач, распределение ресурсов и общие расчёты расписания. Настраивая календарь, вы гарантируете, что расписание учитывает реальные ограничения, такие как корпоративные праздники или правила работы в выходные.

## Зачем определять будние дни для исключений календаря?
Определение исключений для будних дней гарантирует, что движок проекта будет рассматривать эти дни как нерабочие, предотвращая автоматическое планирование задач на них и поддерживая согласованность графика с реальными ограничениями, такими как праздники, окна обслуживания или специальные графики смен в организации.

- **Точные сроки:** Задачи не будут размещаться в праздничные или черные периоды.  
- **Планирование ресурсов:** Ресурсы распределяются только в рабочие дни, предотвращая переутомление.  
- **Соответствие:** Расписания автоматически следуют политике организации или официальным календарям праздников.  

## Расписание нерабочих дней с исключениями календаря
Когда вы поддерживаете **расписание нерабочих дней**, обычно имеется основной список праздников, окон обслуживания или других черных периодов. Добавление этих дат в виде объектов `CalendarException` гарантирует, что каждый расчёт — будь то анализ критического пути или выравнивание ресурсов — автоматически учитывает эти ограничения. Такой подход устраняет ручные корректировки дат и снижает риск отклонения графика.

## Требования
1. **Java Development Kit (JDK)** – версия 8 или новее.  
2. **Aspose.Tasks for Java** – загрузите с официальной [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, NetBeans или любой совместимый с Java редактор.  

## Как планировать нерабочие дни с использованием исключений календаря

Загрузите ваш проект, создайте пользовательский календарь и добавьте объекты `CalendarException`, которые помечают выбранные будние дни как нерабочие. Весь процесс можно выполнить за несколько простых шагов, и полученный календарь автоматически будет влиять на всю логику планирования задач.

### Пошаговое руководство

### Шаг 1: Импортировать необходимые пакеты
We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for date handling.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Шаг 2: Определить каталог данных
Specify where the generated project file will be saved.

```java
String dataDir = "Your Data Directory";
```

### Шаг 3: Создать экземпляр проекта
`Project` is the main object that holds all project data, including tasks, resources, and calendars.

```java
Project project = new Project();
```

### Шаг 4: Определить календарь
`Calendar` represents a schedule of working and non‑working times within a project.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Шаг 5: Определить исключение для будних дней
`CalendarException` represents a period that is marked as non‑working in a calendar.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Шаг 6: Сохранить проект
Persist the project, including the custom calendar and its exception, to an XML file.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|----------|
| **Даты исключений не применяются** | Убедитесь, что `setEnteredByOccurrences(false)` и правильные значения `FromDate/ToDate`. |
| **Сохранённый файл пустой** | Проверьте, что `dataDir` указывает на папку с правом записи, и имя файла заканчивается на `.xml`. |
| **Календарь не учитывается при планировании задач** | Назначьте календарь задачам или ресурсам с помощью `task.setCalendar(cal)` или `resource.setCalendar(cal)`. |

## Часто задаваемые вопросы

**Q: Могу ли я определить несколько исключений для разных будних дней в одном календаре?**  
A: Да. Добавьте дополнительные объекты `CalendarException` в `cal.getExceptions()` для каждого отдельного периода или правила.

**Q: Совместим ли Aspose.Tasks for Java с различными IDE Java?**  
A: Абсолютно. Библиотека работает с IntelliJ IDEA, Eclipse, NetBeans и любой IDE, поддерживающей стандартные Java‑проекты.

**Q: Могу ли я настроить типы исключений, отличные от ежедневных?**  
A: Да. Используйте `CalendarExceptionType.Weekly`, `Monthly` или `Yearly` в соответствии с вашими потребностями планирования.

**Q: Как можно обрабатывать исключения динамически в зависимости от требований проекта?**  
A: Создавайте объекты исключений программно, например, считывайте даты праздников из базы данных или конфигурационного файла и создавайте экземпляры `CalendarException` в цикле.

**Q: Доступна ли пробная версия Aspose.Tasks for Java?**  
A: Да, вы можете скачать бесплатную пробную версию со [страницы загрузки Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).

## Заключение
Следуя этим шагам, вы теперь знаете, как **планировать нерабочие дни**, создавая календарь проекта и определяя исключения для будних дней, точно отражающие праздники или специальные нерабочие периоды. Правильная настройка календаря необходима для реалистичных расписаний, распределения ресурсов и общего успеха проекта. Исследуйте дальше, привязывая пользовательский календарь к задачам или ресурсам и экспериментируя с другими типами исключений, чтобы построить всестороннее **расписание нерабочих дней** для любого проекта.

---

**Последнее обновление:** 2026-07-29  
**Тестировано с:** Aspose.Tasks for Java 24.11  
**Автор:** Aspose

## Связанные руководства

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Create Calendar Exception Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)
- [How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}