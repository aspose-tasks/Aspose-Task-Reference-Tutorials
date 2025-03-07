---
title: Освоение свойств задачи в Aspose.Tasks
linktitle: Чтение и запись общих свойств задач в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Исследуйте возможности Aspose.Tasks для Java, позволяющие легко управлять свойствами задач. Читайте и пишите с легкостью, используя наше пошаговое руководство.
weight: 26
url: /ru/java/task-properties/read-write-general-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Освоение свойств задачи в Aspose.Tasks

## Введение
Раскройте весь потенциал управления задачами на Java с помощью Aspose.Tasks. В этом подробном руководстве мы углубимся в чтение и запись общих свойств задач с использованием Aspose.Tasks для Java. Независимо от того, являетесь ли вы опытным разработчиком или новичком, это руководство даст вам навыки легкого управления свойствами задач.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлен Java Development Kit (JDK).
-  Библиотека Aspose.Tasks для Java скачана и настроена. Вы можете найти ссылку для скачивания[здесь](https://releases.aspose.com/tasks/java/).
- Редактор кода, такой как IntelliJ IDEA или Eclipse.
## Импортировать пакеты
Для начала импортируйте необходимые пакеты в свой Java-проект. Этот шаг гарантирует, что у вас есть доступ к функциям Aspose.Tasks. Вот фрагмент, который поможет вам:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Чтение общих свойств задач
## Шаг 1. Создайте задачу
Начните с создания задачи в своем проекте. Это включает в себя настройку имени задачи, даты начала и других соответствующих деталей. Вот пример:
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## Шаг 2. Прочтите свойства задачи
Теперь, когда вы создали задачу, давайте извлечем и отобразим ее общие свойства. Следующий фрагмент кода выполняет это:
```java
// Чтение общих свойств задач
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
## Написание общих свойств задач
## Шаг 3. Загрузите проект и создайте коллектор
 Чтобы записать общие свойства, загрузите существующий проект и настройте`ChildTasksCollector`:
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## Шаг 4. Анализ и отображение свойств
Наконец, проанализируйте собранные задачи и отобразите их свойства:
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
Поздравляем! Вы успешно прочитали и написали общие свойства задач, используя Aspose.Tasks для Java.
## Заключение
В этом руководстве мы рассмотрели основные шаги по беспрепятственному управлению свойствами задач с помощью Aspose.Tasks для Java. Освоив эти методы, вы сможете улучшить свои навыки разработки Java и оптимизировать управление задачами в своих проектах.
## Часто задаваемые вопросы
### Совместим ли Aspose.Tasks с Java 11?
Да, Aspose.Tasks совместим с Java 11 и более поздними версиями.
### Могу ли я использовать Aspose.Tasks для коммерческих проектов?
 Абсолютно! Aspose.Tasks — мощный инструмент как для личных, так и для коммерческих проектов. Посещать[здесь](https://purchase.aspose.com/buy) изучить варианты лицензирования.
### Как я могу получить временную лицензию для целей тестирования?
 Получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/) для тестирования и оценки.
### Где я могу найти поддержку сообщества для Aspose.Tasks?
 Присоединяйтесь к обсуждению сообщества на[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) за помощь и сотрудничество.
### Есть ли образцы проектов для справки?
 Изучите раздел примеров документации.[здесь](https://reference.aspose.com/tasks/java/) для примеров проектов и фрагментов кода.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
