---
title: Получите рабочие часы из календаря с помощью Aspose.Tasks
linktitle: Получите рабочие часы из календаря с помощью Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Легко извлекайте рабочее время из календарей MS Project с помощью Aspose.Tasks для Java. Упростите задачи управления проектами.
weight: 13
url: /ru/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Получите рабочие часы из календаря с помощью Aspose.Tasks

## Введение
Управление календарями проектов и определение рабочего времени имеет важное значение для эффективного управления проектами. Aspose.Tasks for Java обеспечивает надежную функциональность для легкого получения рабочего времени из календарей MS Project. В этом уроке мы шаг за шагом проведем вас через этот процесс.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
1. В вашей системе установлен Java Development Kit (JDK).
2.  Библиотека Aspose.Tasks для Java загружена и добавлена в ваш проект. Вы можете скачать его с[здесь](https://releases.aspose.com/tasks/java/).
3. Базовое понимание языка программирования Java.
## Импортировать пакеты
Сначала импортируйте необходимые пакеты для работы с Aspose.Tasks for Java:
```java
import com.aspose.tasks.*;
```
## Шаг 1. Загрузите файл проекта
Начните с загрузки файла MS Project:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Шаг 2. Получение информации о задаче и календаре
Извлеките сведения о задаче и календаре из проекта:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Шаг 3. Определите даты начала и окончания
Установите даты начала и окончания задачи:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Шаг 4. Перебор дат
Перебирать даты в пределах продолжительности задачи:
```java
java.util.Calendar tempDate = calStartDate;
```
## Шаг 5: Рассчитайте продолжительность
Рассчитайте продолжительность в минутах, часах и днях:
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
## Заключение
В этом уроке мы рассмотрели, как получить рабочее время из календаря MS Project с помощью Aspose.Tasks для Java. Следуя этим шагам, вы сможете эффективно управлять расписаниями проектов и легко рассчитывать продолжительность задач.
## Часто задаваемые вопросы
### Вопрос: Может ли Aspose.Tasks for Java обрабатывать сложные структуры проектов?
О: Да, Aspose.Tasks for Java обеспечивает комплексную поддержку работы со сложными структурами проектов, включая задачи, ресурсы и календари.
### Вопрос: Совместим ли Aspose.Tasks for Java с различными версиями MS Project?
О: Конечно, Aspose.Tasks for Java поддерживает различные версии MS Project, обеспечивая совместимость в различных средах.
### Вопрос: Могу ли я настроить рабочее время и праздники в календарях проектов?
О: Да, вы можете легко настроить рабочее время и праздники в соответствии с требованиями вашего проекта, используя API Aspose.Tasks для Java.
### Вопрос: Предлагает ли Aspose.Tasks для Java поддержку и документацию?
О: Да, Aspose.Tasks for Java предоставляет обширную документацию и специальные форумы поддержки, которые помогают разработчикам эффективно использовать его функции.
### Вопрос: Доступна ли пробная версия Aspose.Tasks для Java?
 О: Да, вы можете получить доступ к бесплатной пробной версии Aspose.Tasks для Java на сайте[здесь](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
