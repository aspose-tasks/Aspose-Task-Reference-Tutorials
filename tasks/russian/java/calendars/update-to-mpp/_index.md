---
date: 2026-02-05
description: Узнайте, как добавить праздничные дни в календарь, назначить календарь
  проекту и сохранить файл MS Project в формате MPP с помощью Aspose.Tasks для Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Добавить праздники в календарь и сохранить как MPP с Aspose.Tasks
url: /ru/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавление праздников в календарь и сохранение в формате MPP с Aspose.Tasks

## Introduction

В современном управлении проектами часто требуется **add holidays to calendar** файлы, создать **MS Project calendar** и затем поделиться расписанием в нативном формате MPP. Независимо от того, объединяете ли вы графики из нескольких источников или мигрируете устаревшие данные, программное создание календаря устраняет ручные ошибки и ускоряет поставку. Этот учебник проведёт вас через полный процесс создания календаря в MS Project, настройки его с праздниками, **assign calendar to project**, и, наконец, **convert project to MPP** с использованием Aspose.Tasks Java API.

## Quick Answers
- **What does this tutorial cover?** Добавление праздников в календарь, назначение его проекту и сохранение результата в файл MPP с помощью Aspose.Tasks for Java.  
- **Do I need a license?** Бесплатная пробная версия подходит для разработки; для продакшн‑использования требуется коммерческая лицензия.  
- **Which Java version is required?** Java 8 или выше (JDK 8+).  
- **Can I customize the calendar?** Да — можно добавить рабочие часы, исключения и праздники.  
- **How long does implementation take?** Около 10‑15 минут для базового календаря.  

## What is “create calendar MS Project”?

Создание календаря MS Project означает программное определение рабочих дней, часов и исключений, которые управляют планированием задач внутри файла Microsoft Project. С помощью Aspose.Tasks вы можете **java create project calendar**, изменять его и сохранять изменения без необходимости открывать пользовательский интерфейс Microsoft Project.

## Why use Aspose.Tasks for this task?

- **Full .NET/Java compatibility** – работает на любой платформе, поддерживающей Java.  
- **No COM or Office installation needed** – идеально для серверной автоматизации и **automate schedule generation**.  
- **Rich API** – поддерживает все свойства календаря, включая пользовательские рабочие недели и праздники.  
- **Direct MPP output** – вы можете **save project as MPP** без промежуточных конвертаций.

## Prerequisites

1. **Java Development Kit (JDK) 8+** – убедитесь, что `java -version` выводит 1.8 или новее.  
2. **Aspose.Tasks for Java** – скачайте последнюю JAR‑файл с [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse или любой другой редактор по вашему выбору.  
4. **Basic Java knowledge** – знакомство с классами, методами и вводом‑выводом файлов.

## How to Add Holidays to Calendar

Ниже мы пройдём каждый шаг, от настройки окружения до сохранения окончательного файла MPP. Блоки кода оставлены без изменений; пояснения к ним расширены для лучшего понимания.

### Step 1: Import Required Packages

Сначала импортируем классы Aspose.Tasks и утилиты Java.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Step 2: Set Up the Data Directory

Определите, где будут находиться ваш шаблон входных данных и файлы вывода. Замените заполнители реальными путями на вашем компьютере.

```java
String dataDir = "Your Data Directory";
```

### Step 3: Define Input and Output File Names

Мы загрузим существующий файл MPP (или пустой проект) и запишем результат в новый файл.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Step 4: Load the Project and Add a New Calendar

Создайте экземпляр `Project` из исходного файла и добавьте календарь с именем **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Step 5: Customize the Calendar (Optional)

Если нужны специфические рабочие часы, праздники или исключения, вызовите собственный вспомогательный метод. В примере используется `GetTestCalendar` как заглушка.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** Вы можете напрямую работать с `cal1.getWeekDays()` для установки рабочих часов каждого дня недели, либо использовать `cal1.getExceptions()` для **add holidays to calendar**.

### Step 6: Assign the Calendar to the Project

Укажите проекту использовать только что созданный календарь для всех расчётов планирования.

```java
project.set(Prj.CALENDAR, cal1);
```

### Step 7: Save the Project as MPP

Теперь **convert project to MPP**, сохранив его с опцией `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Step 8: Confirm Successful Completion

Простое сообщение в консоли сообщит, что процесс завершён без ошибок.

```java
System.out.println("Process completed Successfully");
```

## Common Use Cases

- **Automated schedule generation** для повторяющихся проектов (например, еженедельные спринты).  
- **Migrating legacy CSV or Excel calendars** в полностью функциональный файл MS Project.  
- **Server‑side reporting**, когда веб‑служба возвращает файл MPP по запросу.  

## Troubleshooting & Common Pitfalls

| Issue | Cause | Fix |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` указывает на несуществующую папку | Убедитесь, что каталог существует, или создайте его программно. |
| Calendar not applied to tasks | Задачи всё ещё ссылаются на календарь по умолчанию | После установки `Prj.CALENDAR` также обновите `Task.CALENDAR` каждой задачи, если они были переопределены ранее. |
| Output file is 0 KB | Отсутствуют права записи | Запустите JVM с соответствующими правами доступа к файловой системе или выберите путь, доступный для записи. |

## Frequently Asked Questions

**Q: Is Aspose.Tasks for Java compatible with different versions of MS Project?**  
A: Yes, Aspose.Tasks for Java supports a wide range of MS Project versions, from Project 2007 up to the latest release, ensuring seamless compatibility.

**Q: Can I customize calendars according to specific project requirements?**  
A: Absolutely. You can define working days, set custom work weeks, add holidays, and even create multiple calendars within a single project file.

**Q: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?**  
A: Yes, you can get help from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

**Q: Is there a free trial available for Aspose.Tasks for Java?**  
A: Yes, a fully functional free trial is available [here](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Tasks for Java?**  
A: Temporary licenses can be requested via the Aspose website [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}