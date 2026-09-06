---
date: 2026-08-13
description: Узнайте, как считывать рабочие недели из календаря MS Project с использованием
  Aspose.Tasks for Java. Следуйте пошаговому руководству с примерами кода и советами
  по устранению неполадок.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Считать рабочие недели из календаря с Aspose.Tasks
og_description: Как считывать рабочие недели из календаря MS Project с помощью Aspose.Tasks
  for Java. Следуйте лаконичному учебнику с шагами настройки, фрагментами кода и советами
  по устранению неполадок.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Как считывать рабочие недели из календаря MS с помощью Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Как считывать рабочие недели из календаря MS с помощью Aspose.Tasks
url: /ru/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как читать рабочие недели из календаря MS с помощью Aspose.Tasks

## Введение
В этом руководстве вы **узнаете, как читать рабочие недели** из календаря Microsoft Project с использованием библиотеки Aspose.Tasks для Java. Независимо от того, создаёте ли вы панель отчётов, синхронизируете расписания с ERP‑системой или автоматизируете извлечение данных для аналитики, программный доступ к определениям рабочих недель экономит бесчисленные часы ручного труда. Aspose.Tasks поддерживает **более 50 форматов ввода и вывода** и может обрабатывать проекты в несколько сотен страниц без загрузки всего файла в память, обеспечивая гибкость и производительность.

## Быстрые ответы
- **Что означает «читать рабочие недели»?** Это извлечение определений рабочих недель (дат и правил ежедневного рабочего времени) из файла Project с помощью кода Java.  
- **Какая библиотека требуется?** Aspose.Tasks для Java (доступна бесплатная пробная версия).  
- **Нужна ли лицензия для разработки?** Пробная версия подходит для тестирования; для продакшн‑развёртываний требуется коммерческая лицензия.  
- **Какие форматы файлов поддерживаются?** Обрабатываются как *.mpp*, так и файлы Project XML, плюс более 50 других форматов для импорта/экспорта.  
- **Сколько времени занимает реализация?** Обычно менее 10 минут после настройки библиотеки.

## Что такое рабочая неделя в MS Project?
Рабочая неделя определяет правила календаря, указывающие, когда ресурсы доступны в течение определённого периода. Она включает дату начала, дату окончания и интервалы рабочего времени для каждого дня (например, 9 ч–17 ч). В MS Project каждый календарь может содержать несколько рабочих недель, позволяя моделировать праздники, сменные графики или сезонные расписания.

## Как Aspose.Tasks читает рабочие недели из календаря?
Aspose.Tasks предоставляет доступ к `WorkWeekCollection` объекта `Calendar`. Создав экземпляр `Project`, выбрав нужный календарь (по UID или имени) и пройдясь по его `WorkWeekCollection`, вы можете получить метку каждой рабочей недели, её действительный диапазон дат и подробные интервалы рабочего времени по дням. API автоматически обрабатывает все преобразования даты‑времени и учитывает настройки часового пояса проекта.

## Зачем читать рабочие недели на Java из календаря Microsoft Project?
Программное чтение рабочих недель устраняет ручное копирование, гарантирует, что downstream‑системы (ERP, HR, отчётность) используют одинаковые правила планирования, и обеспечивает согласованность между несколькими проектами. Автоматизация также снижает риск человеческих ошибок и ускоряет интеграционные конвейеры, особенно когда необходимо обрабатывать десятки файлов проекта каждую ночь.

## Предварительные требования
Перед тем как перейти к коду, убедитесь, что у вас есть:

1. **Java Development Kit (JDK)** – установлен версия 8 или новее.  
2. **Aspose.Tasks для Java** – скачайте последнюю JAR‑файл с официального сайта: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. **Пример файла проекта** (`ReadWorkWeeksInformation.mpp`), размещённый в известной папке на вашем компьютере.

## Импорт пакетов
Сначала импортируйте классы, необходимые для работы с календарями и рабочими неделями:

`Project` представляет файл Microsoft Project, `Calendar` предоставляет доступ к его календарям, `WorkWeek` определяет рабочую неделю, а `WeekDay` представляет день.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Шаг 1: настройте каталог данных
Укажите папку, содержащую файл `.mpp`. Замените заполнитель реальным путём на вашем компьютере:

```java
String dataDir = "Your Data Directory";
```

## Шаг 2: создайте экземпляр Project и получите доступ к календарю
Класс `Project` представляет файл Microsoft Project и предоставляет доступ к его структурам данных, включая календари, задачи и ресурсы.  
Создайте объект `Project`, выберите нужный календарь (по UID) и получите его `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** Если вы не уверены в UID календаря, пройдитесь по `project.getCalendars()` и сначала выведите имя и UID каждого календаря.

## Шаг 3: переберите рабочие недели
Класс `WorkWeek` инкапсулирует определение рабочей недели, включая даты начала/окончания и настройки рабочего времени по дням.  
Пройдитесь по каждому `WorkWeek`, чтобы вывести его название, даты начала/окончания и ежедневные рабочие часы:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Что вы увидите:** Консоль выводит метку каждой рабочей недели (например, “Standard”), её действительный диапазон дат, а также подробные часы работы для каждого дня.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|----------|
| `NullPointerException` при доступе к `calendar` | Неправильный UID или календарь не существует | Проверьте UID с помощью `project.getCalendars().size()` и сначала выведите список доступных календарей. |
| Отсутствует вывод для рабочих недель | Выбранный календарь не имеет пользовательских рабочих недель (использует по умолчанию) | Используйте календарь по умолчанию (`project.getDefaultCalendar()`) или создайте рабочую неделю программно. |
| Формат даты выглядит странно | `System.out.println` использует формат по умолчанию `java.util.Date` | Примените `SimpleDateFormat` для форматирования дат по необходимости. |

## Часто задаваемые вопросы
**Q:** Могу ли я изменить информацию о рабочих неделях с помощью Aspose.Tasks для Java?  
**A:** Да. API предоставляет методы `addWorkWeek()`, `removeWorkWeek()` и сеттеры свойств для изменения названий, дат и рабочих часов.

**Q:** Совместима ли Aspose.Tasks с разными версиями файлов Microsoft Project?  
**A:** Абсолютно. Поддерживаются файлы MPP от Project 98 до последних релизов, а также файлы Project XML.

**Q:** Можно ли интегрировать Aspose.Tasks с другими Java‑фреймворками?  
**A:** Да. Библиотека чисто Java, её можно использовать вместе со Spring, Jakarta EE или любым другим фреймворком.

**Q:** Доступна ли пробная версия Aspose.Tasks?  
**A:** Да, бесплатная 30‑дневная пробная версия доступна на официальном сайте: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q:** Где можно получить поддержку по Aspose.Tasks?  
**A:** Лучшее место — форум сообщества Aspose: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Последнее обновление:** 2026-08-13  
**Тестировано с:** Aspose.Tasks для Java 24.12 (последняя на момент написания)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Добавить календарь в проект с помощью Aspose.Tasks для Java](/tasks/java/calendars/create/)
- [Получить исключения календаря с Aspose.Tasks – учебник по Java](/tasks/java/calendar-exceptions/retrieve/)
- [Как установить календарь и определить рабочие дни в MS Project с Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}