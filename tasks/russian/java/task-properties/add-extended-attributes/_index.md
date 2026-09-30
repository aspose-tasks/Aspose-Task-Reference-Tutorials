---
date: 2026-09-30
description: Узнайте, как создать расширенный атрибут задачи с помощью Aspose.Tasks
  for Java, ведущей библиотеки управления проектами на Java для добавления пользовательских
  полей задачи.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Как создать расширенный атрибут задачи с Aspose.Tasks Java
og_description: Узнайте, как создать расширенный атрибут задачи с помощью Aspose.Tasks
  for Java, ведущей библиотеки управления проектами на Java для добавления пользовательских
  полей задачи.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Как создать расширенный атрибут задачи с Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Как создать расширенный атрибут задачи с Aspose.Tasks Java
url: /ru/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать расширенный атрибут задачи с Aspose.Tasks Java

## Введение
В этом руководстве вы узнаете, как **создать расширенный атрибут задачи** в файле Microsoft Project, используя Aspose.Tasks for Java. Добавление пользовательских полей позволяет фиксировать данные, специфичные для проекта, которые не покрываются встроенными колонками, обеспечивая более тонкий контроль над отчетностью и планированием ресурсов. К концу руководства вы сможете добавлять атрибуты простого текста, с поддержкой списка выбора и длительности к любой задаче.

## Быстрые ответы
- **Что означает «расширенный атрибут»?** Это пользовательское поле, которое вы определяете и привязываете к задачам, ресурсам или назначениям.  
- **Какая библиотека добавляет эту возможность?** Aspose.Tasks for Java, библиотека управления проектами на Java.  
- **Нужна ли лицензия для пробного использования?** Да — бесплатная 30‑дневная пробная версия доступна на сайте Aspose.  
- **Можно ли добавить значения списка выбора?** Конечно; вы можете предоставить список разрешённых значений для текстовых или длительных полей.  
- **Совместим ли API с Java 8 и более новыми версиями?** Да, он поддерживает Java 8+ и работает на всех основных операционных системах.

## Что такое расширенный атрибут задачи?
Расширенный атрибут задачи — это пользовательская колонка, которая хранит дополнительную информацию для каждой задачи в файле проекта. Он ведёт себя как встроенное поле, но может содержать любой тип данных, который вам нужен, например текст, числа, даты или длительности.

## Почему использовать Aspose.Tasks for Java?
Aspose.Tasks поддерживает **более 50 форматов файлов** и может обрабатывать проекты с **более 10 000 задачами**, не требуя установки Microsoft Project. Библиотека работает полностью офлайн, гарантируя конфиденциальность данных и предсказуемую производительность для корпоративных решений.

## Требования
- Базовые знания программирования на Java.  
- Установленная библиотека Aspose.Tasks for Java. Вы можете скачать её с [веб‑сайта](https://releases.aspose.com/tasks/java/).  
- Java IDE (IntelliJ IDEA, Eclipse или VS Code), настроенная на вашем компьютере.

## Импорт пакетов
`import`‑операторы дают вам доступ к основным классам, которые понадобятся, таким как `Project`, `ExtendedAttributeDefinition` и `ExtendedAttribute`.

`Project` представляет файл Microsoft Project и предоставляет методы для чтения, изменения и сохранения.  
`ExtendedAttributeDefinition` определяет пользовательское поле, которое можно привязать к задачам, ресурсам или назначениям.  
`ExtendedAttribute` — это экземпляр определения, содержащий фактическое значение для конкретного объекта.

## Как добавить расширенный атрибут в виде простого текста к задаче?
Чтобы добавить расширенный атрибут простого текста, сначала загрузите проект, затем создайте определение типа Text, добавьте его в коллекцию проекта, создайте задачу, создайте атрибут из определения, задайте его текстовое значение, привяжите к задаче и, наконец, сохраните проект.

### 1. Установите путь к каталогу документов
Укажите, где находятся ваши исходные и выходные файлы.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Создайте новый проект
Создайте объект `Project`, при необходимости загрузив существующий файл .mpp.

```java
String dataDir = "Your Document Directory";
```

### 3. Создайте определение расширенного атрибута типа Text1
Определите пользовательское поле как колонку простого текста с именем «Text1».

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Добавьте определение в коллекцию расширенных атрибутов проекта
Зарегистрируйте новое определение, чтобы проект его распознал.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Добавьте задачу в проект
Создайте задачу, которая получит пользовательское поле.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Создайте расширенный атрибут из определения атрибута
Создайте экземпляр, который можно привязать к конкретной задаче.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Присвойте значение созданному расширенному атрибуту
Установите фактический текст, который хотите сохранить, например «Design Review».

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Добавьте расширенный атрибут к задаче
Привяжите экземпляр атрибута к коллекции `ExtendedAttributes` задачи.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Сохраните проект
Запишите обновлённый проект обратно на диск в нужном формате.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Как добавить текстовый атрибут со списком выбора?
При добавлении текстового атрибута со списком выбора вы следуете тем же шагам, что и для простого текста, но перед добавлением определения заполняете его коллекцию `LookupValues` разрешёнными строками. Эти значения отображаются в виде выпадающего списка в Microsoft Project, обеспечивая согласованность данных.

## Как добавить атрибут длительности со списком выбора?
Чтобы добавить атрибут длительности со списком выбора, замените тип `Text1` на `Duration2` при создании определения, затем заполните коллекцию `LookupValues` строками длительности, например «1 day», «2 days» и т.д. После добавления определения в проект создайте экземпляр атрибута, задайте значение длительности, привяжите его к задаче и сохраните файл.

## Распространённые проблемы и их устранение
- **Lookup values not appearing** – Убедитесь, что вы добавляете каждую запись списка выбора в коллекцию `LookupValues` *до* вызова `project.getExtendedAttributes().add(definition)`.  
- **Attribute value not saved** – Проверьте, что вы добавляете экземпляр `ExtendedAttribute` к задаче *после* установки его значения.  
- **File size grows unexpectedly** – При работе с очень большими проектами рассмотрите возможность вызова `project.setSaveOptions(new ProjectSaveOptions())` для включения инкрементного сохранения.

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Tasks for Java с другими Java‑библиотеками?**  
A: Да, Aspose.Tasks for Java легко интегрируется с любой Java‑экосистемой, включая Spring, Hibernate и Apache POI.

**Q: Подходит ли Aspose.Tasks for Java для крупномасштабных приложений управления проектами?**  
A: Абсолютно. Библиотека спроектирована для работы с проектами, содержащими тысячи задач, и поддерживает потоковую обработку для снижения потребления памяти.

**Q: Есть ли лицензионные ограничения при использовании Aspose.Tasks for Java в коммерческом проекте?**  
A: Да, требуется действующая коммерческая лицензия. Подробности можно посмотреть на [веб‑сайте Aspose.Tasks](https://purchase.aspose.com/buy).

**Q: Как получить поддержку или помощь по Aspose.Tasks for Java?**  
A: Посетите [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для получения помощи от сообщества или откройте запрос в службу поддержки через ваш аккаунт Aspose.

**Q: Можно ли попробовать Aspose.Tasks for Java перед покупкой?**  
A: Да, бесплатную пробную версию можно получить на странице [Aspose.Tasks free trial](https://releases.aspose.com/).

**Last updated:** 2026-09-30  
**Tested with:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Связанные руководства

- [Custom columns and extended attributes in Java project management](/tasks/java/project-management/extended-attributes/)
- [Read Extended Task Attributes with Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [How to Create Project aspose.tasks – Set New Task Attributes](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}