---
date: 2025-12-02
description: Узнайте, как установить календарь, определить рабочие дни в MS Project
  и задать пользовательские рабочие дни с помощью Aspose.Tasks для Java. Сохраните
  проект в формате XML, используя всего несколько строк кода.
language: ru
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как установить календарь и определить рабочие дни в MS Project с помощью Aspose.Tasks
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить календарь и задать рабочие дни в MS Project с Aspose.Tasks

## Введение
В этом руководстве вы узнаете **как программно задать настройки календаря** и определить рабочие дни в файле Microsoft Project с помощью библиотеки Aspose.Tasks для Java. Независимо от того, нужно ли создать стандартную рабочую неделю, добавить рабочие субботу и воскресенье или настроить короткий график пятницы, это руководство проведёт вас через каждый шаг — от создания проекта до сохранения файла в формате XML.

## Быстрые ответы
- **Какая библиотека нужна?** Aspose.Tasks for Java  
- **Можно ли добавить рабочие субботу и воскресенье?** Да — просто добавьте Saturday и Sunday как рабочие дни.  
- **Как сохранить проект?** Используйте `prj.save(..., SaveFileFormat.Xml)`.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для оценки; для продакшна требуется лицензия.  
- **Какая версия Java требуется?** Java 8 или выше.

## Что означает «как установить календарь» в контексте MS Project?
Установка календаря в MS Project подразумевает определение, какие дни являются рабочими, какие часы работы в день и какие исключения (например, праздники). Этот календарь управляет планированием задач, распределением ресурсов и общими сроками проекта.

## Почему стоит использовать Aspose.Tasks для работы с календарём?
- **Полный контроль** — программно создавать, изменять или удалять календари без открытия пользовательского интерфейса.  
- **Кросс‑платформенность** — работает на любой ОС, поддерживающей Java.  
- **Поддержка всех форматов файлов** — MPP, MPT и XML, поэтому вы можете *save project as XML* для лёгкой интеграции с другими системами.  
- **Отсутствие зависимостей от COM** — в отличие от библиотеки Microsoft Project Interop.

## Предварительные требования
Прежде чем начать, убедитесь, что у вас есть:

1. **Java Development Kit (JDK) 8+** — скачайте с [сайта Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** — получите последнюю JAR‑файл со [страницы загрузки Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. IDE или система сборки (Maven/Gradle) для добавления Aspose.Tasks JAR в classpath вашего проекта.

## Импорт пакетов
Сначала импортируйте необходимые классы. Эти импорты дают вам доступ к объектам проекта, календаря и рабочего времени.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Пошаговое руководство

### Шаг 1: Создать экземпляр проекта
Создайте новый объект `Project`. Этот объект представляет файл MS Project, который вы будете редактировать.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Шаг 2: Определить новый календарь
Добавьте новый календарь в проект. Ясное название помогает, когда у вас несколько календарей.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Шаг 3: Добавить стандартные рабочие дни (понедельник‑четверг)
Используйте встроенный помощник `WeekDay.createDefaultWorkingDay` для установки стандартного графика 9 am‑5 pm для основной рабочей недели.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Шаг 4: Добавить рабочие дни выходных
Если ваш проект работает в выходные, просто добавьте Saturday и Sunday как обычные рабочие дни. Это демонстрирует **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Шаг 5: Установить короткий рабочий день (пятница)
Здесь мы **set custom working days** для пятницы: утренний смена (9 am‑12 pm) и дневная смена (1 pm‑4 pm).

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

### Шаг 6: Сохранить проект в формате XML
Наконец, сохраните изменения. Параметр `SaveFileFormat.Xml` позволяет **save project as XML**, что полезно для интеграции с другими инструментами.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|----------|
| **Рабочее время не применяется** | Убедитесь, что вызван `setDayWorking(true)` для пользовательского `WeekDay`. |
| **Файл не найден при сохранении** | Проверьте, что `dataDir` указывает на существующую папку и у вашего приложения есть права записи. |
| **Календарь не отображается в задачах** | Присвойте только что созданный календарь ресурсам или задачам с помощью `task.setCalendar(cal)`. |

## Часто задаваемые вопросы

**В: Можно ли задать пользовательские нерабочие дни с помощью Aspose.Tasks for Java?**  
О: Да. Установите свойство `DayWorking` в `false` для любого `WeekDay`, который нужно сделать нерабочим.

**В: Как добавить праздники или общекорпоративные исключения?**  
О: Создайте объекты `CalendarException`, укажите даты исключений и добавьте их в `cal.getExceptions()`.

**В: Совместима ли библиотека со старыми версиями MS Project?**  
О: Абсолютно. Aspose.Tasks поддерживает форматы MPP, MPT и XML для множества версий Project.

**В: Можно ли изменить существующий календарь в импортированном проекте?**  
О: Загрузите проект с помощью `new Project("existing.mpp")`, получите нужный календарь, внесите изменения и сохраните.

**В: Обрабатывает ли Aspose.Tasks повторяющиеся задачи?**  
О: Да, вы можете создавать и редактировать повторяющиеся задачи с помощью класса `RecurringTask`.

## Заключение
Теперь вы знаете **как установить настройки календаря**, **как задать рабочие дни в MS Project**, добавить рабочие выходные и создать короткий график пятницы — всё это с помощью Aspose.Tasks for Java. Сохраните результат как XML и интегрируйте логику календаря в любое Java‑основанное решение для управления проектами.

---

**Последнее обновление:** 2025-12-02  
**Тестировано с:** Aspose.Tasks for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}