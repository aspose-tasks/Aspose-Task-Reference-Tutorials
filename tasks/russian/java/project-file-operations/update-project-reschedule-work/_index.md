---
date: 2025-12-23
description: Узнайте, как обновлять файлы MS Project и переназначать незавершённую
  работу с помощью Aspose.Tasks для Java. Также посмотрите, как сохранять XML MS Project.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Обновление MS Project и перепланирование работы с Aspose.Tasks
url: /ru/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Обновление MS Project и перенесение работы с Aspose.Tasks

## Введение
Microsoft Project — это широко используемый инструмент управления проектами, который помогает командам планировать, отслеживать и выполнять работу в срок. Когда графики меняются, часто требуется **update MS Project** файлы программно — пометить работу как завершённую, переместить оставшиеся задачи и сохранить точность базовой линии проекта. Aspose.Tasks for Java предоставляет чистый, типобезопасный API для выполнения именно этого без открытия графического интерфейса. В этом руководстве вы увидите, как обновить проект, отметить работу как завершённую до определённой даты, а затем **how to reschedule MS Project** работу, которая ещё остаётся незавершённой.

## Быстрые ответы
- **What does “update MS Project” mean?** Он помечает задачи как выполненные до указанной даты и записывает изменения обратно в файл.  
- **Can I reschedule remaining work automatically?** Да — используйте `rescheduleUncompletedWorkToStartAfter`, чтобы перенести незавершённые задачи вперёд.  
- **Which file format is saved?** Примеры сохраняют проект в формате XML (`SaveFileFormat.Xml`).  
- **Do I need a license to run the code?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.  
- **What Java version is required?** JDK 8 или выше.

## Что такое “update MS Project” в коде?
Обновление проекта означает программное изменение дат задач, длительностей или процентов выполнения и сохранение этих изменений. Aspose.Tasks предоставляет методы, такие как `updateProjectWorkAsComplete`, которые применяют изменения на основе указанной вами эталонной `Date`.

## Почему использовать Aspose.Tasks for Java для обновления MS Project?
- **No UI dependency** – автоматизировать массовые изменения в множестве файлов.  
- **High fidelity** – библиотека сохраняет все нативные данные Project (ресурсы, календари, пользовательские поля).  
- **Cross‑platform** – запускать один и тот же код на Windows, Linux или macOS.  
- **Save MS Project XML** – вы можете экспортировать обновлённый проект в широко поддерживаемый формат XML для последующего использования.

## Требования
1. Установлен Java Development Kit (JDK).  
2. Библиотека Aspose.Tasks for Java — скачайте её по ссылке [here](https://releases.aspose.com/tasks/java/).  
3. Базовые знания синтаксиса Java и объектно‑ориентированных концепций.

## Импорт пакетов
First, import the necessary Aspose.Tasks classes and Java utilities:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Шаг 1: Настройка проекта
Create a new `Project` instance, define a few sample tasks, set their durations, and establish dependencies. Then persist the initial state so you can see the before‑and‑after effect.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Шаг 2: Обновление работы проекта
Mark work as complete up to a specific cutoff date. This is the core of **update MS Project**—the API will adjust task progress and dates automatically.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Шаг 3: Перенос незавершённой работы
After marking completed work, you often need to push the remaining tasks forward. The following call moves any unfinished work to start after the same cutoff date, effectively **how to reschedule MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|----------|
| Задачи не показывают обновлённые даты | Проект был сохранён в другом формате (например, `.mpp`) | Используйте `SaveFileFormat.Xml`, чтобы сохранить структуру XML. |
| `updateProjectWorkAsComplete` кажется не работает | Эталонная дата раньше начала проекта | Убедитесь, что дата `Calendar` находится в пределах временной шкалы проекта. |
| Перенесённые задачи перекрываются | Не применён календарь или выравнивание ресурсов | Примените календарь `Project` или вручную задайте `Task.setStart` после переноса. |

## Часто задаваемые вопросы (расширенные)

**Q: Может ли Aspose.Tasks for Java работать со сложными структурами проекта?**  
A: Да, Aspose.Tasks for Java предоставляет надёжные API для эффективного управления задачами, зависимостями, ресурсами и другими элементами проекта.

**Q: Доступна ли пробная версия Aspose.Tasks for Java?**  
A: Да, вы можете получить бесплатную пробную версию по ссылке [here](https://releases.aspose.com/).

**Q: Как получить поддержку Aspose.Tasks for Java?**  
A: Вы можете посетить форум [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) для любой помощи или вопросов.

**Q: Можно ли приобрести временную лицензию для Aspose.Tasks for Java?**  
A: Да, временные лицензии можно приобрести по ссылке [here](https://purchase.aspose.com/temporary-license/).

**Q: Где найти подробную документацию по Aspose.Tasks for Java?**  
A: Вы можете ознакомиться с документацией по ссылке [here](https://reference.aspose.com/tasks/java/) для всесторонних руководств и справочных материалов API.

## Заключение
В этом руководстве мы прошли полный процесс **updating MS Project** файлов, отметки работы как завершённой, а затем **how to reschedule MS Project** задач, которые остаются незавершёнными. Сохраняя проект в формате XML, вы сохраняете совместимость с другими инструментами и поддерживаете чёткую историю изменений. Используйте эти шаблоны для автоматизации корректировок расписания в больших портфелях, интеграции с CI‑конвейерами или создания пользовательских панелей отчётности.

---

**Последнее обновление:** 2025-12-23  
**Тестировано с:** Aspose.Tasks for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}