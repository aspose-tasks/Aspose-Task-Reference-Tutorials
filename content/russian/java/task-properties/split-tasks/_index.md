---
title: Разделение задач в Aspose.Tasks
linktitle: Разделение задач в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Освойте управление задачами на Java с помощью Aspose.Tasks! Узнайте, как эффективно разделять задачи для оптимизации сроков проекта. Скачать сейчас!
type: docs
weight: 29
url: /ru/java/task-properties/split-tasks/
---
## Введение
Вы испытываете трудности с управлением задачами в своем Java-проекте? Aspose.Tasks for Java предоставляет мощное решение для эффективного разделения задач, расширяя возможности управления проектами. В этом руководстве мы проведем вас через процесс разделения задач с помощью Aspose.Tasks для Java, помогая вам оптимизировать сроки вашего проекта и распределение ресурсов.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
- На вашем компьютере установлен Java Development Kit (JDK).
-  Библиотека Aspose.Tasks для Java загружена и добавлена в ваш проект. Вы можете скачать его с сайта[Документация Aspose.Tasks для Java](https://reference.aspose.com/tasks/java/).
## Импортировать пакеты
Начните с импорта необходимых пакетов в ваш Java-проект:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```
## Шаг 1. Создайте новый проект
Начните с создания нового проекта с использованием библиотеки Aspose.Tasks:
```java
// Создать новый проект
Project splitTaskProject = new Project();
```
## Шаг 2. Установите календарь проекта
Установите настройки календаря проекта, чтобы установить временную шкалу:
```java
// Получите стандартный календарь
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Установите настройки календаря проекта
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (продолжить пример)
```
## Шаг 3. Добавьте корневую задачу
Добавьте корневую задачу в свой проект:
```java
// Корневая задача
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Шаг 4. Добавьте новую задачу в разделение
Добавьте в проект новую задачу, которую хотите разделить:
```java
// Добавить новую задачу
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Шаг 5. Создайте назначение ресурса
Создайте новое назначение ресурса для задачи:
```java
// Создать новое назначение ресурса
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Шаг 6. Сгенерируйте повременные данные
Создайте повременные данные о назначении ресурсов:
```java
// Создание повременных данных о назначении ресурсов
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Шаг 7. Разделите задачу
Разделите задачу на несколько частей:
```java
// Разделите задачу на 3 части
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (продолжить пример)
```
## Заключение
Поздравляем! Вы успешно научились разделять задачи с помощью Aspose.Tasks для Java. Эта мощная библиотека упрощает управление задачами в проектах Java, предоставляя эффективные решения для оптимизации сроков проекта и распределения ресурсов.
## Часто задаваемые вопросы
### Могу ли я разделить задачи разной продолжительности?
Да, вы можете настроить продолжительность задач в соответствии с требованиями вашего проекта.
### Совместим ли Aspose.Tasks для Java со всеми версиями Java?
Aspose.Tasks for Java разработан для бесперебойной работы с различными версиями Java, обеспечивая совместимость.
### Могу ли я использовать Aspose.Tasks для Java бесплатно?
Aspose.Tasks for Java предлагает бесплатную пробную версию, позволяющую вам изучить ее возможности перед покупкой.
### Как я могу получить поддержку Aspose.Tasks для Java?
 Посетить[Форум поддержки Aspose.Tasks для Java](https://forum.aspose.com/c/tasks/15) чтобы получить помощь и связаться с сообществом.
### Нужна ли мне временная лицензия для Aspose.Tasks для Java?
 Вы можете получить временную лицензию[эта ссылка](https://purchase.aspose.com/temporary-license/) для целей тестирования и оценки.