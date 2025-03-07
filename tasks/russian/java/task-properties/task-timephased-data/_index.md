---
title: Повременные данные задачи в Aspose.Tasks
linktitle: Повременные данные задачи в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Изучите Aspose.Tasks для Java и освойте повременное управление данными задач. Загрузите библиотеку, получите бесплатную пробную версию и оптимизируйте отслеживание своих проектов.
weight: 34
url: /ru/java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Повременные данные задачи в Aspose.Tasks

## Введение
В сфере управления проектами точное отслеживание повременных данных задачи имеет решающее значение для эффективного выполнения проекта. Aspose.Tasks for Java представляет собой мощный инструмент для оптимизации этого процесса, предлагающий надежные функции и гибкость. Это руководство поможет вам использовать Aspose.Tasks для Java для эффективного управления повременными данными задач.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
- Среда разработки Java: убедитесь, что в вашей системе установлена Java.
-  Aspose.Tasks для библиотеки Java: Загрузите и включите библиотеку Aspose.Tasks в свой проект. Вы можете найти библиотеку[здесь](https://releases.aspose.com/tasks/java/).
- Каталог документов: создайте каталог для документов вашего проекта.
## Импортировать пакеты
В свой Java-проект импортируйте необходимые пакеты для Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## Шаг 1. Установите дату начала проекта
```java
Project project = new Project(dataDir + "project.xml");
// Дополнительный код для импорта пакетов
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Объяснение: Инициализируйте объект календаря, установите дату начала и примените ее к проекту.
## Шаг 2. Определите задачу и ресурс
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Пояснение: Создайте задачу и ресурс, задав ставки для стандартной и сверхурочной работы.
## Шаг 3. Установите продолжительность задачи
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Пояснение: Определите продолжительность задачи (например, 6 дней).
## Шаг 4. Назначьте ресурс задаче
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Объяснение: Назначьте ресурс задаче.
## Шаг 5. Настройте назначение ресурсов
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Объяснение: Задайте для назначения ресурса такие параметры, как остановка, возобновление и рабочий контур.
## Шаг 6: Установите базовый уровень
```java
project.setBaseline(BaselineType.Baseline);
```
Пояснение: Установите базовый уровень проекта.
## Шаг 7. Завершение задачи обновления
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Пояснение: Укажите процент выполнения задачи.
## Шаг 8. Получение повременных данных
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Пояснение: Получите повременные данные для оставшихся трудозатрат назначения.
## Шаг 9: Отображение повременных данных
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Дополнительный код для отображения других значений
```
Пояснение: Выведите и отобразите повременные данные.
## Заключение
Эффективное управление повременными данными задач необходимо для успеха проекта. Aspose.Tasks for Java упрощает этот процесс, предоставляя полный набор функций. Следуя этому руководству, вы сможете легко интегрировать Aspose.Tasks в свой проект Java, обеспечивая точный контроль над сроками проекта и распределением ресурсов.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks для Java в любом Java-проекте?
О: Да, Aspose.Tasks for Java совместим с любым проектом на основе Java.
### Вопрос: Где я могу найти дополнительную поддержку Aspose.Tasks для Java?
 А: Посетите[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) за поддержку и обсуждения.
### Вопрос: Доступна ли бесплатная пробная версия Aspose.Tasks для Java?
 О: Да, вы можете воспользоваться бесплатной пробной версией.[здесь](https://releases.aspose.com/).
### Вопрос: Как я могу получить временную лицензию на Aspose.Tasks для Java?
 О: Вы можете приобрести временную лицензию.[здесь](https://purchase.aspose.com/temporary-license/).
### Вопрос: Где я могу приобрести Aspose.Tasks для Java?
 О: Вы можете приобрести Aspose.Tasks для Java.[здесь](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
