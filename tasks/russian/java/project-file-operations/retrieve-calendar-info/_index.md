---
date: 2025-12-20
description: Узнайте, как использовать Aspose.Tasks для извлечения сведений о календаре
  проекта из файлов Microsoft Project с помощью Java. Пошаговое руководство с примерами
  кода.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как использовать Aspose.Tasks для получения информации о календаре MS Project
url: /ru/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать Aspose.Tasks для получения информации о календаре MS Project

## Introduction
В этом руководстве **вы узнаете, как использовать Aspose.Tasks** для программного получения информации о календаре из файлов Microsoft Project. Доступ к данным календаря, таким как рабочие дни, часы и исключения, необходим, когда нужно **извлечь сведения о календаре проекта** для отчетности, интеграции или пользовательской логики планирования. Давайте пройдем процесс шаг за шагом.

## Quick Answers
- **Какая библиотека используется в этом руководстве?** Aspose.Tasks for Java.  
- **Какое основное ключевое слово рассматривается?** *how to use aspose.tasks*.  
- **Что можно извлечь?** Календари проекта, включая рабочие дни и часы.  
- **Нужна ли лицензия?** Доступна бесплатная пробная версия; для продакшн‑использования требуется лицензия.  
- **Какая версия Java поддерживается?** Java 8 или выше.

## Why extract project calendar information?
Календари проекта определяют даты задач, распределение ресурсов и расчеты общей временной шкалы. Извлекая эти данные, вы можете:
- Создавать пользовательские отчёты, отражающие реальные рабочие графики.  
- Синхронизировать сроки Microsoft Project с внешними системами (ERP, BI и т.д.).  
- Выполнять what‑if‑анализ, программно изменяя настройки календаря.

## Prerequisites
Прежде чем начать, убедитесь, что у вас есть:

- Базовые знания программирования на Java.  
- Установленный Java Development Kit (JDK).  
- Библиотека Aspose.Tasks for Java. Скачать её можно [здесь](https://releases.aspose.com/tasks/java/).

## Import Packages
Сначала импортируйте необходимые классы Aspose.Tasks в ваш Java‑проект.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Step 1: Set Data Directory
Определите папку, содержащую ваш файл *.mpp*.

```java
String dataDir = "Your Data Directory";
```

Замените `"Your Data Directory"` на абсолютный путь к папке, где находится **project.mpp**.

## Step 2: Define Time Units
Создайте константы, помогающие преобразовать внутреннее представление времени в человекочитаемые часы.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Эти значения выражаются в микросекундах — так Aspose.Tasks хранит время внутри.

## Step 3: Create Project Instance
Загрузите файл Microsoft Project в объект `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Конструктор `Project` разбирает файл *.mpp* и делает все данные проекта, включая календари, доступными через API.

## Step 4: Retrieve Calendars Information
Получите коллекцию календарей, определённых в проекте.

```java
CalendarCollection alCals = project.getCalendars();
```

Проект может содержать несколько календарей (стандартный, ресурсный и пользовательские). Эта коллекция даёт доступ к каждому из них.

## Step 5: Iterate Through Calendars
Пройдитесь по каждому календарю, отобразив его UID, имя и рабочие дни с соответствующими часами.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

Внутренний цикл проверяет каждый объект `WeekDay`. Если день помечен как рабочий, выводится тип дня (Monday, Tuesday, …) вместе с рассчитанными рабочими часами.

## Step 6: Display Completion Message
Сигнализируйте о завершении процесса извлечения.

```java
System.out.println("Process completed Successfully");
```

## Conclusion
Следуя этим шагам, **вы теперь знаете, как использовать Aspose.Tasks для извлечения информации о календаре проекта** из файла MS Project с помощью Java. Вы можете интегрировать эту логику в более крупные приложения, автоматизировать отчётность или синхронизировать расписания с другими корпоративными системами.

## Frequently Asked Questions

**Q: Можно ли использовать Aspose.Tasks с другими языками программирования?**  
A: Да, Aspose.Tasks поддерживает несколько платформ и языков, включая .NET, C++, Python и Java.

**Q: Доступна ли бесплатная пробная версия Aspose.Tasks?**  
A: Да, бесплатную пробную версию можно скачать [здесь](https://releases.aspose.com/).

**Q: Как получить поддержку по Aspose.Tasks?**  
A: Поддержку можно получить на форуме сообщества Aspose.Tasks [здесь](https://forum.aspose.com/c/tasks/15).

**Q: Можно ли приобрести временную лицензию для Aspose.Tasks?**  
A: Да, временные лицензии доступны для покупки [здесь](https://purchase.aspose.com/temporary-license/).

**Q: Где найти подробную документацию по Aspose.Tasks?**  
A: Документацию можно посмотреть [здесь](https://reference.aspose.com/tasks/java/).

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}