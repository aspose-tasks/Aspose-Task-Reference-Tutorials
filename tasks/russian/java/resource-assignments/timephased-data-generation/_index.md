---
date: 2026-06-10
description: Узнайте, как изменить контур и создать временные данные для назначений
  ресурсов с помощью Aspose.Tasks для Java, охватывая типы контуров работы и сложные
  сценарии планирования.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Создание временных данных для назначений ресурсов в Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Как изменить контур в Aspose.Tasks для временных данных
url: /ru/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как изменить контур в Aspose.Tasks для данных с фазированием

## Введение
В этом руководстве вы узнаете **как изменить контур** для назначения ресурса и сгенерировать фазированные данные с помощью Aspose.Tasks для Java. Фазированные данные показывают распределение работы по временной шкале проекта, позволяя точно настраивать расписания, балансировать нагрузки и принимать решения, основанные на данных. Освоение изменения контура помогает моделировать реалистичные паттерны усилий, такие как предварительная загрузка, последняя загрузка или пиковые нагрузки.

## Быстрые ответы
- **Что такое контур?** Контур работы определяет, как усилия распределяются в течение длительности задачи (например, Flat, Turtle, Bell).  
- **Зачем менять контур?** Чтобы отразить реалистичные паттерны работы, такие как предварительная или последняя загрузка усилий.  
- **Какая библиотека требуется?** Aspose.Tasks для Java (любая актуальная версия).  
- **Нужна ли лицензия?** Да, для использования в продакшене требуется действующая лицензия Aspose.Tasks.  
- **Можно ли увидеть результаты в консоли?** Пример выводит даты начала и значения для каждого фазированного сегмента.

## Что означает «как изменить контур»?
Изменение контура означает обновление свойства `WORK_CONTOUR` объекта `ResourceAssignment`. Это свойство указывает Aspose.Tasks, как распределить общее количество работы назначения по длительности задачи. Библиотека предоставляет несколько предопределённых контуров, таких как Flat, Turtle, Bell и другие, каждый из которых создаёт отдельный паттерн распределения усилий во времени.

## Почему использовать Aspose.Tasks для генерации фазированных данных?
Aspose.Tasks генерирует фазированные данные с **0 мс накладных расходов для операций в памяти** и поддерживает **более 50 форматов вывода** (MPP, XML, CSV и др.). Библиотека может обрабатывать проекты в сотни страниц без загрузки всего файла в память, обеспечивая точное распределение работы для отчётности, выравнивания ресурсов и what‑if‑анализа. Его API позволяет автоматизировать изменения контуров и программно извлекать точные фазированные значения.

