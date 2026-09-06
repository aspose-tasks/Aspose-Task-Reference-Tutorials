---
date: 2026-08-24
description: Узнайте, как добавить resource в MS Project, установить standard rate
  и другие свойства resource в MS Project с помощью Aspose.Tasks for Java и эффективно
  управлять ресурсами.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Установить свойства Resource в Aspose.Tasks
og_description: Добавить resource в MS Project и установить standard rate с помощью
  Aspose.Tasks for Java. Узнайте требования, пошаговый код и устранение неполадок
  в этом кратком руководстве.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Добавить resource в MS Project и установить rate с Aspose.Tasks (Java)
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Как добавить resource в MS Project с Aspose.Tasks
url: /ru/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить ресурс ms project и установить ставку в Aspose.Tasks

## Введение
Если вы разрабатываете Java‑приложения, которым необходимо читать или записывать файлы Microsoft Project, **adding a resource ms project** и настройка её стандартной ставки — это рутинная, но важная задача. В этом руководстве вы увидите, как создать объект `Project`, добавить ресурс и установить как стандартную, так и сверхурочную ставки с помощью Aspose.Tasks для Java. К концу вы сможете автоматизировать расчёт затрат и поддерживать графики проекта в актуальном состоянии без необходимости установки Microsoft Project.

## Быстрые ответы
- **Какой класс представляет файл проекта?** `Project`
- **Какой вызов добавляет новый ресурс?** `project.getResources().add()`
- **Как установить стандартную ставку?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Требуется ли лицензия для использования в продакшене?** Да, необходимо загрузить действующую лицензию Aspose.Tasks.
- **Какие версии Java поддерживаются?** Java 8 и новее (рекомендовано Java 17+).

## Что такое «set standard rate»?
Операция *set standard rate* назначает ресурсам стоимость работы по умолчанию за час. Эта ставка используется менеджерами проектов для расчёта расходов на труд, формирования отчётов о затратах и прогнозирования бюджета, гарантируя, что расчёты затрат отражают ожидаемую цену выполненной работы каждым ресурсом на протяжении жизненного цикла проекта.

## Зачем устанавливать ставки с помощью Aspose.Tasks?
Aspose.Tasks может обрабатывать **более 50 форматов ввода и вывода**, включая файлы MPP, MPX, XML и Primavera, и справляется с проектами в сотни страниц без загрузки всего файла в память. Это обеспечивает высокопроизводительную пакетную обработку на серверах Windows, Linux или macOS, сокращая ручные трудозатраты до 90 % в типичных сценариях автоматизации.

## Требования
Прежде чем начать, убедитесь, что следующие элементы готовы:

### Настройка среды разработки Java
1. Установите JDK 8 или новее. Вы можете скачать его с [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Выберите IDE, такую как IntelliJ IDEA, Eclipse или NetBeans, и настройте её для разработки на Java.

### Установка Aspose.Tasks для Java
1. Скачайте последнюю версию пакета Aspose.Tasks для Java со [download page](https://releases.aspose.com/tasks/java/).  
2. Добавьте файлы JAR в classpath вашего проекта или объявите зависимость Maven/Gradle, как показано в документации продукта.

## Импорт пакетов
Импортируйте основные классы Aspose.Tasks, которые вам понадобятся. Этот шаг предоставляет доступ к типам `Project`, `Resource` и `Rsc`, используемым далее.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Шаг 1: создать объект проекта
`Project` класс — это объект верхнего уровня, представляющий в памяти весь файл MS Project. Его создание создает пустой проект, который можно заполнять задачами, ресурсами и другими данными.

```java
Project project = new Project();
```

## Шаг 2: добавить ресурс (add resource ms project)
`Resource` класс моделирует отдельный ресурс проекта, такой как человек, оборудование или материал. Добавление ресурса через `project.getResources().add()` возвращает ненулевой экземпляр `Resource`, готовый к настройке свойств.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Шаг 3: установить свойства ресурса (how to set rates)
`Rsc` перечисление содержит константы для полей ресурса, таких как `STANDARD_RATE` и `OVERTIME_RATE`.  
Вы задаёте стандартную и сверхурочную ставки, вызывая `set` у объекта `Resource` с соответствующими значениями перечисления `Rsc`. Ставки хранятся как `BigDecimal` для сохранения денежной точности.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| `NullPointerException` при вызове `set` | Ресурс был добавлен некорректно. | Убедитесь, что `project.getResources().add()` возвращает ненулевой `Resource`. |
| Ставки отображаются как 0 в сохранённом файле | Используется `int` вместо `BigDecimal`. | Всегда используйте `BigDecimal.valueOf()` для денежных значений. |
| Лицензия не найдена | Файл лицензии не загружен перед созданием `Project`. | Загрузите лицензию (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) при запуске программы. |

## Заключение
Теперь вы знаете, как **add resource ms project**, создать объект `Project` и **set standard and overtime rates** с помощью Aspose.Tasks для Java. Эта возможность позволяет автоматизировать расчёт затрат, генерировать пользовательские отчёты и полностью управлять ресурсами MS Project из любого Java‑приложения.

## Часто задаваемые вопросы
**Q: Может ли Aspose.Tasks для Java обрабатывать сложные файлы MS Project?**  
A: Да, он поддерживает все основные форматы Project, включая большие файлы с тысячами задач и ресурсов, сохраняет каждое поле без потери данных.

**Q: Доступна ли бесплатная пробная версия?**  
A: Да, вы можете получить бесплатную пробную версию Aspose.Tasks для Java на странице [Aspose.Tasks free trial page](https://releases.aspose.com/).

**Q: Где я могу получить поддержку Aspose.Tasks для Java?**  
A: Вы можете обратиться за помощью на [support forum](https://forum.aspose.com/c/tasks/15).

**Q: Как получить временную лицензию для оценки?**  
A: Временная лицензия доступна на странице [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Где можно приобрести лицензионную версию?**  
A: Приобретите полную лицензию на странице [purchase page](https://purchase.aspose.com/buy).

---

**Последнее обновление:** 2026-08-24  
**Тестировано с:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Автор:** Aspose

## Связанные руководства

- [Как создать ресурсы – Управление ресурсами с Aspose.Tasks для Java](/tasks/java/resource-management/)
- [Добавить ресурс в проект с Aspose.Tasks для Java](/tasks/java/resource-management/create-resources/)
- [Как добавить ресурс в проект и работать со свойствами задержки выравнивания в Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}