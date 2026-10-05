---
date: 2026-10-05
description: Узнайте, как создать тестовый проект и вычислить количество дней между
  датами с помощью Aspose.Tasks for Java, добавить пользовательское поле и эффективно
  работать с файлами MPP.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Работа с формулами в Aspose.Tasks
og_description: Создать тестовый проект и вычислить количество дней между датами с
  помощью Aspose.Tasks for Java. В этом руководстве показано, как добавить пользовательское
  поле, установить сроки задач и сохранить проект в файл MPP.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Создать тестовый проект и вычислить количество дней между датами
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Создать тестовый проект и вычислить количество дней между датами
url: /ru/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать тестовый проект и вычислить количество дней между датами

В этом руководстве вы **создадите тестовый проект** и **вычислите количество дней между датами**, добавив пользовательское поле, определив расширенный атрибут и применив формулу Microsoft Project через библиотеку Aspose.Tasks для Java. Независимо от того, нужно ли вам генерировать расписания, вычислять сроки или автоматизировать отчётность, Aspose.Tasks позволяет программно работать с данными Project без установки настольного приложения, поддерживая более 50 форматов ввода‑вывода и обрабатывая файлы в сотни страниц в режиме экономии памяти.

## Быстрые ответы
- **Что покрывает руководство?** Оно показывает, как создать тестовый проект, определить расширенный атрибут, установить дедлайн задачи и использовать формулу для вычисления количества дней между датами.  
- **Какая библиотека требуется?** Aspose.Tasks for Java (последняя версия).  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для использования в продакшене требуется коммерческая лицензия.  
- **Какую IDE можно использовать?** Любую Java‑IDE (IntelliJ IDEA, Eclipse, VS Code), поддерживающую JDK 8+.  
- **Сколько времени занимает реализация?** Около 10‑15 минут на копирование кода и его запуск.

## Что такое «вычисление количества дней между датами» в Aspose.Tasks?
В Aspose.Tasks формула — это строка, которая может ссылаться на поля задачи и выполнять вычисления. `[Deadline] - [Finish]` — синтаксис формулы, используемый Aspose.Tasks для возврата числовой разницы в днях между двумя полями даты. Результат хранится как числовое значение, представляющее полные дни, которое можно отобразить в пользовательском поле или использовать в дальнейших вычислениях.

## Почему стоит использовать Aspose.Tasks для вычисления количества дней между датами?
Aspose.Tasks предоставляет **полное покрытие API** для всех свойств Project, Task и Resource, работает на Windows, Linux и macOS и **не требует установки Microsoft Project или Office**. Движок может обрабатывать проекты с **500+ задачами** менее чем за секунду на типичном серверном оборудовании, что делает его идеальным для CI‑конвейеров, Docker‑контейнеров и высокообъёмной пакетной обработки.

## Как установить дедлайн для задачи
`java.util.Calendar` — класс Java, представляющий конкретный момент времени. Вы задаёте дедлайн, присваивая значение `java.util.Calendar` полю `Tsk.DEADLINE` задачи. После создания экземпляра Calendar задайте его год, месяц и день желаемого дедлайна, затем вызовите `task.set(Tsk.DEADLINE, calendar);`. Дедлайн сохраняется в файле проекта и может использоваться в формулах, таких как `[Deadline] - [Finish]`.

## Как определить расширенный атрибут
Расширенный атрибут — это пользовательское поле, в котором хранится результат вашей формулы. Вы создаёте его один раз, задаёте удобный псевдоним и привязываете выражение `[Deadline] - [Finish]`, чтобы каждая задача автоматически вычисляла интервал. Создайте его, создав экземпляр `ExtendedAttribute`, задав его Alias, присвоив формулу и добавив в коллекцию проекта.

## Требования
Перед началом убедитесь, что у вас есть следующее:

- **Java Development Kit (JDK) 8+** – загрузите с сайта Oracle или используйте OpenJDK.  
- **Aspose.Tasks for Java** – получите последний JAR с [страницы загрузки Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/) и добавьте его в classpath проекта или в зависимости Maven/Gradle.

## Импорт пакетов
Сначала импортируйте необходимые классы:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Пошаговое руководство

### Шаг 1: Создать тестовый проект с пользовательским полем
Мы начинаем с **создания тестового проекта** и добавления пользовательского поля, которое позже будет содержать результат нашей формулы.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` — вспомогательный метод, который создает минимальное расписание и регистрирует расширенный атрибут, готовый к назначению формулы.

### Шаг 2: Определить расширенный атрибут (добавить пользовательское поле)
Далее мы **определяем расширенный атрибут** — по сути пользовательское поле — и задаём ему удобный псевдоним. Здесь мы **добавляем логику пользовательского поля**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** делает поле читаемым в Project.  
- **Formula** вычисляет количество дней между датой *Finish* задачи и её *Deadline* — ядро *вычисления количества дней между датами*.

### Шаг 3: Установить дедлайн для задачи (добавить задачу‑дедлайн и установить дедлайн задачи)
Теперь мы **добавляем данные задачи‑дедлайна**, устанавливая свойство *Deadline* у конкретной задачи.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Экземпляр `Calendar` определяет точный момент дедлайна.  
- `set(Tsk.DEADLINE, …)` **устанавливает дедлайн задачи** для выбранной задачи.

### Шаг 4: Сохранить проект (манипулировать файлом Microsoft Project)
Наконец, мы **манипулируем Microsoft Project**, сохраняя изменения в файл MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Вы можете открыть `SaveFile.mpp` в Microsoft Project, чтобы увидеть пользовательское поле, результат формулы и установленный дедлайн в расписании.

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|---------|
| **Formula not evaluating** | Убедитесь, что строка `Formula` атрибута использует правильные имена полей (например, `[Deadline]`, `[Finish]`). |
| **Task not found** | Проверьте, что ID задачи (`1` в примере) существует; используйте `project.getRootTask().getChildren().size()` для отладки. |
| **License exception** | Примените действующую лицензию Aspose.Tasks перед вызовом любых методов API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Tasks с другими языками программирования?**  
A: Да, Aspose.Tasks предоставляет API для .NET, Java и других платформ, позволяя работать с файлами Microsoft Project на выбранном вами языке.

**Q: Доступна ли бесплатная пробная версия Aspose.Tasks?**  
A: Абсолютно. Скачайте полностью функциональную пробную версию со [страницы загрузки Aspose.Tasks](https://releases.aspose.com/).

**Q: Где найти подробную документацию по Aspose.Tasks?**  
A: Официальная документация размещена по адресу [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Как получить поддержку по Aspose.Tasks?**  
A: Посетите [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15), чтобы задать вопросы и поделиться опытом с сообществом.

**Q: Нужна ли временная лицензия для оценки?**  
A: Временная лицензия доступна для краткосрочного тестирования; её можно запросить на [странице запроса временной лицензии](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-10-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Связанные руководства

- [Как создать файл MPP – создать и сохранить пустой проект в формате MPP с помощью Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Установить дату начала проекта в MS Project с помощью Aspose.Tasks для Java](/tasks/java/project-properties/write-project-info/)
- [Как создать расширенный атрибут в Java с Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}