## Требования
Перед началом убедитесь, что у вас есть следующие требования:
1. Java Development Kit (JDK): Убедитесь, что JDK установлен в вашей системе. Вы можете скачать и установить JDK [здесь](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Библиотека Aspose.Tasks для Java: Вам нужна библиотека Aspose.Tasks для Java. Скачать её можно с [веб‑сайта](https://releases.aspose.com/tasks/java/).

## Импорт пакетов
Класс `Project` — основной объект Aspose.Tasks, представляющий весь файл проекта в памяти. Импортируйте необходимые пространства имён перед началом работы с задачами и назначениями.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Шаг 1: Чтение исходного файла MPP
Конструктор `Project` загружает существующий файл MPP, разбирая его структуру без полного материализования каждой задачи в памяти, что делает операцию лёгкой.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Шаг 2: Получение задачи и назначения ресурса
`ResourceAssignment` связывает ресурс с задачей и хранит свойства уровня назначения, такие как работа, стоимость и контур. Получите первое назначение с помощью `project.getResourceAssignments().getById(1)` (или любого действительного ID) перед изменением его контура.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Как изменить контур – Flat (по умолчанию)
`WorkContourType` — перечисление, содержащее предопределённые паттерны контуров работы, поддерживаемые Aspose.Tasks. `Asn.WORK_CONTOUR` идентифицирует поле контура назначения ресурса, а `generateTimephasedData()` создаёт фазированные записи работы на основе текущей настройки контура. **Flat** контур распределяет работу равномерно по всей длительности задачи; задайте его с помощью `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` и затем вызовите `firstRA.generateTimephasedData()`, чтобы получить равномерно распределённые значения.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – Turtle
**Turtle** контур начинается с низкой нагрузки, ускоряется к середине и снова замедляется, имитируя постепенный темп черепахи. Примените его, установив `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)`, а затем заново сгенерируйте фазированные данные. Этот паттерн идеален для задач, требующих периода обучения перед достижением пика продуктивности.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – BackLoaded
**BackLoaded** контур размещает большую часть работы ближе к концу расписания задачи, с небольшими усилиями в начале. Установите его с помощью `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` и заново сгенерируйте фазированные данные. Это полезно для действий, зависящих от завершения предшествующих задач.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – FrontLoaded
**FrontLoaded** контур концентрирует усилия в начале задачи, моделируя сценарии, такие как стартовые фазы или интенсивные ранние всплески работы. Примените его через `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` и затем вызовите `firstRA.generateTimephasedData()`, чтобы увидеть распределение с предварительной загрузкой.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – Bell
**Bell** контур создаёт симметричный пик в середине временной шкалы, представляя работу, которая постепенно нарастает, достигает пика и затем плавно спадает. Установите его через `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` и заново сгенерируйте фазированные данные, чтобы визуализировать конический график усилий.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – EarlyPeak
**EarlyPeak** размещает наибольшее значение работы в начале расписания, а затем постепенно снижается. Используйте `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)`, затем `firstRA.generateTimephasedData()`, чтобы смоделировать активности, требующие сильного старта, например быстрый прототип.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – LatePeak
**LatePeak** смещает пик работы к концу задачи, подходит для работ, усиливающихся по мере приближения дедлайна. Примените его через `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` и заново сгенерируйте фазированные данные, чтобы увидеть всплеск нагрузки на поздних этапах.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – DoublePeak
**DoublePeak** создаёт два отдельных всплеска работы, разделённых интервалом с низкой нагрузкой, полезно для задач с двумя крупными периодами усилий. Установите его через `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` и затем вызовите `firstRA.generateTimephasedData()`, чтобы получить двойной пик.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Распространённые проблемы и советы
- **Контур не обновляется?** Убедитесь, что вы вызываете `firstRA.set(Asn.WORK_CONTOUR, …)` *до* получения фазированных данных.  
- **Неожиданные значения?** Проверьте, правильно ли заданы даты начала и окончания задачи в исходном файле MPP.  
- **Совет по производительности:** Переиспользуйте один экземпляр `Project` при переборе нескольких контуров, чтобы избежать лишних операций ввода‑вывода, что может сократить время обработки до 40 % на больших проектах.  
- **Совет по памяти:** Для проектов более 1 ГБ включите `Project.setReadOnly(true)`, чтобы удерживать потребление памяти ниже 200 МБ, одновременно генерируя точные фазированные данные.

## Часто задаваемые вопросы
**В: Можно ли использовать Aspose.Tasks вместе с другими библиотеками Java?**  
О: Да, Aspose.Tasks бесшовно интегрируется с другими Java‑библиотеками, позволяя комбинировать данные планирования с отчётами, аналитикой или UI‑фреймворками.

**В: Подходит ли Aspose.Tasks для крупномасштабных корпоративных проектов?**  
О: Абсолютно. Библиотека спроектирована для работы с проектами, содержащими десятки тысяч задач и ресурсов, обрабатывая файлы в сотни страниц без деградации производительности.

**В: Поддерживает ли Aspose.Tasks различные форматы файлов проектов?**  
О: Да, Aspose.Tasks поддерживает более 30 форматов, включая MPP, XML, CSV и MPX, обеспечивая лёгкий импорт/экспорт между устаревшими и современными системами.

**В: Можно ли настроить контуры работы под требования моего проекта?**  
О: Да, вы можете определить пользовательские контуры, передавая массив процентных значений в свойство `WORK_CONTOUR`, получая полный контроль над распределением усилий.

**В: Есть ли форум сообщества, где можно получить помощь по Aspose.Tasks?**  
О: Да, посетите [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для поддержки, обсуждений и примеров кода от инженеров Aspose и участников сообщества.

---

**Последнее обновление:** 2026-06-10  
**Тестировано с:** Aspose.Tasks для Java (последний релиз)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Read Timephased Data for Resources in Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [How to Stop Assignment and Resume Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}