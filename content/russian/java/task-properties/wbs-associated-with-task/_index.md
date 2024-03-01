---
title: WBS, связанная с задачей в Aspose.Tasks
linktitle: WBS, связанная с задачей в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Освойте WBS с помощью Aspose.Tasks для Java. Научитесь читать и перенумеровывать коды WBS задач. Повысьте эффективность управления проектами!
type: docs
weight: 36
url: /ru/java/task-properties/wbs-associated-with-task/
---
## Введение
Добро пожаловать в мир управления проектами с помощью Aspose.Tasks для Java! В этом руководстве мы углубимся в тонкости структуры иерархии работ (WBS), связанной с задачами с использованием Aspose.Tasks для Java. Независимо от того, являетесь ли вы опытным разработчиком или только начинаете, это руководство поможет вам разобраться в основах эффективного управления кодами WBS.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:
- На вашем компьютере установлен Java Development Kit (JDK).
-  Библиотека Aspose.Tasks для Java загружена и добавлена в ваш проект. Вы можете получить его от[здесь](https://releases.aspose.com/tasks/java/).
## Импортировать пакеты
Убедитесь, что вы импортировали необходимые пакеты для запуска проекта:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## Чтение кодов WBS
Начнем с чтения кодов WBS, связанных с задачами. Следуй этим шагам:
## Шаг 1. Загрузите проект
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Шаг 2. Соберите задачи
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Шаг 3. Разбор и настройка
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Этот фрагмент считывает и настраивает коды WBS, связанные с задачами в вашем проекте.
## Перенумерация кодов WBS задач
Теперь давайте рассмотрим перенумерацию кодов WBS для задач:
## Шаг 1. Загрузите проект
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Шаг 2. Выберите все задачи
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Шаг 3. Вывод исходных кодов WBS
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Шаг 4. Перенумерация кодов WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Шаг 5. Вывод обновленных кодов WBS
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Выполнив эти шаги, вы эффективно перенумеруете коды WBS для задач вашего проекта.
## Заключение
Поздравляем! Вы успешно научились работать с кодами WBS с помощью Aspose.Tasks для Java. Эти знания дадут вам возможность эффективно управлять и настраивать иерархию задач вашего проекта.
## Часто задаваемые вопросы
### Вопрос: Где я могу найти документацию по Aspose.Tasks для Java?
 О: Документация доступна.[здесь](https://reference.aspose.com/tasks/java/).
### Вопрос: Как скачать Aspose.Tasks для Java?
 О: Вы можете скачать его[здесь](https://releases.aspose.com/tasks/java/).
### Вопрос: Доступна ли бесплатная пробная версия Aspose.Tasks для Java?
 О: Да, вы можете получить бесплатную пробную версию.[здесь](https://releases.aspose.com/).
### Вопрос: Где я могу получить поддержку Aspose.Tasks для Java?
 А: Посетите[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для поддержки.
### Вопрос: Могу ли я получить временную лицензию на Aspose.Tasks для Java?
 О: Да, получите временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).