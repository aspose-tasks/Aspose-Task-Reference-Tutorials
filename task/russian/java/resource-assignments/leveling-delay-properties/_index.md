---
title: Обработка свойств задержки выравнивания в Aspose.Tasks
linktitle: Обработка свойств задержки выравнивания для назначений ресурсов в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как обрабатывать свойства задержки выравнивания для назначения ресурсов в Aspose.Tasks для Java, с помощью этого подробного руководства.
type: docs
weight: 17
url: /ru/java/resource-assignments/leveling-delay-properties/
---
## Введение
В этом руководстве мы рассмотрим процесс обработки свойств задержки выравнивания для назначений ресурсов в Aspose.Tasks для Java. Aspose.Tasks — это мощная библиотека Java, которая позволяет вам работать с файлами Microsoft Project, не требуя установки Microsoft Project в вашей системе.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1.  Комплект разработки Java (JDK): убедитесь, что в вашей системе установлен Java JDK. Вы можете скачать и установить его с сайта[Веб-сайт](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Библиотека Aspose.Tasks для Java: загрузите библиотеку Aspose.Tasks для Java с сайта[страница загрузки](https://releases.aspose.com/tasks/java/).

## Импортировать пакеты
Сначала импортируйте необходимые пакеты в свой Java-проект, чтобы использовать функции Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Шаг 1. Создайте объект проекта
 Создать экземпляр`Project` объект:
```java
Project prj = new Project();
```
## Шаг 2. Создайте задачу
Добавьте задачу в проект:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Шаг 3. Установите дату начала и продолжительность задачи
Установите дату начала и продолжительность задачи:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Шаг 4. Добавьте ресурс
Добавьте ресурс в проект:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Шаг 5. Создайте назначение ресурса
Создайте назначение ресурса для задачи и ресурса:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Шаг 6: Установите задержку выравнивания
Установите задержку выравнивания для задания:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Шаг 7: Отображение результатов
Распечатайте задержку выравнивания и другую соответствующую информацию:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Заключение
В этом руководстве мы узнали, как обрабатывать свойства задержки выравнивания для назначений ресурсов в Aspose.Tasks для Java. Выполнив эти шаги, вы сможете эффективно управлять назначениями ресурсов в своих проектах Java.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks с другими библиотеками Java?

О: Да, Aspose.Tasks можно интегрировать с другими библиотеками Java для расширения возможностей управления проектами.

### Вопрос: Совместим ли Aspose.Tasks с различными версиями файлов Microsoft Project?

О: Да, Aspose.Tasks поддерживает различные версии файлов Microsoft Project, обеспечивая совместимость в различных средах.

### Вопрос: Где я могу найти дополнительную поддержку Aspose.Tasks?

 О: Вы можете найти поддержку и ресурсы на[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Вопрос: Могу ли я попробовать Aspose.Tasks перед покупкой?

 О: Да, вы можете получить бесплатную пробную версию Aspose.Tasks на сайте[страница релизов](https://releases.aspose.com/).

### Вопрос: Как я могу получить временную лицензию на Aspose.Tasks?

 О: Вы можете запросить временную лицензию у[страница временной лицензии](https://purchase.aspose.com/temporary-license/) в целях оценки.