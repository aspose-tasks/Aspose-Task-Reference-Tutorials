---
date: 2026-01-25
description: Узнайте, как использовать Aspose Tasks Java для управления задачами,
  обрабатывая критические и ориентированные на усилия задачи в ваших проектах. Улучшите
  рабочие процессы проекта с этим руководством.
linktitle: Aspose Tasks Java – Manage Critical and Effort‑Driven Tasks
second_title: Aspose.Tasks Java API
title: Aspose Tasks Java — Управление критическими и задачами, зависящими от трудозатрат
url: /ru/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java: Управление критическими и зависящими от усилий задачами

В современном управлении проектами **aspose tasks java** предоставляет возможность идентифицировать и контролировать критические и зависящие от усилий задачи непосредственно из вашего Java‑кода. Независимо от того, создаёте ли вы планировщик, инструмент отчётности или пользовательскую панель, правильнаяим из рассмотрим всё, что необходимо знать для работы с критическими и зависящими от усилий задачами с использованием Aspose Tasks Java.

## Быстрые ответы
- **Что означает “critical”?** Задача, задержка которой продлит дату завершения проекта.  
- **Что такое “effort‑driven”?** Задача, которая автоматически корректирует свою длительность при изменении объёма работы.  
- **Какая библиотека предоставляет эти возможности?** Aspose Tasks Java.  
- **Нужна ли лицензия для разработки?** Для оценки достаточно бесплатной пробной версии; для продакшн‑использования требуется лицензия.  
- **Можно ли запускать это на любой ОС?** Да — библиотека независима от платформы (Windows, Linux, macOS).

## Что такое критические и зависящие от усилий задачи?
Критические задачи — это задачи, находящиеся на критическом пути проекта; любая задержка напрямую влияет на общий график. Зависящие от усилий задачи, наоборот, пересчитывают свою длительность на основе объёма назначенной работы, что делает их идеальными для ресурсов, способных работать сверхурочно или распределять усилия между несколькими назначениями.

## Почему стоит использовать Aspose Tasks Java для этого?
- **Полный API в стиле .NET в Java** – Нет необходимости менять язык.  
- **Высокая производительность** – Работает с большими XML‑файлами проектов без загрузки всего файла в память.  
- **Богатый набор свойств** – Доступ к `IS_CRITICAL`, `IS_EFFORT_DRIVEN` и многим другим атрибутам задач.  
- **Кросс‑платформенный** – Работает в любой среде, совместимой с JVM.

## Предварительные требования
Прежде чем приступить к руководству, убедитесь, что у вас выполнены следующие требования:
- Aspose.Tasks for Java Library: Скачайте и установите библиотеку из [документации Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/).
- Java Development Kit (JDK): Убедитесь, что Java установлена в вашей системе.
- Integrated Development Environment (IDE): Используйте предпочитаемую IDE для Подготовьте файл проекта в формате XML, который будет использоваться для демонстрации.

## Импорт пакетов
В вашем Java‑проекте импортируйте необходимые пакеты, чтобы воспользоваться функциональностью Aspose.Tasks for Java:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

### Шаг 1: Сбор задач с помощью `ChildTasksCollector`
Создайте экземпляр `ChildTasksCollector` для сбора всех задач из корневой задачи с помощью `TaskUtils.apply`. Это гарантирует доступ ко всем задачам проекта.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Шаг 2: Итерация по собранным задачам
Пройдитесь по всем собранным задачам с помощью цикла `for`. Для каждой задачи определите, является ли она зависящей от усилий и критической, затем выведите соответствующий статус.

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

Следуя этим шагам, вы сможете эффективно управлять критическими и зависящими от усилий задачами в своих проектах с помощью **aspose tasks java**.

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| `NullPointerException` on `tsk.get(Tsk.IS_CRITICAL)` | У задачи не установлен этот параметр (например, у задачи‑сводки). | Проверьте `tsk.get(Tsk.TASK_TYPE)` перед доступом к флагу, либо отфильтруйте задачи‑сводки. |
| Project file not found, "project.xml"). существует. |
 Windows и Linux?
О: Да, Aspose.Tasks for Java независим от Windows, так и пробную версию Aspose.Tasks for Java можно получить [здесь](https://releases.aspose.com/).

### В: Где можно найти поддержку Aspose.Tasks for Java?
О: Посетите [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для получения поддержки от сообщества и обсуждений.

### В: Как получить временную лицензию для Aspose.Tasks for Java?
О: Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

### В: Где можно приобрести Aspose.Tasks for Java?
О: Приобрести Aspose.Tasks for Java можно на [странице покупки](https://purchase.aspose.com/buy).

---

**Последнее обновление:** 2026-01-25  
**Тестировано с:** Aspose.Tasks Java 24.11 (latest at time of writing)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}