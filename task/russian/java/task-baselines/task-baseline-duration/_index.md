---
title: Управление базовой длительностью задач в Aspose.Tasks
linktitle: Управление базовой длительностью задач в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как эффективно управлять базовыми показателями задач в MS Project с помощью Aspose.Tasks для Java. Это руководство шаг за шагом проведет вас через этот процесс.
type: docs
weight: 12
url: /ru/java/task-baselines/task-baseline-duration/
---
## Введение
Управление базовыми планами задач в MS Project имеет решающее значение для планирования и отслеживания проекта. В этом руководстве мы рассмотрим, как эффективно управлять продолжительностью базовых показателей задач с помощью Aspose.Tasks для Java.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1. Среда разработки Java: убедитесь, что в вашей системе установлен Java Development Kit (JDK).
2.  Библиотека Aspose.Tasks: Загрузите и установите библиотеку Aspose.Tasks для Java с сайта[здесь](https://releases.aspose.com/tasks/java/).

## Импортировать пакеты
Сначала импортируйте необходимые пакеты для вашего Java-проекта:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## Шаг 1. Создайте экземпляр проекта
Инициализируйте новый экземпляр проекта, используя следующий код:
```java
Project project = new Project();
```
## Шаг 2. Создайте базовый план задачи
Создайте новую задачу и установите ее базовый план, используя следующий код:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## Шаг 3. Отображение базовой информации о задаче
Получите и отобразите базовую информацию о задаче, такую как продолжительность, дата начала, дата окончания и т. д.:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## Шаг 4. Проверьте промежуточную базовую и фиксированную стоимость
Проверьте, является ли базовый план промежуточным, и получите все связанные с ним фиксированные затраты:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## Шаг 5. Печать повременных данных
Распечатайте повременные данные, связанные с базовым планом задачи:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
Следуя этим шагам, вы сможете эффективно управлять базовой длительностью задач в MS Project с помощью Aspose.Tasks для Java.

## Заключение
Управление базовыми планами задач имеет важное значение для управления проектами, позволяя отслеживать отклонения от запланированного графика. С Aspose.Tasks для Java этот процесс становится оптимизированным и эффективным, что позволяет лучше контролировать и реализовывать проект.
## Часто задаваемые вопросы
### Что такое базовый план задачи в MS Project?
Базовый план задачи в MS Project — это снимок первоначально запланированного расписания задачи, включая дату ее начала, дату окончания и продолжительность.
### Почему важно управлять базовыми показателями задач?
Управление базовыми планами задач помогает сравнивать запланированный график с фактическим ходом проекта, что способствует лучшему отслеживанию и принятию решений.
### Могу ли я изменить базовый план задачи после его установки?
Да, вы можете изменить базовые планы задач в MS Project, чтобы отразить изменения в плане проекта. Однако важно документировать любые отклонения от исходного базового уровня.
### Поддерживает ли Aspose.Tasks другие функции управления проектами?
Да, Aspose.Tasks предлагает широкий спектр функций для управления проектами, включая планирование задач, распределение ресурсов и создание диаграммы Ганта.
### Где я могу найти поддержку Aspose.Tasks?
 Вы можете найти поддержку Aspose.Tasks на сайте[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15), где вы можете задавать вопросы и общаться с другими пользователями.