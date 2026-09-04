---
date: 2026-06-10
description: Узнайте, как создать расширенный атрибут в Java, загрузить файл Microsoft
  Project, установить числовые значения и сохранить проект в формате XML с помощью
  Aspose.Tasks for Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Работа с расширенными атрибутами ресурсов в Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Как создать расширенный атрибут в Java с Aspose.Tasks
url: /ru/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать расширенный атрибут в Java с Aspose.Tasks

## Введение
В этом практическом руководстве вы **создадите расширенный атрибут в Java** для файла Microsoft Project, используя Aspose.Tasks. Мы пройдем процесс загрузки существующего проекта, определения нового числового атрибута, назначения значения ресурсу и, наконец, сохранения изменений в виде XML‑файла. К концу вы получите переиспользуемый шаблон кода, который можно внедрить в любое Java‑решение для управления проектами.

## Быстрые ответы
- **Что такое расширенный атрибут?**  
  Пользовательское поле (например, Возраст, Уровень навыков), которое хранит дополнительные данные о ресурсах или задачах.  
- **Какой API его создает?**  
  Aspose.Tasks for Java предоставляет класс `ExtendedAttributeDefinition` для определения и управления пользовательскими атрибутами.  
- **Нужна ли лицензия?**  
  Временная оценочная лицензия подходит для разработки; для продакшн‑развертываний требуется полная лицензия.  
- **Можно ли хранить числа?**  
  Да – используйте `setNumericValue(BigDecimal)`, чтобы задать точные десятичные значения.  
- **Как сохранить изменения?**  
  Вызовите `project.save("output.xml", SaveFileFormat.Xml)`, чтобы записать обновлённый проект в формате XML.

## Что такое пользовательский атрибут?
**Пользовательский атрибут** (также известный как расширенный атрибут) — это дополнительный столбец, который можно добавить к ресурсам или задачам в Microsoft Project. Он позволяет фиксировать данные, не покрытые встроенными полями, такие как возраст сотрудника, уровень сертификации или любой бизнес‑специфический показатель.

## Зачем создавать расширенный атрибут в Java?
Создание расширенного атрибута в Java позволяет программно обогащать данные проекта, обеспечивая согласованность файлов и автоматизируя отчётность. Определив атрибут один раз, вы можете применять его к любому количеству ресурсов или задач без ручного ввода, экономя время и снижая количество ошибок.

- **Адаптировать данные под вашу организацию** – храните любые важные метрики без ручных обходных путей в Excel.  
- **Обеспечить более богатую отчётность** – запрашивайте пользовательское поле позже для панелей мониторинга или аналитики.  
- **Поддерживать согласованность** – программно применяйте одно и то же определение во множестве проектов, устраняя человеческие ошибки.  
- **Тестировано на производительность** – Aspose.Tasks обрабатывает проекты с до 10 000 задач и 5 000 ресурсов без полной загрузки файла в память, согласно тестам продукта.

## Требования
Перед началом убедитесь, что у вас есть:

1. **Java Development Kit** – установлен JDK 8 или новее.  
2. **Aspose.Tasks for Java** – скачайте последнюю версию [здесь](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA или любая совместимая среда разработки Java.  

## Как создать расширенный атрибут в Java?
Загрузите проект, определите атрибут, привяжите его к ресурсу и сохраните файл – всё в нескольких простых шагах. Ниже каждый шаг разбит на краткое объяснение и место, где будет ваш реальный код.

### Пошаговое руководство

#### Импорт пакетов
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` и связанные классы находятся в пространстве имён `com.aspose.tasks`. Импортируйте их в начале вашего Java‑файла.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### Шаг 1: Определить каталог данных
`Paths` — утилитный класс, предоставляющий методы получения пути в файловой системе независимо от платформы.

```java
String dataDir = "Your Data Directory";
```

#### Шаг 2: Загрузить файл Microsoft Project
`Project` представляет файл Microsoft Project в памяти, позволяя читать и записывать его содержимое.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Шаг 3: Определить пользовательский атрибут
`ExtendedAttributeDefinition` задаёт схему нового пользовательского поля, которое может быть привязано к ресурсам или задачам.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Шаг 4: Установить числовое значение в Java
`ExtendedAttributeResource` хранит значение пользовательского атрибута для конкретного экземпляра ресурса.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Шаг 5: Добавить ресурс и прикрепить пользовательский атрибут
`Resource` моделирует ресурс проекта, такой как человек, оборудование или материал.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Шаг 6: Сохранить проект в формате XML
`SaveFileFormat` перечисляет поддерживаемые форматы вывода при сохранении проекта, включая XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Шаг 7: Показать результат
`System.out.println` выводит строку текста в стандартный консольный вывод.

```java
System.out.println("Process completed Successfully");
```

## Распространённые ошибки и советы
- **Конфликты идентификаторов атрибутов:** Всегда вызывайте `project.getExtendedAttributes().getById(id)` перед созданием нового определения, чтобы избежать дублирования идентификаторов.  
- **Обработка точности:** Предпочитайте `BigDecimal` вместо `float`/`double` для точных числовых значений; это предотвращает ошибки округления в отчётах.  
- **Надёжность пути к файлу:** Используйте `Paths.get(...).toAbsolutePath()` или настройте рабочий каталог IDE, чтобы избежать `FileNotFoundException`.  

## Часто задаваемые вопросы

**В: Можно ли создавать пользовательские атрибуты и для задач, и для ресурсов?**  
О: Да – используйте `ExtendedAttributeTask` вместо `ExtendedAttributeResource` при определении схемы атрибута.

**В: Можно ли добавить несколько пользовательских атрибутов одновременно?**  
О: Абсолютно. Создайте отдельные объекты `ExtendedAttributeDefinition` для каждого атрибута и привяжите их к нужным ресурсам или задачам.

**В: В каких форматах можно сохранять проект?**  
О: Aspose.Tasks поддерживает XML, MPP, PDF, HTML и более 30 дополнительных форматов. В этом примере использовался `SaveFileFormat.Xml`.

**В: Нужна ли лицензия для сборок разработки?**  
О: Временная оценочная лицензия достаточна для тестирования. Для любого продакшн‑развёртывания требуется полная коммерческая лицензия.

**В: Как позже прочитать значения пользовательского атрибута?**  
О: Вызовите `resource.getExtendedAttributes()` и пройдитесь по коллекции; получайте сохранённое значение с помощью `getNumericValue()` или `getTextValue()`.

---

**Последнее обновление:** 2026-06-10  
**Тестировано с:** Aspose.Tasks for Java 24.12  
**Автор:** Aspose

## Связанные руководства

- [Как создать ресурсы – Управление ресурсами с Aspose.Tasks для Java](/tasks/java/resource-management/)
- [Создать пользовательское поле Aspose – Работа с расширенными атрибутами](/tasks/java/project-management/extended-attributes/)
- [Как создать проект – Установить новые атрибуты задач с Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}