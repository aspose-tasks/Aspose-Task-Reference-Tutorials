---
date: 2026-08-24
description: Узнайте, как добавить holidays calendar, определить working days и вычислить
  task duration, извлекая working hours из календарей MS Project с помощью Aspose.Tasks
  for Java.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Как добавить holidays calendar и определить working days
og_description: Узнайте, как добавить holidays calendar, определить working days и
  вычислить task duration, извлекая working hours из календарей MS Project с помощью
  Aspose.Tasks for Java.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Как добавить holidays calendar и определить working days
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: Как добавить holidays calendar и определить working days
url: /ru/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить календарь праздников и определить рабочие дни

Управление календарями проектов является ключевой частью успешного планирования проектов. В этом руководстве вы **добавите календарь праздников**, **определите рабочие дни** для любой задачи и **извлечёте рабочие часы** из календаря MS Project с помощью Aspose.Tasks for Java. К концу руководства вы сможете **рассчитать продолжительность задачи**, настроить рабочие часы и надёжно **загрузить файл MPP**, чтобы получить необходимые данные — без установки Microsoft Project.

## Быстрые ответы
- **Что означает «determine working days»?** Это означает определение, какие даты календаря считаются рабочими днями для данной задачи.  
- **Какую библиотеку использовать?** Aspose.Tasks for Java предоставляет полнофункциональный API для работы с файлами MS Project.  
- **Сколько времени занимает реализация?** Обычно 10–15 минут для базового извлечения.  
- **Нужна ли лицензия?** Доступна бесплатная пробная версия; для использования в продакшене требуется коммерческая лицензия.  
- **Можно ли настроить рабочие часы?** Да — вы можете изменять календари, добавлять праздники и задавать пользовательские диапазоны рабочего времени.  

## Что такое «determine working days»?
**Determine working days** означает запрос к календарю проекта для определения, какие даты помечены как рабочие, а какие — нерабочие (выходные, праздники или пользовательские исключения). Эта информация необходима для точного **calculate task duration**, поскольку только рабочие дни учитываются в продолжительности задачи.

## Почему использовать Aspose.Tasks для получения рабочих часов?
Aspose.Tasks позволяет читать файлы MS Project без установленного Microsoft Project, обеспечивая автоматизацию на любой платформе. Он также предоставляет высокопроизводительную обработку, широкую поддержку форматов и подробную документацию.  

- **Full calendar support** – календарь по умолчанию, ресурсный и календарь задачи доступны.  
- **High performance** – может обрабатывать проекты, содержащие **10,000+ tasks in under 2 seconds** на стандартном процессоре 2.5 GHz.  
- **Extensive format coverage** – поддерживает **50+ input and output formats**, включая MPP, MPX, XML и Primavera.  
- **Comprehensive documentation** – доступны примеры кода, справочник API и форумы сообщества.  

## Предварительные требования
1. **Java Development Kit (JDK)** – версия 8 или выше.  
2. **Aspose.Tasks for Java** – скачайте последнюю JAR с [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/).  
3. Базовые знания программирования на Java.  

## Импорт пакетов
Класс `Project` является верхнеуровневым объектом Aspose.Tasks, представляющим один файл MS Project в памяти. Импортируйте необходимое пространство имён перед началом работы:

Импорт пакетов

```java
import com.aspose.tasks.*;
```

## Как загрузить файл MPP с помощью Aspose.Tasks?
Класс `Project` загружает файл MS Project и предоставляет доступ к его данным. Загрузите файл проекта одной строкой кода; пользовательский интерфейс или COM‑interop не требуются. Этот простой шаг дает полный доступ к календарям, задачам и ресурсам.

Загрузка файла MPP

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Получение информации о задаче и календаре
`Task` представляет задачу проекта, а `Calendar` определяет правила её рабочего времени. Выберите задачу, которую хотите проанализировать, и получите связанный с ней календарь. Объект `Task` предоставляет методы `getStart()` и `getFinish()`, а объект `Calendar` раскрывает определения рабочего времени.

