---
date: 2025-12-04
description: Изучите, как установить календарь проекта и управлять свойствами календаря
  MS Project в Java с помощью Aspose.Tasks. Пошаговое руководство по отображению рабочих
  часов календаря и настройке расписаний.
language: ru
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как установить календарь проекта с помощью Aspose.Tasks для Java
url: /java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить календарь проекта с помощью Aspose.Tasks для Java

## Introduction
В этом руководстве вы узнаете, **как установить календарь проекта** программно, используя библиотеку Aspose.Tasks для Java. Управление свойствами календаря позволяет **отображать рабочие часы календаря**, определять пользовательские рабочие дни и согласовывать график проекта с реальными ограничениями. Мы пройдем каждый шаг — от настройки среды до перебора календарей и чтения их свойств — чтобы вы могли уверенно управлять календарями MS Project в своих приложениях.

## Quick Answers
- **Что означает «установить календарь проекта»?** Это создание или обновление рабочих времён календаря, базового календаря и типов дней в файле MS Project.  
- **Какая библиотека требуется?** Aspose.Tasks for Java (любая актуальная версия).  
- **Нужна ли лицензия?** Бесплатная trial‑версия подходит для разработки; для продакшена требуется коммерческая лицензия.  
- **Можно ли отобразить рабочие часы календаря?** Да — читая каждый `WeekDay`, вы можете вывести часы для каждого типа дня.  
- **Совместимо ли это с Maven/Gradle?** Абсолютно — добавьте JAR Aspose.Tasks в зависимости.

## What Is a Project Calendar?
Календарь проекта определяет рабочие дни и часы для задач, ресурсов и общей временной шкалы проекта. В MS Project календари могут наследоваться от базового календаря, и каждый тип дня (например, **Standard**, **Non‑working**) может иметь своё рабочее время. Программное управление этими настройками позволяет динамически корректировать расписание без ручного редактирования.

## Why Manage MS Project Calendar Programmatically?
- **Автоматизация:** Корректировать календари во множестве проектов одним скриптом.  
- **Последовательность:** Обеспечить соблюдение политики рабочего времени во всей организации.  
- **Интеграция:** Синхронизировать календари с внешними системами (HR, ERP).  
- **Видимость:** Быстро **отобразить рабочие часы календаря** для отчетов или отладки.

## Prerequisites
Перед началом убедитесь, что у вас есть:

- **Java Development Kit (JDK) 8+** установлен и настроен `JAVA_HOME`.  
- **Aspose.Tasks for Java** библиотека загружена со [страницы загрузки](https://releases.aspose.com/tasks/java/). Добавьте JAR в classpath вашего проекта или в зависимости Maven/Gradle.  

## Import Packages
First, import the core Aspose.Tasks classes that we’ll use throughout the tutorial:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up the Data Directory
Define the folder that contains your project files. Replace the placeholder with the actual path on your machine.

```java
String dataDir = "Your Data Directory";
```

## Step 2: Define Time Units
Working times are expressed in milliseconds. Defining reusable constants makes the code easier to read.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Step 3: Load Project Data
Create a `Project` instance by loading an existing MS Project XML file (`.xml` or `.mpp`). This gives us access to all calendars stored in the file.

```java
Project project = new Project(dataDir + "project.xml");
```

## Step 4: Iterate Through Calendars and Display Working Hours
Now we loop through every calendar, print its unique identifier, name, base calendar, and the working hours for each day type. This demonstrates **how to set project calendar** values and also how to **display calendar working hours**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### What This Code Does
- **Filters unnamed calendars** (some internal calendars may have a `null` name).  
- **Prints UID and name** – useful for identifying the calendar later.  
- **Shows the base calendar** – either “Self” (the calendar is its own base) or the name of the inherited calendar.  
- **Loops through each `WeekDay`** to calculate and output the total working hours (`workingTime` is in milliseconds, so we divide by `OneHour`).  

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` при `cal.getBaseCalendar()` | Календарь является базовым календарём (isBaseCalendar() возвращает `true`). | Используйте тернарную проверку, как показано (`cal.isBaseCalendar() ? "Self" : ...`). |
| Отсутствует вывод рабочих часов | Файл проекта использует другую единицу времени (тиков). | Проверьте формат файла; Aspose.Tasks нормализует до миллисекунд, но убедитесь, что загружаете правильный тип файла. |
| Не удалось найти `project.xml` | Неправильный путь `dataDir`. | Используйте абсолютный путь или `Paths.get(dataDir, "project.xml").toString()`. |

## Frequently Asked Questions

**Q: В: Могу ли я программно изменять свойства календаря с помощью Aspose.Tasks?**  
A: Да, API предоставляет полный доступ чтения/записи к календарям, позволяя добавлять, редактировать или удалять рабочие времена, исключения и связи базовых календарей.

**Q: В: Есть ли ограничения на настройку календаря в Aspose.Tasks?**  
A: Библиотека отражает возможности Microsoft Project, поэтому вы можете настраивать практически все аспекты календаря. Только очень старые версии файлов Project могут иметь небольшие несовместимости.

**Q: В: Можно ли интегрировать управление календарём в существующие Java‑проекты?**  
A: Конечно. Просто добавьте JAR Aspose.Tasks в путь сборки и используйте те же шаблоны кода, показанные здесь.

**Q: В: Поддерживает ли Aspose.Tasks другие функции управления проектами, помимо календарей?**  
A: Да, она охватывает задачи, ресурсы, назначения, структуры, базовые линии и многое другое — это комплексное решение для автоматизации проектов на Java.

**Q: В: Доступна ли техническая поддержка для разработчиков, использующих Aspose.Tasks?**  
A: Да, Aspose предоставляет специализированные форумы, поддержку по электронной почте и обширную документацию для всех лицензированных пользователей.

## Conclusion
By following this guide you now know **how to set project calendar** values, read and **display calendar working hours**, and integrate these capabilities into any Java application using Aspose.Tasks. This empowers you to automate schedule adjustments, enforce consistent working policies, and build richer project‑management solutions.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}