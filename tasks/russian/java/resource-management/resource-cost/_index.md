---
date: 2026-06-15
description: Узнайте, как управлять затратами в файлах MS Project с использованием
  Aspose.Tasks for Java, включая загрузку MPP‑файла и чтение actual cost work и budgeted
  cost schedule.
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: Работа с затратами ресурсов в Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Как управлять затратами в MS Project с помощью Aspose.Tasks for Java
url: /ru/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как управлять затратами в MS Project с помощью Aspose.Tasks для Java

## Введение

Управление бюджетами проектов является основной обязанностью любого менеджера проекта, и **как управлять затратами** эффективно может стать решающим фактором успеха проекта. Aspose.Tasks for Java предоставляет программный контроль над файлами Microsoft Project, позволяя читать и обновлять данные о затратах ресурсов без необходимости открывать файл .mpp вручную. В этом учебнике вы шаг за шагом увидите, как загрузить файл MPP, проверить фактические затраты работы и извлечь планируемый график затрат для каждого ресурса.

## Быстрые ответы
- **Что делает Aspose.Tasks для Java?** Он читает и записывает файлы Microsoft Project (.mpp) без необходимости установки Microsoft Project.  
- **Как загрузить файл MPP?** Use `new Project("path/to/file.mpp")` – API разбирает файл в памяти.  
- **Какие поля затрат доступны?** Actual Cost Work (ACWP), Budgeted Cost of Work Scheduled (BCWS) и Budgeted Cost of Work Performed (BCWP).  
- **Нужна ли лицензия для разработки?** Бесплатная временная лицензия работает для тестирования; полная лицензия требуется для продакшна.  
- **Какие версии Java поддерживаются?** Java 8 и выше, включая Java 17 LTS.

## Как управлять затратами в MS Project?

Загрузите ваш проект с помощью `new Project("yourFile.mpp")`, затем пройдитесь по каждому объекту `Resource`, чтобы прочитать свойства, связанные с затратами, такие как ACWP, BCWS и BCWP. Aspose.Tasks автоматически конвертирует внутренние значения затрат в валюту проекта, поэтому вы можете отображать их или сохранять напрямую. Такой подход устраняет необходимость ручных расчётов в таблицах и гарантирует согласованность данных во всех отчётах проекта.

## Предварительные требования

1. Базовое понимание программирования на Java.  
2. Библиотека Aspose.Tasks for Java добавлена в ваш проект (Maven/Gradle или вручную JAR).  
3. Доступ к файлу Microsoft Project (`.mpp`), который вы хотите проанализировать.  

## Импорт пакетов

Классы `Project` и `Resource` являются точками входа для работы с данными проекта.

Класс `Project` — это объект верхнего уровня Aspose.Tasks, представляющий один файл Microsoft Project в памяти.  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## Шаг 1: Определите каталог данных

Сначала укажите папку, содержащую ваш файл `.mpp`. Этот путь может быть абсолютным или относительным к рабочему каталогу вашего приложения.

```text
```java
String dataDir = "Your Data Directory";
```
```

## Шаг 2: Загрузите файл MS Project

`Project` загружает файл и строит объектную модель, которую вы можете запросить. API разбирает файл без необходимости установки Microsoft Project, поддерживая более 30 форматов ввода.

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## Шаг 3: Переберите ресурсы

Объекты `Resource` представляют людей, оборудование или материалы, потребляющие бюджет. Вы можете пройтись по коллекции `project.getResources()` для доступа к каждому из них.

```text
```java
for (Resource res : prj.getResources()) {
```
```

## Шаг 4: Проверьте имя ресурса и затраты

Для каждого ресурса проверьте, определено ли имя, затем прочитайте поля затрат. Метод `getActualCost()` возвращает **actual cost work** (ACWP), в то время как `getBudgetedCost()` предоставляет **budgeted cost schedule** (BCWS/BCWP).

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## Почему использовать Aspose.Tasks for Java для загрузки файла MPP?

Aspose.Tasks поддерживает **30+ форматов файлов** (включая `.mpp`, `.xml` и `.xlsx`) и может обрабатывать проекты с **до 10 000 задач**, используя менее 200 МБ ОЗУ. Библиотека выполняет все расчёты на стороне сервера, устраняя необходимость в лицензированной копии Microsoft Project.

## Распространённые проблемы и решения

- **Null resource names:** Некоторые устаревшие файлы содержат резервные ресурсы. Всегда проверяйте `resource.getName() != null` перед доступом к полям затрат.  
- **Large files causing memory pressure:** LoadOptions — это класс конфигурации, позволяющий указать, какие данные проекта загружать. Используйте `project.setLoadOptions(LoadOptions.setLoadResourceData(false))`, чтобы загрузить только необходимые данные, а затем включить их позже при необходимости.  
- **Currency mismatches:** API учитывает настройки валюты проекта; при необходимости вы можете переопределить их с помощью `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)`. CostRateTableType перечисляет различные таблицы ставок затрат, которые могут быть применены к задаче.

## Часто задаваемые вопросы

**Q: Может ли Aspose.Tasks for Java обрабатывать сложные структуры проектов?**  
A: Да, он полностью поддерживает вложенные задачи‑сводки, несколько календарей ресурсов и пользовательские поля во всех поддерживаемых версиях Project.

**Q: Совместима ли библиотека с разными версиями файлов Microsoft Project?**  
A: Абсолютно. Aspose.Tasks читает и записывает файлы от Microsoft Project 2000 до последнего формата 2023 года.

**Q: Могу ли я интегрировать Aspose.Tasks for Java с другими библиотеками Java?**  
A: Да, API возвращает стандартные объекты Java, что позволяет без проблем интегрировать его с фреймворками логирования, ORM‑инструментами или библиотеками отчетности.

**Q: Предоставляет ли Aspose.Tasks for Java поддержку клиентов?**  
A: Aspose предоставляет специализированную поддержку на форумах, подробную документацию и оперативную помощь по электронной почте для лицензированных пользователей.

**Q: Есть ли бесплатная пробная версия Aspose.Tasks for Java?**  
A: Вы можете скачать 30‑дневную оценочную лицензию с сайта Aspose, чтобы бесплатно ознакомиться со всеми функциями.

---

**Последнее обновление:** 2026-06-15  
**Тестировано с:** Aspose.Tasks for Java 24.12  
**Автор:** Aspose

## Связанные руководства

- [Как рассчитать отклонение затрат и управлять затратами назначений с Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Управление бюджетом, работой и затратами задач в Aspose.Tasks](/tasks/java/task-properties/task-budget-work-cost/)
- [Добавление ресурса в проект с помощью Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}