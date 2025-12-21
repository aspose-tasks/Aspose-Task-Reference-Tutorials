---
date: 2025-12-21
description: Узнайте, как настраивать представления диаграммы Ганта, управлять визуализацией
  проекта и сохранять проект в формате PDF с помощью Aspose.Tasks для Java. Легко
  регулируйте количество делений временной шкалы.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Настройка диаграммы Ганта — освоение подсчёта шкалы времени в MS Project в
  Aspose.Tasks
url: /ru/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Настройка диаграммы Ганта – Освоение количества масштабов времени в MS Project с Aspose.Tasks

## Introduction
Если вам нужно **настроить визуализацию диаграммы Ганта** в Microsoft Project, контроль количества масштабов времени — ключевая техника. С помощью Aspose.Tasks for Java вы можете программно задать нижний и средний уровни масштабов времени, точно настроить отображение делений и затем **сохранить проект в PDF** для обмена со стейкхолдерами. Этот учебник проведёт вас через весь процесс — от настройки окружения до создания отшлифованного PDF, отражающего вашу настроенную диаграмму Ганта.

## Quick Answers
- **Что означает “customize Gantt chart”?** Настройка уровней масштабов времени, цветов и макета в соответствии с вашими потребностями в отчётности.  
- **Какой метод API задает количество нижнего уровня?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Могу ли я напрямую создать PDF из проекта?** Да — используйте `project.save(..., SaveFileFormat.Pdf)`.  
- **Нужна ли лицензия для продакшн‑использования?** Требуется коммерческая лицензия; доступна бесплатная пробная версия.  
- **Какая версия Java поддерживается?** Java 8 или выше работает с последней библиотекой Aspose.Tasks.

## What is “customize Gantt chart” in Aspose.Tasks?
Настройка диаграммы Ганта означает программное изменение её визуальных компонентов — таких как интервалы масштабов времени, деления и полосы задач — чтобы диаграмма соответствовала тому, как вы хотите **управлять визуализацией проекта**. Изменяя количество масштабов времени, вы контролируете, сколько дней, недель или месяцев представляет каждый сегмент, делая диаграмму более понятной для разных аудиторий.

## Prerequisites
Прежде чем начать, убедитесь, что у вас есть:

1. **Java Development Environment** — установлен JDK 8 или новее.  
2. **Aspose.Tasks for Java Library** — скачайте её [здесь](https://releases.aspose.com/tasks/java/).  
3. **Basic Java Knowledge** — знакомство с синтаксисом Java и объектно‑ориентированными концепциями.

## Import Packages
Импортируйте необходимые классы в ваш Java‑проект:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step‑by‑Step Guide

### Step 1: Set Data Directory
Определите, откуда будут читаться и куда будут записываться файлы вашего проекта:

```java
String dataDir = "Your Data Directory";
```

Замените `"Your Data Directory"` на абсолютный путь на вашем компьютере.

### Step 2: Create a New Project Instance
Создайте новый объект `Project`, который будет содержать все задачи и настройки представления:

```java
Project project = new Project();
```

### Step 3: Configure the Gantt Chart View
Создайте объект `GanttChartView` — здесь вы будете **генерировать Java‑код для представления Ганта**, чтобы управлять внешним видом диаграммы:

```java
GanttChartView view = new GanttChartView();
```

### Step 4: Set Time Scale Count for the Bottom Tier
Настройте нижний уровень, чтобы отображать два интервала и скрыть деления:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Step 5: Set Time Scale Count for the Middle Tier
Примените ту же конфигурацию к среднему уровню:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Step 6: Add the Customized View to the Project
Присоедините только что настроенное представление к экземпляру `Project`:

```java
project.getViews().add(view);
```

### Step 7: Add Sample Tasks (Test Data)
Создайте пару задач с конкретными длительностями, чтобы проиллюстрировать настроенную диаграмму Ганта:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Step 8: Save the Project as a PDF
Наконец, экспортируйте проект — включая вашу **настроенную диаграмму Ганта** — в PDF‑файл:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Полученный PDF демонстрирует, как нижний и средний уровни масштабов времени были **настроены**, предоставляя стейкхолдерам чёткое, печатное представление расписания.

## Common Issues & Troubleshooting
- **PDF пустой** — Убедитесь, что путь `dataDir` заканчивается разделителем файлов (`/` или `\`) и что каталог существует.  
- **Деления всё ещё отображаются** — Проверьте, что `setShowTicks(false)` вызывается для обоих уровней.  
- **Длительность не применена** — Убедитесь, что при создании длительностей вы используете `TimeUnitType.Hour` (или соответствующую единицу).

## Frequently Asked Questions

**Q: Может ли Aspose.Tasks for Java обрабатывать крупномасштабные файлы проектов?**  
A: Да, библиотека оптимизирована для высокопроизводительной обработки объёмных данных проекта.

**Q: Совместим ли Aspose.Tasks for Java с различными IDE для Java?**  
A: Абсолютно — он без проблем работает с Eclipse, IntelliJ IDEA, NetBeans и другими популярными IDE.

**Q: Могу ли я настроить внешний вид диаграмм Ганта помимо настроек масштабов времени?**  
A: Да, Aspose.Tasks предоставляет широкие возможности стилизации, такие как цвета полос, шрифты и линии сетки.

**Q: Доступна ли пробная версия Aspose.Tasks for Java?**  
A: Да, вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/).

**Q: Где я могу получить поддержку по Aspose.Tasks for Java?**  
A: Поддержку и помощь можно найти на форуме Aspose.Tasks [здесь](https://forum.aspose.com/c/tasks/15).

**Q: Как программно изменить цвет фона диаграммы Ганта?**  
A: Используйте метод `view.getGanttChartProperties().setBackgroundColor(Color)` после импорта `java.awt.Color`.

## Conclusion
Следуя этим шагам, вы научились **настраивать уровни масштабов времени диаграммы Ганта**, улучшать **визуализацию проекта** и **сохранять проект в PDF** с помощью Aspose.Tasks for Java. Этот подход даёт вам полный контроль над визуальным выводом, упрощая обмен чёткими, профессиональными расписаниями с вашей командой или клиентами.

---

**Последнее обновление:** 2025-12-21  
**Тестировано с:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}