---
date: 2026-06-10
description: Узнайте, как читать rate и как записывать rate scale для resource assignments
  с использованием Aspose.Tasks for Java. Поддерживает material resources, multiple
  formats и large projects.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Чтение и запись Rate Scale для Resource Assignments в Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Как читать Rate Scale и записывать Rate Scale для Resource Assignments в Aspose.Tasks
url: /ru/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как читать шкалу ставок и записывать шкалу ставок для назначений ресурсов в Aspose.Tasks

В этом руководстве вы узнаете **как читать шкалу ставок** и настраивать её для назначений ресурсов с помощью Aspose.Tasks для Java. Независимо от того, создаёте ли вы планировщик, инструмент отчётности или просто хотите автоматизировать обновления проекта, освоение управления шкалой ставок даёт вам точный контроль над материалами и рабочими ресурсами.

## Быстрые ответы
`ResourceAssignment` связывает задачу с ресурсом и хранит данные, специфичные для назначения.  
`Asn` содержит константы полей назначения, включая `RATE_SCALE`.  
`RateScaleType` перечисляет возможные единицы времени для шкалы ставок.  

- **Какой основной класс для работы со шкалой ставок?** `ResourceAssignment` со свойством `Asn.RATE_SCALE`.  
- **Какое перечисление определяет варианты шкалы?** `RateScaleType` (Day, Week, Month и т.д.).  
- **Нужна ли лицензия для запуска примера?** Бесплатная оценочная лицензия подходит для тестирования; для продакшна требуется коммерческая лицензия.  
- **Можно ли изменить шкалу после сохранения?** Да — перезагрузите проект и измените `Asn.RATE_SCALE`, как показано.  
- **Поддерживаемые IDE?** Любая Java‑IDE (IntelliJ IDEA, Eclipse, NetBeans) может компилировать код.

## Как прочитать шкалу ставок для назначений ресурсов?

Загрузите проект, найдите нужный `ResourceAssignment` и вызовите `getRateScale()` — он возвращает значение `RateScaleType`, которое указывает, применяется ли ставка за день, неделю, месяц или другую единицу. Ответ получаем мгновенно, используя всего два вызова API, что делает этот подход идеальным для скриптов аудита или отображения в UI.

## Как записать шкалу ставок для назначений ресурсов?

Создайте или получите объект `ResourceAssignment`, установите его свойство `Asn.RATE_SCALE` в нужный `RateScaleType` (например, `RateScaleType.Week`) и сохраните проект. Это единственное изменение свойства автоматически обновит расчёты стоимости и сохранится во всех поддерживаемых форматах файлов. После установки шкалы может потребоваться скорректировать стандартную ставку ресурса или ставку за сверхурочную работу, чтобы новые расчёты оставались точными.

## Что такое шкала ставок?

Шкала ставок определяет единицу времени (день, неделя, месяц и т.д.), к которой применяется стоимость ресурса. Изменяя шкалу, вы можете точно моделировать потребление материалов или трудозатраты. Например, установка шкалы в Week означает, что стоимость интерпретируется как стоимость за неделю, а общая стоимость задачи рассчитывается исходя из количества недель, в течение которых ресурс назначен.

## Зачем читать и записывать шкалу ставок?

Чтение текущей шкалы помогает проводить аудит существующих расписаний, а запись новой шкалы позволяет согласовать ресурсы с политиками биллинга или потребления проекта. Это особенно полезно при **определении стоимости материальных ресурсов** или когда необходимо **установить шкалу** для нестандартных рабочих календарей.

## Предварительные требования
1. **Java Development Environment** – установлен JDK 8 или выше.  
2. **Aspose.Tasks for Java Library** – скачайте и установите библиотеку из [here](https://releases.aspose.com/tasks/java/).

## Импорт пакетов
Класс `ResourceAssignment` представляет связь между задачей и ресурсом, а `RateScaleType` перечисляет возможные единицы времени для ставки. Импортируйте необходимые классы Aspose.Tasks перед началом кодирования.  

`Project` — основной объект, который загружает и сохраняет файлы Microsoft Project.  
`Resource` определяет ресурс проекта, такой как работа или материал.  
`ResourceType` перечисление указывает, является ли ресурс рабочим или материальным.  
`Task` представляет рабочий элемент в расписании проекта.  
`SaveFileFormat` перечисление задаёт формат вывода при сохранении проекта.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Шаг 1: Настройте ваш Java‑проект
Создайте проект Maven или Gradle и добавьте JAR‑файл Aspose.Tasks в classpath. Этот шаг гарантирует, что компилятор найдёт импортированные классы.

## Шаг 2: Загрузите файл проекта
Загрузите существующий файл Microsoft Project, с которым хотите работать.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Шаг 3: Добавьте задачу
Создайте новую задачу, которая позже получит назначения ресурсов.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Шаг 4: Определите ресурсы
Здесь мы **определяем материальный ресурс** и обычный рабочий ресурс. Обратите внимание на использование `ResourceType.Material` для ресурса типа материал.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Шаг 5: Назначьте ресурсы задаче
Теперь мы **назначаем ресурсы задаче** и указываем **как установить шкалу**, используя `RateScaleType.Week`. Это демонстрирует как чтение, так и запись шкалы ставок.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Шаг 6: Сохраните проект
Сохраните изменения в новый файл, чтобы позже можно было проверить сохранённую шкалу ставок.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Шаг 7: Получите назначения ресурсов
Перезагрузите сохранённый проект и **прочитайте шкалу ставок**, чтобы убедиться, что она была записана корректно.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Распространённые ошибки и советы
- **Несоответствие UID** – При получении назначений по UID убедитесь, что значения UID совпадают с теми, что были заданы при создании.  
- **Неправильный тип ресурса** – Использование `ResourceType.Material` для рабочего ресурса приведёт к некорректным расчётам ставок.  
- **Формат сохранения** – Всегда сохраняйте с помощью `SaveFileFormat.Mpp` (или другого поддерживаемого формата), чтобы сохранить пользовательские поля, такие как шкала ставок.  
- **Большие проекты** – Aspose.Tasks может обрабатывать файлы с **500+ страницами** без полной загрузки документа в память благодаря потоковой архитектуре.

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Tasks для Java в любой Java IDE?**  
A: Да, Aspose.Tasks для Java совместим со всеми популярными Java IDE, включая IntelliJ IDEA, Eclipse и NetBeans.

**Q: Поддерживает ли Aspose.Tasks другие форматы файлов, кроме MPP?**  
A: Да, Aspose.Tasks поддерживает различные форматы файлов, включая MPP, XML и HTML.

**Q: Подходит ли Aspose.Tasks для корпоративного управления проектами?**  
A: Абсолютно, Aspose.Tasks предлагает полный набор функций для управления проектами любого масштаба, что делает его подходящим для корпоративного уровня.

**Q: Можно ли дальше настраивать назначения ресурсов, помимо шкалы ставок?**  
A: Да, Aspose.Tasks предоставляет широкие возможности для настройки назначений ресурсов, включая корректировку стоимости, работы и длительности.

**Q: Есть ли сообщество или форум поддержки Aspose.Tasks?**  
A: Да, вы можете получить поддержку и пообщаться с другими пользователями на форуме Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Связанные руководства

- [Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [How to Modify Assignments – Read Shared Resources with Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [How to Add Notes to Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}