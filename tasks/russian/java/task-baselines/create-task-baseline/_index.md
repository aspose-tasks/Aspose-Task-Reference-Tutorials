---
date: 2026-08-29
description: Узнайте, как добавить задачу в проект на Java, создать список задач и
  установить базовый план без Microsoft Project с помощью Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Создание базового плана задачи в Aspose.Tasks
og_description: Узнайте, как добавить задачу в проект на Java и установить базовый
  план с помощью Aspose.Tasks. Это руководство показывает пошаговый код без необходимости
  использования Microsoft Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Как добавить задачу в проект на Java и установить базовый план
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Как добавить задачу в проект на Java и установить базовый план
url: /ru/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить задачу в проект на Java и установить базовый план

## Введение
В этом руководстве вы **add task to project** программно, сгенерируете базовый план задачи Microsoft Project и сохраните файл — всё без открытия Microsoft Project. Aspose.Tasks for Java предоставляет чистый Java API, который работает на любой платформе, что делает его идеальным для автоматизированных конвейеров сборки, сервисов отчетности или любого серверного решения, требующего работы с файлами .mpp.

## Быстрые ответы
- **Что делает Aspose.Tasks?** Он предоставляет Java API для создания, чтения и редактирования файлов Microsoft Project без необходимости наличия Microsoft Project.  
- **Нужен ли установленный Microsoft Project?** Нет, библиотека работает полностью независимо.  
- **Какая версия Java требуется?** JDK 8 или новее.  
- **Можно ли установить базовый план для отдельной задачи?** Да — вызовите `setBaseline` для списка, содержащего только нужные задачи.  
- **Нужна ли лицензия для продакшна?** Да, коммерческая лицензия снимает ограничения оценки и открывает все функции.

## Что такое базовый план задачи?
Базовый план задачи фиксирует изначально запланированные дату начала, дату завершения и объём работы для задачи в момент первого сохранения расписания. Этот снимок служит точкой отсчёта, позволяя менеджерам проекта сравнивать фактический прогресс и затраты с первоначальным планом и вычислять отклонения для анализа эффективности.

## Почему использовать Aspose.Tasks для добавления задачи в проект на Java?
Вы можете создавать, изменять и устанавливать базовые планы задач без какой‑либо настольной установки, что позволяет полностью автоматизировать рабочие процессы. Aspose.Tasks поддерживает **50+ форматов ввода и вывода** и может работать с проектами, содержащими **сотни задач**, при этом потребление памяти остаётся ниже 200 МБ, что делает его идеальным для облачных сервисов и конвейеров CI/CD.

## Требования
1. **Java Development Kit (JDK)** – установите JDK 8 или новее.  
2. **Aspose.Tasks for Java** – загрузите библиотеку по [download link](https://releases.aspose.com/tasks/java/).  

## Импорт пакетов
Чтобы начать работу с Aspose.Tasks в вашем Java‑проекте, импортируйте необходимые пакеты:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Шаг 1: создать объект проекта
Класс `Project` является верхнеуровневым объектом Aspose.Tasks, представляющим файл Microsoft Project в памяти. Его создание даёт вам пустой проект, который можно заполнять задачами, ресурсами и календарями.

```java
Project project = new Project();
```
Здесь мы создаём новый объект `Project` — он представляет файл MS Project, который будет содержать наш список задач.

## Шаг 2: добавить задачу в проект
Класс `Task` представляет отдельный элемент работы в расписании проекта. Каждая `Task` может иметь собственную продолжительность, дату начала и назначения ресурсов.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
С помощью `getRootTask()` мы получаем корень иерархии проекта и **add task to Microsoft Project**. Строка `"Task"` — это имя задачи; вы можете заменить её любой необходимой вам описательной строкой.

## Шаг 3: установить базовый план для выбранных задач
`BaselineType` — перечисление, определяющее, в какой слот базового плана (Baseline, Baseline1 … Baseline10) записывать данные. Передавая список задач, вы можете установить базовый план только для выбранных элементов.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Чтобы **set baseline without MS Project**, создайте список задач, которые нужно включить в базовый план (здесь `myList`) и передайте его в `setBaseline`. Заполните `myList` задачами, которые вы добавили, если нужен выборочный базовый план.

## Шаг 4: установить базовый план для всего проекта
`setBaseline` записывает выбранные значения базового плана во все задачи проекта.  
Если вы хотите установить базовый план для всего проекта одним вызовом, просто вызовите `setBaseline` с нужным `BaselineType`.

```java
project.setBaseline(BaselineType.Baseline);
```
Этот вызов записывает выбранные значения базового плана для **every task** в проекте, обеспечивая полную копию оригинального расписания.

## Как добавить задачу в Microsoft Project с помощью Aspose.Tasks
Метод `add()` создаёт новую дочернюю задачу под указанной родительской задачей и возвращает только что созданный объект `Task`.  
Вы добавляете задачу, вызывая `add()` у родительского объекта `Task` (обычно у корневой задачи). Метод возвращает новый экземпляр `Task`, который можно дальше настраивать — продолжительность, дату начала, ресурсы или пользовательские поля — перед сохранением файла проекта.

## Как установить базовый план без MS Project
Aspose.Tasks позволяет полностью создавать базовый план через код. Выберите `BaselineType` (например, `BaselineType.Baseline`) и вызовите `setBaseline`. При необходимости можно повторить процесс с `Baseline1`‑`Baseline10`, чтобы хранить несколько ревизий базовых планов, всё без открытия Microsoft Project.

## Распространённые проблемы и решения
- **Baseline not appearing:** Убедитесь, что вызываете `project.save("output.mpp")` после установки базового плана (шаг сохранения опущен здесь для краткости).  
- **Task list appears empty:** Проверьте, что вы добавляете задачи к правильному родителю (`getRootTask()` или подзадаче).  
- **Version mismatch errors:** Используйте последнюю версию Aspose.Tasks JAR, чтобы гарантировать совместимость с новыми форматами .mpp.

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Tasks for Java без установленного Microsoft Project?**  
A: Да, Aspose.Tasks работает независимо и не требует Microsoft Project на хост‑машине.

**Q: Совместим ли Aspose.Tasks for Java с разными версиями Microsoft Project?**  
A: Абсолютно. Библиотека поддерживает файлы Project начиная с 2007 года и до последних выпусков 2024 года.

**Q: Можно ли управлять ресурсами проекта с помощью Aspose.Tasks for Java?**  
A: Да, вы можете программно добавлять, обновлять и удалять ресурсы, так же как и задачи.

**Q: Поддерживает ли Aspose.Tasks for Java установку зависимостей задач?**  
A: Да, вы можете определять отношения предшественник‑последователь с помощью класса `TaskLink`.

**Q: Доступна ли техническая поддержка для Aspose.Tasks for Java?**  
A: Да, помощь можно получить через [support forum](https://forum.aspose.com/c/tasks/15), где сотрудники Aspose и сообщество отвечают на вопросы.

## Заключение
Следуя этим шагам, вы узнали, как **add task to project** на Java, создать список задач и **set baseline without MS Project** с помощью Aspose.Tasks. Такой подход упрощает автоматизацию проектов, устраняет необходимость в настольных установках Project и предоставляет полный программный контроль над каждым аспектом вашего расписания.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Связанные руководства

- [Как создать проект aspose.tasks – Установить новые атрибуты задачи](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Как установить длительность базового плана в Aspose.Tasks для Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Создание задач Aspose Java – Свойства задачи](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}