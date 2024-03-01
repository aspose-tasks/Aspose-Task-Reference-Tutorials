---
title: Обновите и перенесите проект MS в Aspose.Tasks
linktitle: Обновите проект и перенесите незавершенную работу в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как программно обновлять и перепланировать файлы MS Project с помощью Aspose.Tasks для Java.
type: docs
weight: 23
url: /ru/java/project-file-operations/update-project-reschedule-work/
---
## Введение
Microsoft Project — это широко используемое программное обеспечение для управления проектами, которое позволяет пользователям эффективно управлять задачами, ресурсами и сроками. Aspose.Tasks for Java предоставляет мощный набор API для программного управления файлами Microsoft Project. В этом уроке мы узнаем, как обновить файлы MS Project и перенести незавершенную работу с помощью Aspose.Tasks для Java.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1. В вашей системе установлен Java Development Kit (JDK).
2.  Aspose.Tasks для библиотеки Java. Вы можете скачать его с[здесь](https://releases.aspose.com/tasks/java/).
3. Базовое понимание языка программирования Java.

## Импортировать пакеты
Сначала импортируйте необходимые пакеты в свой Java-код:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Шаг 1: Настройте проект
Инициализируйте новый объект Project и определите в нем задачи, а также их продолжительность и зависимости.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Определите задачи и их продолжительность.
// ...
// Определить зависимости задач
// ...
// Сохраните исходное состояние проекта
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Шаг 2. Обновление работы проекта
Обновите работу над проектом, чтобы пометить ее как завершенную к определенной дате.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Сохраните обновленный проект
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Шаг 3. Перенесите незавершенную работу
Перенесите любую незавершенную работу, чтобы она началась после указанной даты.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Сохранить перенесенный проект
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Заключение
В этом уроке мы узнали, как обновить файлы MS Project и перенести незавершенную работу с помощью Aspose.Tasks для Java. Это может быть особенно полезно в сценариях, когда сроки проекта требуют корректировки в зависимости от прогресса или изменения приоритетов.

## Часто задаваемые вопросы
### Вопрос: Может ли Aspose.Tasks for Java обрабатывать сложные структуры проектов?
О: Да, Aspose.Tasks for Java предоставляет надежные API для эффективного управления задачами, зависимостями, ресурсами и другими элементами проекта.
### Вопрос: Доступна ли пробная версия Aspose.Tasks для Java?
 О: Да, вы можете получить бесплатную пробную версию на[здесь](https://releases.aspose.com/).
### Вопрос: Как я могу получить поддержку Aspose.Tasks для Java?
 О: Вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для любой помощи или вопросов.
### Вопрос: Могу ли я приобрести временную лицензию на Aspose.Tasks для Java?
 О: Да, временные лицензии доступны для приобретения.[здесь](https://purchase.aspose.com/temporary-license/).
### Вопрос: Где я могу найти подробную документацию по Aspose.Tasks для Java?
 О: Вы можете обратиться к документации[здесь](https://reference.aspose.com/tasks/java/) подробные руководства и ссылки на API.