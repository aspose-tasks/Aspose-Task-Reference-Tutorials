---
title: Управляйте длительностью задач в Aspose.Tasks
linktitle: Управляйте длительностью задач в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Изучите Aspose.Tasks для Java и научитесь легко управлять длительностью задач. Следуйте нашему пошаговому руководству для эффективного планирования и реализации проекта.
weight: 20
url: /ru/java/task-properties/manage-durations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Управляйте длительностью задач в Aspose.Tasks

## Введение
Aspose.Tasks for Java предоставляет надежное решение для эффективного управления задачами и продолжительностью проекта. В этом уроке мы рассмотрим, как управлять продолжительностью задач с помощью Aspose.Tasks, проведя вас через каждый шаг. Независимо от того, являетесь ли вы опытным разработчиком или новичком, это руководство поможет вам понять основы работы с длительностью задач в ваших проектах.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
-  Комплект разработки Java (JDK): убедитесь, что на вашем компьютере установлена Java. Вы можете скачать его[здесь](https://www.oracle.com/java/technologies/javase-downloads.html).
- Библиотека Aspose.Tasks: Загрузите и включите библиотеку Aspose.Tasks в свой проект. Вы можете найти библиотеку[здесь](https://releases.aspose.com/tasks/java/).
## Импортировать пакеты
В свой Java-проект импортируйте необходимые пакеты для работы с Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Шаг 1. Настройте свой проект
```java
// Создать новый проект
Project project = new Project();
```
## Шаг 2. Добавьте новую задачу
```java
// Добавьте новую задачу в проект
Task task = project.getRootTask().getChildren().add("Task");
```
## Шаг 3. Получите и преобразуйте продолжительность задачи
```java
// Получить продолжительность задачи в днях (единица времени по умолчанию)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Преобразование продолжительности в часы в единицу времени
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Шаг 4. Обновите продолжительность задачи до 1 недели.
```java
// Увеличьте продолжительность задачи до 1 недели.
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Шаг 5. Уменьшите продолжительность задачи
```java
// Уменьшить продолжительность задачи
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Выполнив эти шаги, вы успешно управляете продолжительностью задач в своем проекте Aspose.Tasks for Java.
## Заключение
В этом руководстве мы рассмотрели основы управления длительностью задач с помощью Aspose.Tasks для Java. Теперь вы можете с уверенностью включать эти методы в свои проекты для эффективного управления продолжительностью задач.
## Часто задаваемые вопросы
### Совместим ли Aspose.Tasks со всеми версиями Java?
Aspose.Tasks совместим с Java 6 и более поздними версиями.
### Могу ли я использовать Aspose.Tasks для коммерческих проектов?
 Да, вы можете использовать Aspose.Tasks как для личных, так и для коммерческих проектов. Посещать[здесь](https://purchase.aspose.com/buy) для получения подробной информации о лицензировании.
### Где я могу найти дополнительную поддержку и ресурсы?
 Посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) за поддержку сообщества и обсуждения.
### Как я могу получить временную лицензию для целей тестирования?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/) для тестирования и оценки.
### Доступна ли бесплатная пробная версия Aspose.Tasks?
 Да, вы можете получить доступ к бесплатной пробной версии[здесь](https://releases.aspose.com/) чтобы изучить Aspose.Tasks перед совершением покупки.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
