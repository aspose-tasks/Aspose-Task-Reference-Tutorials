---
date: 2026-01-18
description: Узнайте, как создать список задач в Java и добавить задачу в Microsoft
  Project, установить базовый план без MS Project с помощью Aspose.Tasks.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Создание списка задач Java – базовый план MS Project с использованием Aspose.Tasks
url: /ru/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание списка задач Java – базовая линия проекта MS Project с Aspose.Tasks

## Введение
В этом руководстве вы **создадете список задач Java**, сгенерировав базовую линию задачи Microsoft Project с помощью Aspose.Tasks for Java. Aspose.Tasks позволяет работать с файлами Project без установки Microsoft Project, поэтому вы можете **добавлять задачи в Microsoft Project**, управлять ресурсами и даже **устанавливать базовую линию без MS Project** — всё из чистого кода Java.

## Краткие ответы
- **Что делает Aspose.Tasks?** Он предоставляет Java API для создания, чтения и редактирования файлов Microsoft Project без MS Project.  
- **Нужен ли установленный Microsoft Project?** Нет, Aspose.Tasks работает независимо.  
- **Какая версия Java требуется?** JDK 8 или выше.  
- **Можно ли установить базовую линию для отдельной задачи?** Да, используйте `setBaseline` со списком задач.  
- **Нужна ли лицензия для продакшн?** Да, коммерческая лицензия снимает ограничения оценки.

## Что такое базовая линия задачи?
Базовая линия задачи фиксирует исходные запланированные значения начала, окончания и объёма работы задачи. Она служит точкой отсчёта для сравнения фактического прогресса с оригинальным планом.

## Почему использовать Aspose.Tasks для создания списка задач Java?
- **Отсутствие зависимости от MS Project** — идеально для серверной автоматизации.  
- **Полный контроль** над задачами, ресурсами и календарями через Java‑код.  
- **Кросс‑версионная совместимость** с файлами Project 2007‑2024.

## Требования
1. **Java Development Kit (JDK)** — установите JDK 8 или новее.  
2. **Aspose.Tasks for Java** — скачайте библиотеку по [download link](https://releases.aspose.com/tasks/java/).  

## Импорт пакетов
Чтобы начать работу с Aspose.Tasks в вашем Java‑проекте, импортируйте необходимые пакеты:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Шаг 1: Создание объекта Project
```java
Project project = new Project();
```
Здесь мы создаём новый объект `Project` — он представляет файл MS Project, который будет содержать наш список задач.

## Шаг 2: Добавление задачи в проект
```java
Task task = project.getRootTask().getChildren().add("Task");
```
С помощью `getRootTask()` мы получаем корень иерархии проекта и **добавляем задачу в Microsoft Project**. Строка `"Task"` — это имя задачи; вы можете заменить её любой нужной вам описанием.

## Шаг 3: Установка базовой линии для выбранных задач
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Чтобы **установить базовую линию без MS Project**, создайте список задач, для которых требуется базовая линия (здесь `myList`) и передайте его в `setBaseline`. Заполните `myList` задачами, которые вы добавили, если нужен выборочный базовый план.

## Шаг 4: Установка базовой линии для всего проекта
```java
project.setBaseline(BaselineType.Baseline);
```
Если вы хотите установить базовую линию для всего проекта одним вызовом, просто вызовите `setBaseline` с нужным `BaselineType`.

## Как добавить задачу в Microsoft Project с помощью Aspose.Tasks
Помимо показанной выше одиночной задачи, вы можете добавлять несколько задач, подзадачи и назначать ресурсы. Каждый вызов `add()` возвращает объект `Task`, который можно дополнительно настроить (длительность, дату начала и т.д.).

## Как установить базовую линию без MS Project
Aspose.Tasks позволяет создавать базовую линию полностью через код. Вы можете задавать разные типы базовых линий (Baseline, Baseline1‑Baseline10), изменяя перечисление `BaselineType`, что даёт возможность отслеживать несколько ревизий базовых линий без открытия MS Project.

## Распространённые проблемы и решения
- **Базовая линия не отображается:** Убедитесь, что вы вызываете `project.save("output.mpp")` после установки базовой линии (шаг сохранения опущен здесь для краткости).  
- **Список задач пуст:** Проверьте, что вы добавляете задачи к правильному родителю (`getRootTask()` или подзадаче).  
- **Ошибки несоответствия версий:** Используйте последнюю версию Aspose.Tasks JAR, чтобы гарантировать совместимость с новыми форматами .mpp.

## Часто задаваемые вопросы

**Q: Могу ли я использовать Aspose.Tasks for Java без установленного Microsoft Project?**  
A: Да, Aspose.Tasks работает независимо и не требует Microsoft Project на хост‑машине.

**Q: Совместим ли Aspose.Tasks for Java с разными версиями Microsoft Project?**  
A: Абсолютно. Библиотека поддерживает файлы Project с 2007 года до последних выпусков 2024 года.

**Q: Могу ли я управлять ресурсами проекта с помощью Aspose.Tasks for Java?**  
A: Да, вы можете программно добавлять, обновлять и удалять ресурсы, так же как и задачи.

**Q: Поддерживает ли Aspose.Tasks for Java установку зависимостей задач?**  
A: Да, вы можете определять отношения предшественник‑последователь с помощью класса `TaskLink`.

**Q: Доступна ли техническая поддержка для Aspose.Tasks for Java?**  
A: Да, вы можете получить помощь через [форум поддержки](https://forum.aspose.com/c/tasks/15), где сотрудники Aspose и сообщество отвечают на вопросы.

## Заключение
Следуя этим шагам, вы узнали, как **создать список задач Java**, **добавить задачу в Microsoft Project** и **установить базовую линию без MS Project** с помощью Aspose.Tasks. Этот подход упрощает автоматизацию проектов, устраняет необходимость в настольных установках Project и предоставляет полный программный контроль над данными вашего проекта.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---