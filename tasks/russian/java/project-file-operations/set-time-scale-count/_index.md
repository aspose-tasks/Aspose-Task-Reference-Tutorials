---
date: 2026-03-29
description: Узнайте, как создавать PDF‑файлы проекта, настраивая количество масштабов
  времени в диаграмме Ганта с помощью Aspose.Tasks for Java. Это руководство пошагово
  покажет, как экспортировать диаграмму Ганта в PDF с полным контролем.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Создать PDF проекта — Настроить масштаб времени диаграммы Ганта
url: /ru/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать PDF проекта – Настроить масштаб времени диаграммы Ганта

## Введение
Если вам нужно **create project PDF** файлы, отражающие идеально настроенную диаграмму Ганта, контроль количества масштабов времени является ключевым. С помощью Aspose.Tasks for Java вы можете программно установить нижний и средний уровни масштаба времени, скрыть деления и затем **save project as PDF** для удобного распространения. В этом руководстве мы пройдем все необходимое — от настройки среды разработки до создания полированного PDF, демонстрирующего ваш настроенный вид диаграммы Ганта.

## Краткие ответы
- **Что означает «customize Gantt chart»?** Настройка уровней масштаба времени, цветов и макета в соответствии с вашими требованиями к отчетности.  
- **Какой метод API устанавливает количество нижнего уровня?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Могу ли я сгенерировать PDF напрямую из проекта?** Да — используйте `project.save(..., SaveFileFormat.Pdf)`.  
- **Нужна ли лицензия для использования в продакшене?** Требуется коммерческая лицензия; доступна бесплатная пробная версия.  
- **Какая версия Java поддерживается?** Java 8 или выше работает с последней библиотекой Aspose.Tasks.

## Что такое «customize Gantt chart» в Aspose.Tasks?
Настройка диаграммы Ганта означает программное изменение её визуальных компонентов — таких как интервалы масштаба времени, деления и полосы задач — чтобы диаграмма соответствовала тому, как вы хотите **manage project visualization**. Изменяя количество масштабов времени, вы контролируете, сколько дней, недель или месяцев представляет каждый сегмент, делая диаграмму более понятной для разных аудиторий.

## Зачем создавать PDF проекта с настроенной диаграммой Ганта?
- **Stakeholder‑ready output:** PDF универсально просматривается, обеспечивая одинаковый вид расписания для всех.  
- **Print‑friendly:** Точный контроль над уровнями масштаба времени предотвращает перегруженные или неоднозначные печатные версии.  
- **Automation:** Интегрируйте генерацию PDF в CI‑конвейеры или сервисы отчетности для полной автоматизации без ручных действий.  

## Требования
Прежде чем начать, убедитесь, что у вас есть:

1. **Java Development Environment** – установлен JDK 8 или новее.  
2. **Aspose.Tasks for Java Library** – Скачайте её по ссылке [here](https://releases.aspose.com/tasks/java/).  
3. **Basic Java Knowledge** – Знание синтаксиса Java и объектно‑ориентированных концепций.

## Импорт пакетов
Импортируйте необходимые классы в ваш Java‑проект:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Пошаговое руководство

### Шаг 1: Установить каталог данных
Определите, откуда будут читаться и куда записываться файлы вашего проекта:

```java
String dataDir = "Your Data Directory";
```

Замените `"Your Data Directory"` на абсолютный путь на вашем компьютере.

### Шаг 2: Создать новый экземпляр проекта
Создайте новый объект `Project`, который будет содержать все задачи и настройки представления:

```java
Project project = new Project();
```

### Шаг 3: Настроить представление диаграммы Ганта
Создайте объект `GanttChartView` — здесь вы будете **generate Gantt view Java** код для контроля внешнего вида диаграммы:

```java
GanttChartView view = new GanttChartView();
```

### Шаг 4: Установить количество масштабов времени для нижнего уровня
Настройте нижний уровень, чтобы отображать два интервала и скрыть деления:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Шаг 5: Установить количество масштабов времени для среднего уровня
Примените ту же конфигурацию к среднему уровню:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Шаг 6: Добавить настроенное представление в проект
Присоедините только что настроенное представление к экземпляру `Project`:

```java
project.getViews().add(view);
```

### Шаг 7: Добавить примерные задачи (тестовые данные)
Создайте несколько задач с определёнными длительностями, чтобы проиллюстрировать настроенную диаграмму Ганта:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Шаг 8: Сохранить проект в PDF
Наконец, экспортируйте проект — включая ваш **customized Gantt chart** — в файл PDF:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Полученный PDF демонстрирует, как нижний и средний уровни масштаба времени были **customized**, предоставляя заинтересованным сторонам чёткое, пригодное для печати представление расписания.

## Распространённые проблемы и устранение неполадок
- **PDF is blank** – Убедитесь, что путь `dataDir` заканчивается разделителем файлов (`/` или `\`) и что каталог существует.  
- **Ticks still appear** – Проверьте, что `setShowTicks(false)` вызывается для обоих уровней.  
- **Duration not applied** – Убедитесь, что при создании длительностей вы используете `TimeUnitType.Hour` (или соответствующую единицу).

## Часто задаваемые вопросы

**Q: Может ли Aspose.Tasks for Java обрабатывать крупномасштабные файлы проектов?**  
A: Да, библиотека оптимизирована для высокопроизводительной обработки больших объёмов данных проекта.

**Q: Совместим ли Aspose.Tasks for Java с различными IDE Java?**  
A: Абсолютно — он без проблем работает с Eclipse, IntelliJ IDEA, NetBeans и другими популярными IDE.

**Q: Могу ли я настроить внешний вид диаграмм Ганта за пределами настроек масштаба времени?**  
A: Да, Aspose.Tasks предоставляет обширные параметры стилизации, такие как цвета полос, шрифты и линии сетки.

**Q: Доступна ли пробная версия Aspose.Tasks for Java?**  
A: Да, вы можете получить бесплатную пробную версию по ссылке [here](https://releases.aspose.com/).

**Q: Где я могу получить поддержку по Aspose.Tasks for Java?**  
A: Поддержку и помощь можно найти на форуме Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Q: Как программно изменить цвет фона диаграммы Ганта?**  
A: Используйте метод `view.getGanttChartProperties().setBackgroundColor(Color)` после импорта `java.awt.Color`.

## Заключение
Следуя этим шагам, вы узнали, как **create project PDF** файлы с полностью настроенным масштабом времени диаграммы Ганта, улучшить **project visualization** и **save project as PDF** с помощью Aspose.Tasks for Java. Такой подход дает вам полный контроль над визуальным выводом, облегчая обмен чёткими, профессиональными расписаниями с вашей командой или клиентами.

---

**Последнее обновление:** 2026-03-29  
**Тестировано с:** Aspose.Tasks for Java (latest)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}