---
date: 2026-02-20
description: Изучите, как добавить задачу в проект и управлять длительностями с помощью
  Aspose.Tasks для Java. Узнайте, как установить длительность и как легко преобразовать
  её.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Добавьте задачу в проект и управляйте длительностями с помощью Aspose.Tasks
url: /ru/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить задачу в проект и управлять длительностью с Aspose.Tasks

## Введение
В этом учебнике вы узнаете **как добавить задачу в проект** и контролировать её длительность с помощью Aspose.Tasks для Java. Независимо от того, создаёте ли вы новый инструмент планирования проектов или расширяете существующее решение, освоение работы с длительностью задач необходимо для точного расписания и отчётности.

## Быстрые ответы
- **Что означает “add task to project”?** Это создаёт новый объект задачи в корне проекта или в конкретной сводной задаче.  
- **Какой класс представляет длительность?** `com.aspose.tasks.Duration`.  
- **Как установить длительность?** Используйте `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Можно ли преобразовать длительность в другую единицу?** Да, вызовите `duration.convert(TimeUnitType.Hour)` или любую другую `TimeUnitType`.  
- **Нужна ли лицензия для продакшна?** Для коммерческого использования требуется действующая лицензия Aspose.Tasks.

## Что такое “add task to project”?
Добавление задачи в проект означает создание объекта `Task` и привязку его к иерархии задач проекта. Эта операция — первый шаг перед тем, как вы сможете задать работу, ресурсы или длительность для задачи.

## Почему важно управлять длительностью задач?
Точные длительности обеспечивают реалистичные сроки, распределение ресурсов и анализ критического пути. С помощью Aspose.Tasks вы можете программно задавать, считывать, преобразовывать и корректировать длительности, получая полный контроль над графиками проекта.

## Предварительные требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- Java Development Kit (JDK): Убедитесь, что Java установлена на вашем компьютере. Скачать её можно [здесь](https://www.oracle.com/java/technologies/javase-downloads.html).
- Библиотека Aspose.Tasks: Скачайте и подключите библиотеку Aspose.Tasks в ваш проект. Библиотеку можно найти [здесь](https://releases.aspose.com/tasks/java/).

## Импорт пакетов
В вашем Java‑проекте импортируйте необходимые пакеты для работы с Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Шаг 1: Настройка проекта
```java
// Create a new project
Project project = new Project();
```

## Шаг 2: Добавление новой задачи (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Как установить длительность
Теперь, когда задача существует, вы можете задать её продолжительность. По умолчанию длительности выражаются в днях.

## Шаг 3: Получение и преобразование длительности задачи
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Как преобразовать длительность
Метод `convert` позволяет перевести `Duration` из одного `TimeUnitType` в другой (например, дни → часы, недели → дни).

## Шаг 4: Обновление длительности задачи до 1 недели
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Шаг 5: Уменьшение длительности задачи
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Следуя этим шагам, вы успешно **добавили задачу в проект** и управили её длительностью с помощью Aspose.Tasks для Java.

## Распространённые ошибки и советы
- **Ошибка:** Забвение преобразовать длительность перед выполнением арифметических операций может привести к неверным результатам. Всегда проверяйте единицу с помощью `duration.getTimeUnit()`.
- **Совет:** Используйте `project.getDuration(value, TimeUnitType)`, чтобы создавать длительности в нужной единице, а не преобразовывать их позже.
- **Ошибка:** Установка отрицательной длительности вызовет исключение. Убедитесь, что входные значения проверены.

## Заключение
В этом руководстве мы рассмотрели, как **добавить задачу в проект**, прочитать её длительность по умолчанию, **установить длительность** и **преобразовать длительность** в разные единицы времени. Теперь вы можете интегрировать эти приёмы в более крупные приложения планирования для точного управления проектами.

## Часто задаваемые вопросы
### Совместима ли Aspose.Tasks со всеми версиями Java?
Aspose.Tasks совместима с Java 6 и более новыми версиями.

### Можно ли использовать Aspose.Tasks в коммерческих проектах?
Да, вы можете использовать Aspose.Tasks как в личных, так и в коммерческих проектах. Подробнее о лицензировании см. [здесь](https://purchase.aspose.com/buy).

### Где найти дополнительную поддержку и ресурсы?
Посетите [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для общения с сообществом и обсуждения вопросов.

### Как получить временную лицензию для тестирования?
Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/) для тестирования и оценки.

### Есть ли бесплатная пробная версия Aspose.Tasks?
Да, бесплатную пробную версию можно скачать [здесь](https://releases.aspose.com/) и ознакомиться с возможностями Aspose.Tasks перед покупкой.

## Часто задаваемые вопросы

**В: Как изменить длительность задачи после её установки?**  
О: Получите текущую длительность с помощью `task.get(Tsk.DURATION)`, измените её (например, `add`, `subtract` или `convert`) и затем установите обратно через `task.set(Tsk.DURATION, newDuration)`.

**В: Можно ли задать длительность в минутах?**  
О: Да, используйте `TimeUnitType.Minute` при вызове `project.getDuration(value, TimeUnitType.Minute)`.

**В: Обновляются ли автоматически даты начала и окончания задачи при изменении длительности?**  
О: Только если режим планирования проекта установлен в автоматический. В противном случае может потребоваться пересчитать график с помощью `project.calculateCriticalPath()`.

**В: Можно ли получить длительность как чистое число?**  
О: Вызовите `duration.getTimeSpan()`, чтобы получить числовое значение в текущей единице измерения.

**В: Что произойдёт, если вычесть больше, чем текущая длительность?**  
О: API выбросит `ArgumentOutOfRangeException`. Всегда проверяйте, чтобы результирующая длительность оставалась положительной.

---

**Последнее обновление:** 2026-02-20  
**Тестировано с:** Aspose.Tasks for Java (latest)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}