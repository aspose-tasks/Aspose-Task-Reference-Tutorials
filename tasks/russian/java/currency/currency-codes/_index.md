---
date: 2026-09-25
description: Узнайте, как извлекать currency codes из файлов MS Project с помощью
  Aspose.Tasks for Java — быстрый способ получить currency code, необходимый разработчикам
  Java.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Управление Currency Codes в Aspose.Tasks
og_description: Получить currency code Java из файлов MS Project с помощью Aspose.Tasks.
  Это руководство показывает, как прочитать проект, извлечь ISO currency identifier
  и применить его в Java‑приложениях.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Получить currency code Java из MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Получить currency code Java из MS Project с помощью Aspose.Tasks
url: /ru/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Получить код валюты java из MS Project с помощью Aspose.Tasks

## Введение
В этом руководстве вы узнаете **как получить код валюты java** из файла MS Project, используя API Aspose.Tasks для Java. Независимо от того, нужно ли вам генерировать финансовые отчёты в нескольких валютах, консолидировать проекты из разных регионов или просто отображать правильный денежный символ в downstream‑системе, нижеописанные шаги проведут вас от настройки окружения до однострочного вызова, возвращающего ISO‑идентификатор валюты. К концу руководства вы будете уверенно загружать любой поддерживаемый формат файла Project и извлекать трёхбуквенный код валюты, такой как `USD`, `EUR` или `GBP`.

## Краткие ответы
- **Что делает API?** Он читает файлы MS Project и предоставляет свойства, такие как код валюты.  
- **Какой язык используется?** Java, через библиотеку Aspose.Tasks для Java.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.  
- **Можно ли получить код в одну строку?** Да — `prj.get(Prj.CURRENCY_CODE)` мгновенно возвращает строку кода валюты.  
- **Совместим ли он со всеми версиями Project?** Aspose.Tasks поддерживает более 20 форматов ввода, включая устаревшие MPP, XML и XER.

## Что такое чтение файла MS Project?
Чтение файла MS Project означает программное открытие *.mpp* (или любого другого поддерживаемого формата, такого как XML или XER) и доступ к его внутренним структурам данных. Эти структуры включают задачи, ресурсы, календари, таблицы затрат и финансовые настройки. Парсинг файла позволяет извлекать информацию без запуска Microsoft Project, что упрощает автоматизированную отчётность, миграцию и интеграционные рабочие процессы.

## Зачем использовать Aspose.Tasks для чтения файлов msproject?
Aspose.Tasks предлагает чисто Java‑решение, устраняющее необходимость в COM‑interop или локальной установке Microsoft Project. Он поддерживает более 20 форматов файлов, может обрабатывать проекты с тысячами задач, используя менее 100 МБ памяти, и предоставляет богатую объектную модель. Прямой доступ к константам вроде `Prj.CURRENCY_CODE` позволяет мгновенно и надёжно получать информацию о валюте.

## Требования
Перед тем как перейти к коду, убедитесь, что у вас есть следующее:

### Установлен Java Development Kit (JDK)
Требуется современный JDK (11 или новее). Скачайте его с официального сайта Oracle: [здесь](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Библиотека Aspose.Tasks для Java
Получите последние бинарные файлы Aspose.Tasks для Java и добавьте их в classpath вашего проекта. Полная документация и ссылки для загрузки доступны [здесь](https://reference.aspose.com/tasks/java/).

## Импорт пакетов
Класс `Project` и константы `Prj` находятся в пространстве имён `com.aspose.tasks`. Импортируйте их в начале вашего Java‑файла:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Пошаговое руководство

### Шаг 1: настройка каталога данных
Определите папку, содержащую ваш файл *.mpp*. Скорректируйте путь в соответствии с вашей средой, чтобы время выполнения могло найти файл проекта.

```java
String dataDir = "Your Data Directory";
```

### Шаг 2: загрузка файла проекта
Класс `Project` — это объект верхнего уровня Aspose.Tasks, представляющий один файл MS Project в памяти. Создание экземпляра читает файл и формирует модель в памяти, которую можно запросить.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Шаг 3: получение кода валюты
Константа `Prj.CURRENCY_CODE` указывает свойство, в котором хранится ISO‑идентификатор валюты. Вызов `prj.get(Prj.CURRENCY_CODE)` возвращает трёхбуквенный код за одну операцию.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Вывод будет содержать трёхбуквенный ISO‑код валюты (например, `USD`, `EUR`, `GBP`), который настроен в проекте.

### Шаг 4: как получить код валюты в Java (дополнительный контекст)
Загрузите ваш проект, вызовите `prj.get(Prj.CURRENCY_CODE)` и сохраните результат в `String`. Затем вы можете передать это значение любой финансовой службе, системе отчётности или UI‑компоненту, требующему идентификатор валюты.

### Шаг 5: (необязательно) использовать код валюты
Типичные downstream‑сценарии включают:

- **Генерацию отчётов** — добавить код перед колонками стоимости (`USD 1 200`).  
- **Интеграцию API** — отправлять ISO‑код в платёжные шлюзы, требующие параметр валюты.  
- **Консолидацию данных** — группировать несколько проектов по валюте для анализа портфеля.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|----------|----------|
| **Пустой вывод** | В файле проекта не задана валюта (по умолчанию пусто). | Установите валюту в Microsoft Project или задайте её через `prj.set(Prj.CURRENCY_CODE, "USD");` перед чтением. |
| **Файл не найден** | Неправильный путь `dataDir`. | Проверьте путь и убедитесь, что имя файла указано точно, с учётом регистра. |
| **Неподдерживаемая версия файла** | Очень старый или повреждённый *.mpp* файл. | Обновите до последней версии Aspose.Tasks или сначала конвертируйте файл в более новый формат в Microsoft Project. |

## Часто задаваемые вопросы

**В: Может ли Aspose.Tasks обрабатывать сложные структуры проектов?**  
О: Да, API читает многоуровневые иерархии задач, пулы ресурсов, пользовательские поля и календари без ограничений.

**В: Совместим ли Aspose.Tasks с разными версиями файлов MS Project?**  
О: Абсолютно. Поддерживаются MPP, XML, XER и другие форматы от Project 98 до последних выпусков Office.

**В: Предоставляет ли Aspose.Tasks документацию и поддержку?**  
О: Полная справочная API, примеры кода и выделенная техническая поддержка доступны на сайте Aspose.

**В: Можно ли попробовать Aspose.Tasks перед покупкой?**  
О: Да, предлагается бесплатная пробная версия, позволяющая оценить все функции, включая извлечение кода валюты.

**В: Где можно получить временную лицензию для оценки?**  
О: Временные лицензии доступны на [веб‑сайте](https://purchase.aspose.com/temporary-license/).

---

**Последнее обновление:** 2026-09-25  
**Тестировано с:** Aspose.Tasks for Java (последняя версия)  
**Автор:** Aspose

## Связанные руководства

- [Project Properties Java – Read Metadata with Aspose.Tasks](/tasks/java/project-properties/)
- [How to Read Project Information from Microsoft Project with Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [Retrieve MS Project Outline Codes in Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}