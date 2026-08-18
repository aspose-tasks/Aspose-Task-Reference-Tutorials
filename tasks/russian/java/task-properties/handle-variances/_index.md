---
date: 2026-02-20
description: Узнайте, как установить дату начала проекта и управлять отклонениями
  проекта с помощью Aspose.Tasks for Java. Это руководство также показывает, как эффективно
  задать продолжительность задачи.
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Установить дату начала проекта и обработать отклонения задач Aspose.Tasks
url: /ru/java/task-properties/handle-variances/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Установить дату начала проекта и управлять отклонениями задач Aspose.Tasks

## Introduction
В мире управления проектами **установка даты начала проекта** — одно из первых действий, которое вы делаете, чтобы дать вашему расписанию прочную основу. Aspose.Tasks for Java делает этот шаг — а также последующее управление отклонениями задач — простым и надёжным. В этом руководстве вы узнаете, как установить дату начала проекта, задать длительность задачи и эффективно управлять отклонениями проекта.

## Quick Answers
- **Какой основной метод для установки даты начала проекта?** Используйте `project.set(Prj.START_DATE, …)` с экземпляром `java.util.Calendar`.  
- **Какой класс представляет базовую линию для отслеживания отклонений?** `BaselineType.Baseline`.  
- **Можно ли изменить даты начала и завершения задачи после установки базовой линии?** Да, просто обновите `Tsk.START` и `Tsk.STOP`.  
- **Нужна ли лицензия для разработки?** Временная лицензия доступна для оценки.  
- **Какая версия Aspose.Tasks работает с этим кодом?** Последний релиз Aspose.Tasks for Java.

## What is **set project start date**?
Установка даты начала проекта определяет календарный день, с которого рассчитываются все даты задач. Это влияет на расчёты расписания, анализ критического пути и создание базовой линии, делая её необходимой для точного управления отклонениями.

## Why set project start date and manage variances?
- **Предсказуемость:** Устанавливает известную базовую линию для сравнения фактического прогресса.  
- **Гибкость:** Позволяет корректировать даты отдельных задач без потери оригинального плана.  
- **Отчётность:** Обеспечивает чёткие отчёты об отклонениях, подчёркивающие отставание расписания или раннее завершение.  

## Prerequisites
Прежде чем приступить, убедитесь, что у вас есть следующее:

- Среда разработки Java — установленный JDK и готовая IDE или система сборки.  
- Библиотека Aspose.Tasks — скачайте библиотеку **[здесь](https://releases.aspose.com/tasks/java/)**.  

## Import Packages
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Setting Up the Project
Создайте новый экземпляр `Project`, который будет содержать все задачи и информацию о расписании.

```java
Project project = new Project();
```

## Step 2: Adding a Task
Добавьте задачу в корневую задачу. Это будет рабочий элемент, который мы позже скорректируем.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Step 3: Setting Start Date and Duration
Определите дату начала проекта и задайте задаче длительность. Это демонстрирует **установку длительности задачи** на практике.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## Step 4: Setting Baseline
Создайте базовую линию, чтобы позже сравнивать плановые и фактические даты — это необходимо для **управления отклонениями проекта**.

```java
project.setBaseline(BaselineType.Baseline);
```

## Step 5: Adjusting Task Start and Stop Dates
Измените даты начала и завершения задачи, чтобы смоделировать сценарий отклонения.

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*Не стесняйтесь менять даты и длительности, чтобы они соответствовали специфическим требованиям вашего проекта.*

## Common Issues & Tips
- **Базовая линия должна быть установлена до изменения дат.** Если изменить даты сначала, базовая линия зафиксирует уже изменённое расписание вместо оригинального плана.  
- **Месяцы в Calendar начинаются с нуля.** Помните, что `Calendar.FEBRUARY` соответствует месяцу 1, а не 2.  
- **Единицы длительности:** `project.getDuration(2)` создаёт длительность в два дня по умолчанию; измените единицу, если нужны часы или недели.

## Conclusion
Освоив, как **установить дату начала проекта**, **задать длительность задачи** и **управлять отклонениями проекта**, вы получаете полный контроль над расписанием проекта с помощью Aspose.Tasks for Java. Приведённые выше шаги дают прочную основу, которую можно расширять для более сложных сценариев, таких как многофазные проекты, распределение ресурсов и автоматизированные отчёты.

## Frequently Asked Questions
### Is Aspose.Tasks suitable for all project management needs?
Aspose.Tasks is a versatile tool suitable for a wide range of project management requirements, providing flexibility and robust features.

### Can I integrate Aspose.Tasks into my existing Java project?
Yes, you can easily integrate Aspose.Tasks into your Java project by following the provided documentation **[here](https://reference.aspose.com/tasks/java/)**.

### Is a temporary license available for Aspose.Tasks?
Yes, you can obtain a temporary license for Aspose.Tasks **[here](https://purchase.aspose.com/temporary-license/)**.

### Where can I get support for Aspose.Tasks?
For support and discussions, visit the Aspose.Tasks forum **[here](https://forum.aspose.com/c/tasks/15)**.

### Can I download Aspose.Tasks for Java?
Yes, download the latest version of Aspose.Tasks for Java **[here](https://releases.aspose.com/tasks/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks latest Java release  
**Author:** Aspose