---
title: Обновите данные задачи в формат MPP в Aspose.Tasks
linktitle: Обновите данные задачи в формат MPP в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как обновить данные задачи в формат MPP с помощью Aspose.Tasks для Java. Следуйте нашему пошаговому руководству для эффективного управления проектами.
type: docs
weight: 35
url: /ru/java/task-properties/update-task-data/
---
## Введение
Добро пожаловать в наше пошаговое руководство по обновлению данных задачи в формат MPP с помощью Aspose.Tasks для Java. В этом уроке мы проведем вас через весь процесс, гарантируя, что вы четко поймете каждый шаг. Aspose.Tasks for Java предоставляет надежное решение для работы с файлами Microsoft Project, и к концу этого руководства вы сможете эффективно обновлять данные задач в формате MPP.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:
-  Aspose.Tasks для Java: убедитесь, что у вас установлена библиотека Aspose.Tasks. Вы можете скачать его с сайта[страница выпуска](https://releases.aspose.com/tasks/java/).
- Комплект разработки Java (JDK): убедитесь, что в вашей системе установлена Java.
- Интегрированная среда разработки (IDE): используйте любую IDE для разработки на Java.
## Импортировать пакеты
Начните с импорта необходимых пакетов в ваш Java-проект. Следующий фрагмент демонстрирует, как импортировать пакеты:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. Создайте и настройте начальную задачу.
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Продолжить остальную часть кода)
```
## 2. Установите дату начала и продолжительность.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Продолжить остальную часть кода)
```
## 3. Создайте сводную задачу.
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Продолжить остальную часть кода)
```
## 4. Установите крайний срок и примечания к задачам
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Продолжить остальную часть кода)
```
## 5. Настройте ограничения задач
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Продолжить остальную часть кода)
```
## 6. Создайте дополнительные задачи
```java
//Создайте 10 новых задач.
for (int i = 0; i < 10; i++) {
    //... (Продолжить остальную часть кода)
}
//... (Продолжить остальную часть кода)
```
## 7. Сохраните проект
```java
// Сохранить проект
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Выполнив эти шаги, вы успешно обновили данные задачи в формате MPP с помощью Aspose.Tasks для Java.
## Заключение
Поздравляем! Вы завершили подробное руководство по обновлению данных задачи в формате MPP с помощью Aspose.Tasks для Java. Эта мощная библиотека упрощает задачи управления проектами, что делает ее ценным инструментом для разработчиков Java.
## Часто задаваемые вопросы
### Вопрос: Где я могу найти документацию Aspose.Tasks для Java?
 О: Документация доступна.[здесь](https://reference.aspose.com/tasks/java/).
### Вопрос: Как скачать Aspose.Tasks для Java?
 О: Вы можете скачать его с[страница выпуска](https://releases.aspose.com/tasks/java/).
### Вопрос: Доступна ли бесплатная пробная версия?
 О: Да, вы можете получить доступ к бесплатной пробной версии.[здесь](https://releases.aspose.com/).
### Вопрос: Где я могу получить поддержку Aspose.Tasks для Java?
 О: Посетите форум поддержки.[здесь](https://forum.aspose.com/c/tasks/15).
### Вопрос: Предлагаете ли вы временные лицензии для целей тестирования?
 О: Да, вы можете получить временную лицензию.[здесь](https://purchase.aspose.com/temporary-license/).