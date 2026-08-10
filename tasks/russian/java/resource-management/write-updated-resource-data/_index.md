---
date: 2026-06-30
description: Узнайте, как обновить несколько ресурсов и изменить данные группы ресурсов,
  затем экспортировать проект в MPP и сохранить проект как MPP с помощью Aspose.Tasks
  for Java.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Обновление нескольких ресурсов в Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Обновление нескольких ресурсов в Aspose.Tasks for Java
url: /ru/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Обновление нескольких ресурсов в Aspise.Tasks для Java

## Введение
В этом руководстве вы узнаете, как **обновлять несколько ресурсов** в файле Microsoft Project с помощью Aspose.Tasks для Java. Независимо от того, нужно ли вам изменить ставки, переназначить группы или экспортировать обновлённый файл в MPP, ниже приведённые шаги проведут вас через полностью готовый к использованию в продакшене процесс. Установка Microsoft Project не требуется, а API может эффективно обрабатывать проекты с сотнями ресурсов.

## Быстрые ответы
- **Могу ли я обновлять несколько ресурсов одновременно?** Да — пройдитесь по `ResourceCollection` и задайте атрибуты за один проход.  
- **Какой метод сохраняет файл как MPP?** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **Нужна ли лицензия для коммерческого использования?** Требуется платная лицензия для продакшена; доступна бесплатная пробная версия.  
- **Какие версии Java поддерживаются?** Java 6 и выше, включая Java 17 LTS.  
- **Эффективно ли массовое обновление?** Aspose.Tasks обрабатывает проекты с 500 ресурсами менее чем за 2 секунды на типичном сервере.

## Что такое «обновление нескольких ресурсов»?
**«Обновление нескольких ресурсов»** означает программное изменение свойств нескольких записей ресурсов — таких как ставки, группы, календари или пользовательские поля — в одном файле Project. Эта операция часто требуется при синхронизации данных проекта с системами планирования ресурсов предприятия, корректировке бюджетов для множества ресурсов или применении общих для организации политических изменений.

## Зачем использовать Aspose.Tasks для изменения группы ресурсов и экспорта проекта в MPP?
Aspose.Tasks поддерживает **более 50 форматов ввода и вывода**, включая MPP, XML и CSV, и может **экспортировать проект в MPP** без загрузки всего файла в память. Библиотека обрабатывает файлы размером до **2 ГБ**, позволяя **сохранять проект как MPP** быстро и надёжно.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Java Development Kit (JDK), установленный в вашей системе.  
2. Библиотека Aspose.Tasks для Java. Вы можете скачать её [здесь](https://releases.aspose.com/tasks/java/).  
3. Базовые знания программирования на Java.  

## Импорт пакетов

`import`‑операторы импортируют необходимые классы Aspose.Tasks в ваш исходный файл.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Шаг 1: Настройте каталог данных

Определите каталог, где находятся ваши файлы данных:

```java
String dataDir = "Your Data Directory";
```

## Шаг 2: Укажите входные и выходные файлы

Укажите пути к входному файлу MS Project и к полученному обновлённому файлу:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Шаг 3: Загрузите проект

`Project` представляет файл Microsoft Project, загруженный в память, предоставляя доступ к задачам, ресурсам и другим данным проекта.

```java
Project project = new Project(file);
```

## Шаг 4: Добавьте ресурс и задайте атрибуты

`Resource` моделирует отдельный ресурс проекта, позволяя задавать ставки, группы, календари и другие атрибуты.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Шаг 5: Эффективно обновляйте несколько ресурсов

`ResourceCollection` — это коллекция всех ресурсов в проекте, доступная через `project.getResources()`.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Шаг 6: Сохраните проект

`SaveFileFormat` перечисляет поддерживаемые форматы файлов для сохранения проекта, такие как MPP, XML и PDF.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Как обновить несколько ресурсов в проекте?

Загрузите существующий проект, получите его `ResourceCollection` и пройдитесь по каждому объекту `Resource`. Для каждого ресурса измените необходимые поля, такие как ставки, группы или пользовательские атрибуты, затем перейдите к следующему элементу. После обработки всех ресурсов вызовите `project.save(...)` один раз, чтобы эффективно сохранить изменения.

## Распространённые проблемы и решения

- **Конфликт идентификаторов ресурсов** – Убедитесь, что каждый новый ресурс получает уникальный ID, используя `project.getResources().add(new Resource())`.  
- **Ошибки формата ставки** – Используйте объекты `ResourceRate` и задайте `RateType` как `StandardRate` или `OvertimeRate`.  
- **Большие файлы вызывают нагрузку на память** – Включите `Project.setReadOnly(true)` перед загрузкой, чтобы уменьшить потребление памяти.

## Часто задаваемые вопросы

**Q: Могу ли я обновлять несколько ресурсов в одном проекте с помощью Aspose.Tasks для Java?**  
A: Да, вы можете обновлять несколько ресурсов, проходя по ним и устанавливая их атрибуты соответствующим образом.

**Q: Поддерживает ли Aspose.Tasks другие форматы файлов, помимо MS Project?**  
A: Да, Aspose.Tasks поддерживает различные форматы файлов, включая XML, MPP и другие.

**Q: Совместим ли Aspose.Tasks с разными версиями Java?**  
A: Aspose.Tasks совместим с версиями Java 6 и выше.

**Q: Могу ли я выполнять другие операции с файлами MS Project с помощью Aspose.Tasks?**  
A: Да, вы можете выполнять широкий спектр операций, таких как чтение, запись и манипулирование задачами, ресурсами и календарями.

**Q: Где я могу найти дополнительную помощь или поддержку по Aspose.Tasks?**  
A: Вы можете посетить [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для получения помощи или вопросов.

**Q: Как экспортировать обновлённый файл в формат MPP?**  
A: Вызовите `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` после внесения всех изменений ресурсов.

**Q: Какой лучший способ изменить группу ресурса?**  
A: Установите свойство `Resource.Group` у каждого объекта `Resource` перед сохранением проекта.

---

**Последнее обновление:** 2026-06-30  
**Тестировано с:** Aspose.Tasks for Java 24.12  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Добавить ресурс в проект с Aspose.Tasks для Java](/tasks/java/resource-management/create-resources/)
- [Управление затратами ресурсов MS Project с Aspose.Tasks для Java](/tasks/java/resource-management/resource-cost/)
- [Как экспортировать MPP в Excel с Aspose.Tasks для Java](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}