---
date: 2026-03-03
description: Узнайте, как перенумеровать WBS в Aspose.Tasks для Java, управлять разбивкой
  работ и эффективно настраивать коды WBS с пошаговыми примерами.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как перенумеровать WBS в Aspose.Tasks для Java
url: /ru/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как перенумеровать WBS в Aspose.Tasks для Java

## Введение
Если вам нужно **перенумеровать WBS** в файле Microsoft Project с помощью Aspose.Tasks для Java, вы попали по адресу. Этот учебник проведёт вас через чтение существующих кодов WBS, их настройку и последующее перенумерование иерархии, чтобы ваш проект оставался упорядоченным. Независимо от того, чистите ли вы устаревший график или создаёте новый с нуля, освоив эти шаги, вы сможете уверенно **управлять структурами разбивки работ**.

## Быстрые ответы
- **Что делает перенумерование WBS?** Оно пересчитывает иерархическую нумерацию задач, отражая любые структурные изменения.  
- **Какой класс выполняет перенумерование?** `Project.renumberWBSCode`.  
- **Нужна ли лицензия для запуска кода?** Для использования в продакшене требуется действующая лицензия Aspose.Tasks.  
- **Можно ли настроить формат WBS?** Да — используйте `Task.set(Tsk.WBS, "...")`, чтобы задать любую строку.  
- **Какие основные предпосылки?** Java JDK, библиотека Aspose.Tasks для Java и действующий файл проекта (.mpp).

## Что такое структура разбивки работ (WBS)?
Структура разбивки работ (Work Breakdown Structure, WBS) — это иерархическое представление поставок и задач проекта. Каждая задача получает код (например, 1.2.3), отражающий её положение в иерархии. Перенумерование становится необходимым, когда задачи добавляются, удаляются или переупорядочиваются, обеспечивая логичность и читаемость кодов.

## Почему управлять разбивкой работ и настраивать коды WBS?
- **Ясность:** Чёткие коды WBS упрощают поиск задач для заинтересованных сторон.  
- **Отчётность:** Многие инструменты отчётности полагаются на согласованную нумерацию.  
- **Гибкость:** Пользовательские коды позволяют согласовать структуру проекта с внутренними стандартами.  

## Предпосылки
Прежде чем перейти к коду, убедитесь, что у вас есть следующее:

- Установленный Java Development Kit (JDK).  
- Библиотека Aspose.Tasks для Java, добавленная в ваш проект. Скачать её можно [здесь](https://releases.aspose.com/tasks/java/).  

## Импорт пакетов
Убедитесь, что импортировали необходимые пакеты для начала работы над проектом:

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
Сначала мы прочитаем существующие коды WBS, чтобы вы увидели, с чем работаете.

### Шаг 1: Загрузка проекта
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Шаг 2: Сбор задач
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Шаг 3: Разбор и настройка
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

Приведённый выше фрагмент выводит текущий WBS и уровень каждой задачи, а затем демонстрирует **настройку кодов WBS**, присваивая новую строку.

## Перенумеровать коды WBS задач
Теперь действительно перенумеруем иерархию WBS.

### Шаг 1: Загрузка проекта (пример перенумерования)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Шаг 2: Выбор всех задач
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Шаг 3: Вывод начальных кодов WBS
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Шаг 4: Перенумеровать коды WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Шаг 5: Вывод обновлённых кодов WBS
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Следуя этим шагам, вы эффективно **перенумеруете WBS** для любого набора задач в файле проекта.

## Распространённые проблемы и решения
- **WBS не меняется после вызова `set`:** Убедитесь, что работаете с правильным экземпляром задачи и проект сохраняется после изменений.  
- **`renumberWBSCode` бросает исключение:** Проверьте, что список идентификаторов соответствует количеству задач верхнего уровня; иначе метод не сможет правильно сопоставить новые номера.  
- **Отсутствуют значения WBS:** Некоторые задачи могут иметь `null` в поле WBS, если они импортированы из файла без определения этого поля. Используйте значение‑запас перед выводом.

## Часто задаваемые вопросы

**В: Где найти документацию по Aspose.Tasks для Java?**  
О: Документация доступна [здесь](https://reference.aspose.com/tasks/java/).

**В: Как скачать Aspose.Tasks для Java?**  
О: Скачать можно [здесь](https://releases.aspose.com/tasks/java/).

**В: Есть ли бесплатная пробная версия Aspose.Tasks для Java?**  
О: Да, бесплатную пробную версию можно получить [здесь](https://releases.aspose.com/).

**В: Где получить поддержку по Aspose.Tasks для Java?**  
О: Обратитесь к [форуму Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для получения поддержки.

**В: Можно ли получить временную лицензию для Aspose.Tasks для Java?**  
О: Да, временную лицензию можно оформить [здесь](https://purchase.aspose.com/temporary-license/).

**В: Можно ли изменить формат WBS после перенумерования?**  
О: Конечно. После вызова `renumberWBSCode` можно пройтись по задачам и применить `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))`, чтобы соответствовать вашим правилам именования.

**В: Влияет ли перенумерование на зависимости задач?**  
О: Нет. Метод обновляет только строку WBS; ссылки и ограничения задач остаются без изменений.

---

**Последнее обновление:** 2026-03-03  
**Тестировано с:** Aspose.Tasks для Java 24.12 (latest)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}