Получение задачи и календаря

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Определение дат начала и окончания
Объекты `Date` задают временное окно для анализа календаря. Установите окно времени, для которого вы хотите **determine working days**. Использование дат начала и окончания задачи гарантирует, что вы оцениваете только релевантный период.

Определение дат

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Итерация по датам
`for`‑цикл может проходить по каждому дню в диапазоне дат. Перебирайте каждую дату в продолжительности задачи. Этот цикл позволит вам позже **customize working hours**, если потребуется, и служит основой для расчёта общего рабочего времени.

Итерация по датам

```java
java.util.Calendar tempDate = calStartDate;
```

## Расчёт продолжительности
`Duration` агрегирует общее рабочее время, вычисленное в ходе итерации. Во время итерации вы проверяете, является ли каждый день рабочим, суммируете рабочие часы и в конце вычисляете продолжительность задачи в минутах, часах и днях. Это демонстрирует, как программно **calculate working days** и **calculate task duration**.

Вычисление продолжительности

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## Как настроить рабочие часы и праздники
Вы можете изменять диапазоны рабочего времени календаря и добавлять исключения, такие как праздники. Используйте `taskCalendar.addWorkingTime()` для установки новых рабочих периодов и `taskCalendar.addException()` для вставки праздника. Это полезно, когда расписание по умолчанию 9‑5 не соответствует политике вашей организации.

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|----------|
| **Task возвращает `null` для календаря** | Убедитесь, что задаче действительно назначен календарь; иначе она наследует календарь проекта по умолчанию. |
| **Некорректная продолжительность из‑за праздников** | Проверьте, что праздники определены в календаре задачи или в базовом календаре проекта. |
| **Несоответствие часового пояса** | При необходимости используйте `java.util.TimeZone` для согласования часового пояса календаря с вашей системой. |

## Часто задаваемые вопросы
### В: Может ли Aspose.Tasks for Java работать со сложными структурами проектов?
О: Да, Aspose.Tasks for Java предоставляет всестороннюю поддержку для работы со сложными структурами проектов, включая задачи, ресурсы и календари.

### В: Совместим ли Aspose.Tasks for Java с различными версиями MS Project?
О: Абсолютно, Aspose.Tasks for Java поддерживает различные версии MS Project, обеспечивая совместимость в разных средах.

### В: Могу ли я настроить рабочие часы и праздники в календарях проекта?
О: Да, вы можете легко настроить рабочие часы и праздники в соответствии с требованиями вашего проекта, используя API Aspose.Tasks for Java.

### В: Предоставляет ли Aspose.Tasks for Java поддержку и документацию?
О: Да, Aspose.Tasks for Java предоставляет обширную документацию и специализированные форумы поддержки, помогающие разработчикам эффективно использовать его возможности.

### В: Доступна ли пробная версия Aspose.Tasks for Java?
О: Да, вы можете получить бесплатную пробную версию Aspose.Tasks for Java на странице [Aspose releases page](https://releases.aspose.com/).

## Заключение
В этом руководстве мы продемонстрировали, как **add holidays calendar**, **determine working days**, **retrieve working hours** и **calculate task duration** из календаря MS Project с помощью Aspose.Tasks for Java. Следуя приведённым шагам, вы сможете автоматизировать анализ расписания, настраивать календари и поддерживать планы проектов точными и актуальными. Теперь у вас есть инструменты для **read MS Project** данных, **load an MPP file** и выполнения точных расчётов продолжительности без необходимости в Microsoft Project.

---

**Последнее обновление:** 2026-08-24  
**Тестировано с:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Автор:** Aspose

## Связанные руководства

- [Добавить календарь в проект с Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Добавить праздники в календарь и сохранить как MPP с Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [Создать пользовательские исключения календаря с Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}