---
date: 2026-03-29
description: Узнайте, как перенести незавершённую работу, обновить проектную работу
  и сохранить файлы MS Project в формате XML, используя Aspose.Tasks для Java.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Перепланировать незавершённую работу и обновить файлы MS Project с помощью
  Aspose.Tasks
url: /ru/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Перепланировать незавершённую работу и обновить файлы MS Project с помощью Aspose.Tasks

## Введение
Microsoft Project — широко используемый инструмент управления проектами, который помогает командам планировать задачи, распределять ресурсы и отслеживать сроки. Aspose.Tasks for Java предоставляет разработчикам богатый API для программного управления файлами Microsoft Project. В этом руководстве вы узнаете, как **обновлять работу проекта**, **перепланировать незавершённую работу** и **сохранять файл MS Project** в формате XML с помощью Aspose.Tasks for Java.

## Быстрые ответы
- **Что означает «перепланировать незавершённую работу»?** Она перемещает оставшуюся работу по задачам так, чтобы они начинались после выбранной даты, не затрагивая завершённые части.  
- **Какой метод помечает работу как завершённую?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Как сохранить изменения?** Используйте `project.save(<path>, SaveFileFormat.Xml)`.  
- **Нужна ли лицензия для продакшн?** Да, для коммерческого использования требуется действующая лицензия Aspose.Tasks.  
- **Какая версия Java поддерживается?** Полностью поддерживаются Java 8 и более новые версии.

## Что такое «перепланировать незавершённую работу»?
Перепланирование незавершённой работы изменяет даты начала всех задач, которые ещё не завершены, сдвигая их начало на период после указанной контрольной даты. Это полезно, когда график проекта меняется из‑за задержек или изменения объёма работ.

## Почему стоит использовать Aspose.Tasks для обновления работы проекта и перепланирования задач?
- **Тонкий контроль:** Позволяет напрямую задавать процент завершения работы и даты.  
- **Без пользовательского интерфейса:** Автоматизирует массовое обновление множества файлов проектов.  
- **Кроссплатформенный:** Работает на любой системе, где установлен Java.  
- **Сохраняет целостность данных:** Все зависимости, ограничения и ресурсы остаются согласованными.

## Предварительные требования
Перед началом убедитесь, что у вас есть следующее:
1. Установленный Java Development Kit (JDK) на вашей системе.  
2. Библиотека Aspose.Tasks for Java. Вы можете скачать её [здесь](https://releases.aspose.com/tasks/java/).  
3. Базовые знания языка программирования Java.

## Импорт пакетов
Сначала импортируйте необходимые пакеты в ваш Java‑код:
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
Инициализируйте новый объект `Project`, определите задачи, задайте длительности и установите зависимости. Это создаёт базовый проект, который мы позже обновим и перепланируем.
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
Пометьте работу как завершённую до определённой даты. Этот шаг демонстрирует операцию **обновления работы проекта**, которая часто является первой перед перепланированием.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Шаг 3: Перепланировать незавершённую работу
Теперь мы перемещаем любую оставшуюся (незавершённую) работу так, чтобы она начиналась после той же контрольной даты. Это основная функция **перепланирования незавершённой работы**.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Заключение
В этом руководстве мы рассмотрели, как **обновлять работу проекта**, **перепланировать незавершённую работу** и **сохранять файл MS Project** в формате XML с помощью Aspose.Tasks for Java. Эти возможности необходимы, когда графики проектов нужно корректировать в соответствии с реальным прогрессом или изменяющимися бизнес‑приоритетами.

## Часто задаваемые вопросы
### Q: Может ли Aspose.Tasks for Java обрабатывать сложные структуры проектов?
A: Да, Aspose.Tasks for Java предоставляет надёжные API для эффективного управления задачами, зависимостями, ресурсами и другими элементами проекта.

### Q: Доступна ли пробная версия Aspose.Tasks for Java?
A: Да, вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/).

### Q: Как получить поддержку Aspose.Tasks for Java?
A: Вы можете посетить [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для получения помощи или вопросов.

### Q: Можно ли приобрести временную лицензию для Aspose.Tasks for Java?
A: Да, временные лицензии доступны для покупки [здесь](https://purchase.aspose.com/temporary-license/).

### Q: Где можно найти подробную документацию по Aspose.Tasks for Java?
A: Вы можете ознакомиться с документацией [здесь](https://reference.aspose.com/tasks/java/) для получения подробных руководств и справки по API.

## Дополнительные часто задаваемые вопросы

**Q: Как убедиться, что сохранённый файл совместим со старыми версиями Microsoft Project?**  
A: Сохраните проект, используя `SaveFileFormat.Xml`; XML широко поддерживается в разных версиях Project.

**Q: Можно ли перепланировать только часть задач, а не весь проект?**  
A: Да, вы можете перебрать конкретные задачи и вызвать `task.setStart(date)` после расчёта новой даты начала.

**Q: Что происходит с распределением ресурсов при перепланировании незавершённой работы?**  
A: Назначения ресурсов автоматически смещаются в соответствии с новыми датами начала задач, сохраняя логику распределения.

**Q: Можно ли программно отменить операцию перепланирования?**  
A: Вы можете перезагрузить оригинальный файл проекта (или резервную копию), чтобы откатить изменения.

**Q: Поддерживает ли Aspose.Tasks сохранение в другие форматы, например .mpp?**  
A: Конечно. Используйте `SaveFileFormat.MPP` для сохранения в нативном формате Microsoft Project.

---

**Последнее обновление:** 2026-03-29  
**Тестировано с:** Aspose.Tasks for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}