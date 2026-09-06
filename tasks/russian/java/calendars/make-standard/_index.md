---
date: 2026-08-13
description: Узнайте, как создать стандартный календарь MS Project на Java с помощью
  Aspose.Tasks. Это пошаговое руководство покажет, как создать стандартный календарь
  MS Project, установить его по умолчанию и сохранить файл.
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: Создать стандартный календарь в Aspose.Tasks
og_description: Как создать календарь на Java с помощью Aspose.Tasks. Узнайте, как
  быстро построить стандартный календарь MS Project, установить его по умолчанию и
  сохранить файл проекта.
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: Как создать календарь – создать стандартный календарь в Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: Как создать календарь – создать стандартный календарь в Aspose.Tasks
url: /ru/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать календарь – создать стандартный календарь в Aspose.Tasks

## Введение
В этом руководстве вы научитесь **как создать календарь** объектов для файлов Microsoft Project, используя библиотеку Aspose.Tasks для Java. Мы пройдем процесс создания стандартного календаря MS Project, сделаем его календарём по умолчанию (стандартным) и сохраним файл проекта. К концу руководства вы сможете интегрировать создание календаря в любое Java‑основанное решение для управления проектами.

## Быстрые ответы
- **Что означает «стандартный календарь»?** Это определение рабочего времени по умолчанию, применяемое к задачам, которым не назначен пользовательский календарь.  
- **Какая библиотека требуется?** Aspose.Tasks for Java – чистый Java API, работающий без установленного Microsoft Project.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшн‑развертываний.  
- **Какой формат файла создаётся?** XML‑файл Microsoft Project (`.xml`).  
- **Сколько времени занимает реализация?** Около 5‑10 минут для базовой настройки календаря.

## Что такое стандартный календарь в Microsoft Project?
Стандартный календарь определяет рабочие дни и часы проекта по умолчанию, обычно с понедельника по пятницу, с 8 до 17 часов. Когда вы добавляете стандартный календарь, любая задача без назначенного пользовательского календаря наследует эти рабочие часы, обеспечивая согласованное планирование по всему проекту.

## Почему использовать Aspose.Tasks для создания календаря?
Aspose.Tasks for Java поддерживает **более 50 форматов ввода и вывода** и может обрабатывать проекты с до **10 000 задач** без загрузки всего файла в память. Эта чистая Java‑библиотека позволяет автоматизировать создание файлов Project на серверах, в CI‑конвейерах или в любом Java‑приложении, устраняя необходимость в лицензированной установке Microsoft Project.

## Предварительные требования
Прежде чем начать, убедитесь, что выполнены следующие условия:

### Установка Java Development Kit (JDK)
Установите последнюю версию JDK с сайта Oracle или из дистрибутива OpenJDK.

### Библиотека Aspose.Tasks for Java
Скачайте библиотеку со [страницы загрузки](https://releases.aspose.com/tasks/java/). Добавьте JAR в classpath вашего проекта.

## Импорт пакетов
Для этого руководства нам нужен только один импорт:

```java
import com.aspose.tasks.*;
```

## Пошаговое руководство

### Шаг 1: настройка каталога данных
Укажите, где будет сохранён сгенерированный файл проекта.

```java
String dataDir = "Your Data Directory";
```

Замените `"Your Data Directory"` на абсолютный путь на вашем компьютере (например, `C:/Projects/Output/`).

### Шаг 2: создание экземпляра проекта
`Project` — это объект верхнего уровня Aspose.Tasks, представляющий в памяти один файл Microsoft Project. Его создание предоставляет контейнер для календарей, задач, ресурсов и других данных проекта.

```java
Project project = new Project();
```

### Шаг 3: определение и установка календаря как стандартного
`Calendar` — класс, моделирующий расписание рабочего времени. Добавление нового календаря с именем **«My Cal»** и вызов `makeStandardCalendar` делает его календарём по умолчанию для всего проекта.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Совет:** Метод `makeStandardCalendar` автоматически помечает переданный календарь как календарь по умолчанию для проекта, что именно необходимо, когда вы хотите **добавить функциональность стандартного календаря**.

### Шаг 4: сохранение проекта
SaveFileFormat — это перечисление, указывающее формат файла, используемый при сохранении проекта.  
Сохраните проект (включая новый календарь) в XML‑файл.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Вы можете изменить имя файла или формат (`SaveFileFormat.Pp`), если предпочитаете другую версию Project.

### Шаг 5: вывод сообщения о завершении
Отобразите визуальный индикатор, подтверждающий, что процесс завершился без ошибок.

```java
System.out.println("Process completed Successfully");
```

## Распространённые проблемы и решения
| Issue | Cause | Fix |
|-------|-------|-----|
| **Файл не найден** | `dataDir` указывает на несуществующую папку | Создайте папку или используйте абсолютный путь |
| **Исключение лицензии** | Запуск без действующей лицензии Aspose.Tasks в продакшн | Примените файл лицензии через `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Пустой календарь** | Забыли добавить определения рабочего времени | Используйте `cal1.getWeekDays().add(WeekDay.DayType.Monday)` и т.д., если нужны пользовательские часы |

## Часто задаваемые вопросы

**Q: Совместим ли Aspose.Tasks со всеми версиями Microsoft Project?**  
A: Да, Aspose.Tasks поддерживает широкий спектр версий Microsoft Project, от 2000 до последних выпусков.

**Q: Можно ли дальше настраивать параметры календаря?**  
A: Конечно! Вы можете изменять рабочие дни, добавлять исключения и определять конкретные рабочие часы с помощью классов `WeekDay` и `WorkingTime`.

**Q: Подходит ли Aspose.Tasks для корпоративных приложений?**  
A: Безусловно. Библиотека разработана для высокопроизводительных, масштабируемых сред и предоставляет полную поддержку крупных файлов Project.

**Q: Предоставляет ли Aspose.Tasks техническую поддержку разработчикам?**  
A: Да, Aspose предоставляет специализированные форумы, поддержку по тикетам и обширную документацию, чтобы помочь быстро решить любые проблемы.

**Q: Могу ли я попробовать Aspose.Tasks перед покупкой?**  
A: Да, вы можете ознакомиться с бесплатной пробной версией, доступной на [веб‑сайте](https://purchase.aspose.com/buy), что позволяет оценить все функции перед покупкой.

**Последнее обновление:** 2026-08-13  
**Тестировано с:** Aspose.Tasks for Java 24.12  
**Автор:** Aspose

## Связанные руководства

- [Добавить календарь в проект с Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Как установить календарь проекта в Java с Aspose.Tasks](/tasks/java/calendars/properties/)
- [Создание пользовательских исключений календаря с Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}