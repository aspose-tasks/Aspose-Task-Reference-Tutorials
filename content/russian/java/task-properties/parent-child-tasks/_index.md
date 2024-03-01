---
title: Управление родительскими и дочерними задачами в Aspose.Tasks
linktitle: Управление родительскими и дочерними задачами в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Повысьте эффективность управления проектами с помощью Aspose.Tasks для Java. Научитесь шаг за шагом управлять родительскими и дочерними задачами. Начать сейчас!
type: docs
weight: 24
url: /ru/java/task-properties/parent-child-tasks/
---
## Введение
В сфере управления проектами решающее значение имеет эффективная организация задач. Aspose.Tasks for Java предоставляет надежное решение для эффективного управления родительскими и дочерними задачами. В этом руководстве мы покажем вам процесс использования Aspose.Tasks для Java для оптимизации задач вашего проекта.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
- Базовое понимание программирования на Java.
-  Установлена библиотека Aspose.Tasks для Java. Вы можете скачать его[здесь](https://releases.aspose.com/tasks/java/).
- В вашей системе установлена интегрированная среда разработки Java (IDE).
## Импортировать пакеты
Для начала импортируйте необходимые пакеты в ваш Java-проект. Эти пакеты облегчают интеграцию с функциями Aspose.Tasks for Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## Шаг 1. Установите дату начала проекта
Начните с установки даты начала проекта и других соответствующих параметров.
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Дополнительный код для импорта пакетов можно добавить здесь.
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Шаг 2. Добавьте родительскую задачу (задача 1).
Создайте родительскую задачу с именем «Задача 1» и настройте ее свойства.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Шаг 3. Добавьте родительскую задачу (задача 2) с дочерними задачами
Теперь добавьте еще одну родительскую задачу с именем «Задача 2» и включите дочерние задачи (Задача 3 и Задача 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Добавьте дочерние задачи в задачу 2.
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Дополнительную конфигурацию для задачи 3 и задачи 4 можно добавить здесь.
```
## Шаг 4. Настройка дочерних задач
Укажите даты начала, продолжительность и ограничения для задачи 3 и задачи 4.
```java
// Настройка задачи 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Настройка задачи 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Шаг 5. Обновите процент выполнения задачи
Настройте процент выполнения для задачи 3 и задачи 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Шаг 6: Сохраните проект
Наконец, сохраните проект с внесенными изменениями.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Это пошаговое руководство демонстрирует, как эффективно управлять родительскими и дочерними задачами с помощью Aspose.Tasks для Java. Поэкспериментируйте с различными конфигурациями в соответствии с требованиями вашего проекта.
## Заключение
В заключение, Aspose.Tasks for Java позволяет разработчикам эффективно решать задачи проекта, обеспечивая бесперебойную организацию и отслеживание. Выполните описанные шаги, чтобы расширить свои возможности управления проектами.
## Часто задаваемые вопросы
### Совместим ли Aspose.Tasks для Java с различными форматами файлов проектов?
Да, Aspose.Tasks for Java поддерживает различные форматы файлов проектов, включая MPP и XML.
### Могу ли я настроить свойства задачи помимо того, что описано в этом руководстве?
Абсолютно! Aspose.Tasks for Java предоставляет широкие возможности настройки свойств задач.
### Существует ли форум сообщества Aspose.Tasks, где я могу обратиться за поддержкой?
 Да, вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для поддержки сообщества.
### Как я могу получить временную лицензию на Aspose.Tasks для Java?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Где я могу найти подробную документацию по Aspose.Tasks для Java?
 Документация доступна[здесь](https://reference.aspose.com/tasks/java/).