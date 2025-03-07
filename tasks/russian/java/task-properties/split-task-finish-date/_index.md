---
title: Разделить дату завершения задачи в Aspose.Tasks
linktitle: Разделить дату завершения задачи в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как легко разделить даты завершения задач с помощью Aspose.Tasks для Java. Улучшите управление проектами с помощью точных сроков.
weight: 28
url: /ru/java/task-properties/split-task-finish-date/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Разделить дату завершения задачи в Aspose.Tasks

## Введение
В управлении проектами понимание сроков выполнения задач имеет решающее значение для успешного завершения проекта. Aspose.Tasks for Java предоставляет мощные функции для эффективного управления задачами проекта. В этом уроке мы углубимся в разделение дат завершения задач с помощью Aspose.Tasks, что поможет вам эффективно управлять сроками проекта.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
- Базовые знания Java-программирования.
-  Установлена библиотека Aspose.Tasks для Java. Вы можете скачать его[здесь](https://releases.aspose.com/tasks/java/).
- Настроена среда разработки Java.
## Импортировать пакеты
Начните с включения необходимых пакетов в ваш Java-проект:
```java
import com.aspose.tasks.*;
```
## Шаг 1. Найдите разделенную задачу
Найдите задачу, которую хотите разделить внутри проекта:
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Читать проект
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Шаг 2. Найдите календарь проекта
Получите календарь проекта для точных расчетов дат:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Шаг 3. Рассчитайте дату завершения задачи с разной продолжительностью
Теперь рассчитаем дату окончания задачи для различной длительности:
## Шаг 3.1: Продолжительность 8 часов
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Повторите приведенный выше код для разной продолжительности, соответствующим образом корректируя часы.
## Заключение
Овладение искусством управления датами завершения задач имеет решающее значение для эффективного управления проектами. Aspose.Tasks для Java упрощает этот процесс, позволяя вам без труда оптимизировать сроки реализации проекта.
## Часто задаваемые вопросы
### Вопрос 1: Как загрузить Aspose.Tasks для Java?
 A1: Вы можете скачать его[здесь](https://releases.aspose.com/tasks/java/).
### Вопрос 2: Где я могу найти документацию для Aspose.Tasks?
 A2: обратитесь к документации[здесь](https://reference.aspose.com/tasks/java/).
### В3: Как мне получить временную лицензию на Aspose.Tasks?
 A3: Получите временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### В4: Где я могу получить поддержку для Aspose.Tasks?
 A4: Посетите форум поддержки.[здесь](https://forum.aspose.com/c/tasks/15).
### В5: Могу ли я приобрести Aspose.Tasks?
 A5: Да, вы можете приобрести его[здесь](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
