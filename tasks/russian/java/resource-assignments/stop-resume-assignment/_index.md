---
date: 2026-07-14
description: Узнайте, как остановить назначение ресурсов в Java, управлять назначениями
  ресурсов и просматривать примеры с использованием Aspose.Tasks for Java в этом пошаговом
  руководстве.
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Остановка и возобновление назначений ресурсов в Aspose.Tasks
og_description: Остановка назначения ресурсов в Java с Aspose.Tasks. Этот учебник
  показывает, как приостанавливать и возобновлять назначения, работать с датами и
  интегрировать API без Microsoft Project.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Остановка назначения ресурсов в Java – руководство Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Как остановить назначение ресурсов в Java – возобновление с Aspose.Tasks
url: /ru/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как остановить назначение ресурса Java – возобновление с Aspose.Tasks

## Введение
В этом руководстве вы узнаете **how to stop resource assignment java** и позже возобновите его, используя Aspose.Tasks для Java. Aspose.Tasks — это мощный Java API, позволяющий читать и записывать файлы Microsoft Project, управлять расписаниями и контролировать назначения ресурсов — без необходимости установки Microsoft Project. Мы пройдем каждый шаг, объясним, почему важна каждая строка, и поделимся практическими советами, которые вы можете применить к реальным планам проектов.

## Быстрые ответы
- **Что означает «stop assignment»?** Он помечает назначение ресурса как временно неактивное с определённой даты остановки.  
- **Могу ли я позже возобновить то же назначение?** Да, установив дату возобновления для того же назначения.  
- **Нужен ли Microsoft Project для использования этого API?** Нет, Aspose.Tasks работает независимо от Microsoft Project.  
- **Какая версия Java требуется?** Рекомендуется Java 8 или новее.  
- **Где можно скачать библиотеку?** На официальной странице загрузки Aspose.Tasks Java.

## Как остановить назначение ресурса в Java?
Загрузите ваш проект, найдите целевой `ResourceAssignment`, установите дату `STOP`, при необходимости задайте дату `RESUME`, а затем сохраните файл. Эта последовательность приостанавливает работу на указанный период и автоматически возобновляет её после даты возобновления, предоставляя точный контроль над календарями ресурсов без ручного редактирования файлов.

## Что означает «how to stop assignment» в контексте Aspose.Tasks?
Остановка назначения сообщает планировщику игнорировать работу, назначенную ресурсу после **stop date**, до **resume date** (если указана). Это полезно для учёта отпусков, простоя оборудования или любого периода, когда ресурс не должен считаться активным.

## Почему стоит использовать Aspose.Tasks для управления назначениями ресурсов?
Aspose.Tasks позволяет программно управлять датами назначений, устраняя ручные правки и снижая риск ошибок. Он поддерживает **более 50 форматов ввода и вывода** и может обрабатывать проекты с **до 10 000 задач**, при этом потребление памяти остаётся ниже 200 МБ, поскольку данные передаются потоково, а не загружаются полностью в память. API работает на любой ОС, поддерживающей Java, обеспечивая кросс‑платформенную гибкость.

## Предварительные требования
- Установлен Java Development Kit (JDK) версии 8 или новее.  
- Скачана библиотека Aspose.Tasks for Java. Вы можете загрузить её [здесь](https://releases.aspose.com/tasks/java/).  
- Базовые знания программирования на Java.  

## Импорт пакетов
Классы `Project`, `ResourceAssignment` и `Asn` находятся в пространстве имён `com.aspose.tasks`. Импортируйте их в начале вашего исходного файла:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Шаг 1: Загрузка файла проекта
Класс `Project` — это объект верхнего уровня Aspose.Tasks, представляющий в памяти один файл Microsoft Project. Создание экземпляра загружает файл и предоставляет доступ к задачам, ресурсам и назначениям.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## Шаг 2: Итерация по назначениям ресурсов
Объекты `ResourceAssignment` раскрывают все поля, связанные с назначениями. Мы задаём **minimum date**, чтобы отфильтровать фиктивные даты, а затем перебираем каждое назначение. Этот шаблон является стандартным *примером назначения ресурсов* для проверки или изменения.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## Шаг 3: Проверка дат STOP и RESUME
В этом блоке мы проверяем поля `STOP` и `RESUME` для каждого назначения. Если дата раньше нашего `minDate`, считаем её не установленной (`"NA"`); иначе выводим фактическую дату. Эта логика необходима для правильного **управления назначениями ресурсов**.

```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

## Распространённые проблемы и решения
- **Null dates** – `ra.get(Asn.STOP)` может вернуть `null`. Защититесь, добавив проверку на null перед вызовом `.before(minDate)`.  
- **Incorrect file path** – Убедитесь, что `dataDir` заканчивается разделителем пути (`/` или `\\`), соответствующим вашей ОС.  
- **Version mismatch** – Используйте последнюю версию Aspose.Tasks for Java, чтобы избежать отсутствия значений перечисления.

## Часто задаваемые вопросы

**Q: Как программно установить дату остановки для назначения?**  
A: Используйте `ra.set(Asn.STOP, yourDateObject);`, где `yourDateObject` — это `java.util.Date`.

**Q: Что происходит, если дата возобновления раньше даты остановки?**  
A: API не принуждает к хронологическому порядку; однако планировщик будет считать назначение активным только после более поздней из двух дат, поэтому вам следует самостоятельно проверять даты.

**Q: Можно ли отфильтровать назначения, оставив только те, у которых установлена дата остановки?**  
A: Да, пройдитесь по `prj.getResourceAssignments()` и проверьте `ra.get(Asn.STOP) != null`.

**Q: Можно ли удалить установленную дату остановки?**  
A: Установите дату остановки в `null` с помощью `ra.set(Asn.STOP, null);`, затем сохраните проект.

**Q: Поддерживает ли Aspose.Tasks другие поля, связанные с датами, такие как start, finish или actual start?**  
A: Конечно. Перечисление `Asn` предоставляет константы для всех полей назначения, например `Asn.START`, `Asn.FINISH` и т.д.

## Заключение
Следуя этим шагам, вы теперь знаете **how to stop resource assignment java**, можете проверять даты STOP/RESUME и при необходимости возобновлять назначение. Эта возможность позволяет более точно **управлять назначениями ресурсов**, особенно в сценариях, таких как отпуска ресурсов или простой оборудования. Не стесняйтесь расширять пример для обновления дат, генерации отчётов или интеграции с вашей собственной логикой планирования.

---

**Последнее обновление:** 2026-07-14  
**Тестировано с:** Aspose.Tasks for Java 24.12  
**Автор:** Aspose

## Связанные руководства

- [Создать назначения ресурсов в Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Как рассчитать отклонение стоимости и управлять затратами назначений с Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Как добавить заметки к назначениям ресурсов в Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}