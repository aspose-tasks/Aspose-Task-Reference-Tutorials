---
date: 2026-02-28
description: Узнайте, как использовать Aspose.Tasks для Java для управления временно‑фазированными
  данными задач, скачайте библиотеку, попробуйте бесплатно и упростите отслеживание
  проектов.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как использовать Aspose.Tasks для управления данными задач по временным фазам
  (Java)
url: /ru/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать Aspose.Tasks для данных о задачах с фазированием во времени

## Введение
Если вы ищете **как использовать Aspose**, чтобы держать ваш график проекта под строгим контролем, вы попали в нужное место. Точное отслеживание данных о задачах с фазированием во времени является краеугольным камнем успешного управления проектом, а Aspose.Tasks for Java предоставляет инструменты, необходимые для автоматизации этого процесса. В этом руководстве мы пройдем полный пример от начала до конца, показывающий, как использовать Aspose.Tasks для создания проекта, назначения ресурсов, установки базовых линий и, наконец, получения и отображения фазированных данных.

## Быстрые ответы
- **Что означает «timephased data»?** Это данные, разбитые по временным интервалам (дни, недели, месяцы), показывающие работу, стоимость или оставшуюся работу в течение графика проекта.  
- **Какая библиотека предоставляет эту возможность?** Aspose.Tasks for Java.  
- **Нужна ли лицензия для запуска примера?** Бесплатная пробная версия подходит для разработки; лицензия требуется для продакшн.  
- **Какая версия Java требуется?** Java 8 или выше.  
- **Можно ли экспортировать результаты в Excel?** Да — вы можете перебрать коллекцию `TimephasedData` и записать значения в любой нужный вам формат.

## Что такое данные о задачах с фазированием во времени?
Данные о задачах с фазированием во времени представляют собой количество работы (или стоимости), запланированной для задачи в каждом временном отрезке календаря проекта. Они позволяют увидеть, как распределена работа, обнаружить переутомление и сравнить плановое и фактическое выполнение.

## Почему использовать Aspose.Tasks для управления данными с фазированием во времени?
- **Полный контроль** — программно создавать, изменять и запрашивать фазированные данные без открытия Microsoft Project.  
- **Кросс‑платформенный** — работает на любой ОС, поддерживающей Java.  
- **Без зависимостей COM** — идеально для серверной автоматизации.  
- **Богатый API** — поддерживает базовые линии, контуры работы и пользовательские поля сразу из коробки.

## Предварительные требования
Перед тем как погрузиться в код, убедитесь, что у вас есть:

- **Среда разработки Java** — установлен JDK 8+ и настроена переменная `JAVA_HOME`.  
- **Библиотека Aspose.Tasks for Java** — скачайте и включите библиотеку Aspose.Tasks в ваш проект. Вы можете найти библиотеку [здесь](https://releases.aspose.com/tasks/java/).  
- **Каталог документов** — папка на вашем компьютере, из которой будет читаться и в которую будет записываться примерный файл проекта (`project.xml`).

## Импорт пакетов
В вашем Java‑проекте импортируйте необходимые классы Aspose.Tasks:

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

## Шаг 1: Установить дату начала проекта
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Объяснение:* Мы создаём экземпляр `Project`, инициализируем `Calendar` с желаемой датой начала и назначаем её свойству `START_DATE` проекта.

## Шаг 2: Определить задачу и ресурс
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Объяснение:* Добавляется новая задача с именем **Task** под корневой задачей. Мы также создаём ресурс под названием **Rsc** и задаём его стандартные и сверхурочные ставки.

## Шаг 3: Установить длительность задачи
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Объяснение:* Задача запланирована на длительность **6 дней**.

## Шаг 4: Назначить ресурс задаче
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Объяснение:* Ранее определённый ресурс связывается с задачей через `ResourceAssignment`.

## Шаг 5: Настроить назначение ресурса
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Объяснение:* Мы задаём даты остановки и возобновления назначения (используя значение‑заполнитель) и применяем контур работы **Back‑Loaded**, который смещает большую часть работы к концу назначения.

## Шаг 6: Установить базовую линию
```java
project.setBaseline(BaselineType.Baseline);
```
*Объяснение:* Сохранение базовой линии позволяет позже сравнивать плановые и фактические значения.

## Шаг 7: Обновить завершённость задачи
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Объяснение:* Задача помечена как **50 % выполнена**, что повлияет на расчёт оставшейся работы.

## Шаг 8: Получить фазированные данные
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Объяснение:* Этот вызов извлекает **оставшуюся работу** для назначения, разбитую по временным интервалам проекта.

## Шаг 9: Отобразить фазированные данные
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Объяснение:* Мы просто выводим количество фазированных записей и значение первой записи. В реальном сценарии вы бы перебирали список и экспортировали данные в отчёт или пользовательский интерфейс.

## Распространённые проблемы и решения
- **NullPointerException при вызове `getTimephasedData`** — Убедитесь, что даты `START` и `FINISH` назначения заданы перед вызовом метода.  
- **Неправильный контур работы** — Проверьте, что выбранный `WorkContourType` соответствует вашей стратегии планирования; `BackLoaded` — лишь один из нескольких вариантов.  
- **Базовая линия не отражает изменения** — Не забудьте вызвать `project.setBaseline` *после* определения задач, ресурсов и назначений.

## Часто задаваемые вопросы
### Q: Могу ли я использовать Aspose.Tasks for Java в любом Java‑проекте?
A: Да, Aspose.Tasks for Java совместим с любым проектом на Java.

### Q: Где я могу найти дополнительную поддержку для Aspose.Tasks for Java?
A: Посетите [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для поддержки и обсуждений.

### Q: Доступна ли бесплатная пробная версия Aspose.Tasks for Java?
A: Да, вы можете ознакомиться с бесплатной пробной версией [здесь](https://releases.aspose.com/).

### Q: Как получить временную лицензию для Aspose.Tasks for Java?
A: Вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

### Q: Где можно приобрести Aspose.Tasks for Java?
A: Вы можете приобрести Aspose.Tasks for Java [здесь](https://purchase.aspose.com/buy).

---

**Последнее обновление:** 2026-02-28  
**Тестировано с:** Aspose.Tasks for Java 24.12 (последняя на момент написания)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}