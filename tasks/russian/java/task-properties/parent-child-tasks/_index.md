---
date: 2026-02-23
description: Узнайте, как установить дату начала проекта, задать длительность задачи
  и сохранить проект в формате MPP с помощью Aspose.Tasks для Java. Эффективно управляйте
  родительскими и дочерними задачами.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Установите дату начала проекта и управляйте родительскими и дочерними задачами
  в Aspose.Tasks
url: /ru/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Установить дату начала проекта и управлять родительскими и дочерними задачами в Aspose.Tasks

## Введение
Эффективная организация задач — основа успешного управления проектом, а **правильная установка даты начала проекта** является первым шагом к хорошо структурированному расписанию. В этом руководстве вы узнаете, как **установить дату начала проекта**, настроить длительности задач и управлять отношениями «родитель‑дочерняя» с помощью Aspose.Tasks for Java. К концу вы сможете **сохранить проект как MPP**, обновлять процент выполнения задач и настраивать свойства задач под любые реальные сценарии.

## Быстрые ответы
- **Как установить дату начала проекта?** Используйте `proj.set(Prj.START_DATE, startDate);` после инициализации объекта `Project`.  
- **Можно ли добавить дочерние задачи к родительской задаче?** Да — вызовите `parentTask.getChildren().add("Child Task")`.  
- **В каком формате Aspose.Tasks сохраняет файл?** Используйте `SaveFileFormat.Mpp`, чтобы **сохранить проект как MPP**.  
- **Как обновить процент выполнения задачи?** Установите `Tsk.PERCENT_COMPLETE` у объекта задачи.  
- **Где можно получить временную лицензию?** Перейдите на страницу временной лицензии, ссылка указана в разделе FAQ.

## Предварительные требования
Прежде чем приступить к руководству, убедитесь, что у вас есть следующее:
- Базовое понимание программирования на Java.  
- Библиотека Aspose.Tasks for Java установлена. Скачать её можно [здесь](https://releases.aspose.com/tasks/java/).  
- На вашей системе настроена интегрированная среда разработки Java (IDE).

## Импорт пакетов
Для начала импортируйте необходимые пакеты в ваш Java‑проект. Эти пакеты обеспечивают бесшовную интеграцию с функциональностью Aspose.Tasks for Java.
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

## Шаг 1: Установить дату начала проекта
Начните с установки даты начала проекта и других релевантных параметров.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Шаг 2: Добавить родительскую задачу (Task 1)
Создайте родительскую задачу с именем «Task 1» и настройте её свойства, включая **установку длительности задачи**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Шаг 3: Добавить родительскую задачу (Task 2) с дочерними задачами
Теперь добавьте ещё одну родительскую задачу с именем «Task 2» и включите дочерние задачи (Task 3 и Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Шаг 4: Настроить дочерние задачи
Укажите даты начала, длительности и ограничения для Task 3 и Task 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Шаг 5: Обновить процент выполнения задачи
Отрегулируйте процент выполнения для Task 3 и Task 4 — так вы **обновляете выполнение задачи**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Шаг 6: Сохранить проект
Наконец, **сохраните проект как MPP** с применёнными изменениями.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Это пошаговое руководство демонстрирует, как эффективно управлять родительскими и дочерними задачами с помощью Aspose.Tasks for Java. Экспериментируйте с различными конфигурациями, чтобы они соответствовали требованиям вашего проекта.

## Почему стоит настраивать свойства задач?
Настройка свойств задач, таких как даты начала, длительности, ограничения и процент выполнения, даёт вам детальный контроль над поведением расписания. Независимо от того, нужно ли согласовать задачи с доступностью ресурсов или внедрить бизнес‑правила, Aspose.Tasks позволяет **настраивать свойства задач** программно.

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|---------|
| **Дата начала не применяется** | Убедитесь, что вызываете `proj.set(Prj.START_DATE, …)` **после** создания объекта `Project` и **до** добавления задач. |
| **Дочерние задачи наследуют неверные ограничения** | Явно задайте `ConstraintType` и `ConstraintDate` для каждой дочерней задачи, как показано в Шаге 4. |
| **Сохранённый файл не открывается в MS Project** | Проверьте, что используете последнюю версию Aspose.Tasks и сохраняете с помощью `SaveFileFormat.Mpp`. |
| **Процент не отображается в интерфейсе** | После установки `Tsk.PERCENT_COMPLETE` вызовите `proj.calculateTaskSchedule()`, если требуется пересчёт дат. |

## Часто задаваемые вопросы
### Совместима ли Aspose.Tasks for Java с различными форматами файлов проекта?
Да, Aspose.Tasks for Java поддерживает различные форматы файлов проекта, включая MPP и XML.

### Могу ли я настраивать свойства задач, выходящие за рамки данного руководства?
Конечно! Aspose.Tasks for Java предоставляет обширные возможности настройки свойств задач.

### Есть ли сообщество или форум по Aspose.Tasks, где можно получить поддержку?
Да, вы можете посетить [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для общения с сообществом.

### Как получить временную лицензию для Aspose.Tasks for Java?
Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

### Где найти полную документацию по Aspose.Tasks for Java?
Документация доступна [здесь](https://reference.aspose.com/tasks/java/).

**Дополнительные вопросы и ответы**

**В: Как программно получить временную лицензию?**  
О: Загрузите файл временной лицензии с помощью `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**В: Можно ли изменить единицу измерения длительности задачи по умолчанию?**  
О: Да — измените аргумент `TimeUnitType` в вызове `proj.getDuration(value, TimeUnitType.YourChoice)`.

**В: Какая версия Aspose.Tasks требуется для использования `SaveFileFormat.Mpp`?**  
О: Все последние версии (2022‑2026) поддерживают сохранение в формате MPP; уточняйте в примечаниях к выпуску.

---

**Последнее обновление:** 2026-02-23  
**Тестировано с:** Aspose.Tasks for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}