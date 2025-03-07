---
title: Остановить и возобновить назначение ресурсов в Aspose.Tasks
linktitle: Остановить и возобновить назначение ресурсов в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как эффективно управлять назначениями ресурсов в Aspose.Tasks для Java, с помощью этого пошагового руководства.
weight: 23
url: /ru/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Остановить и возобновить назначение ресурсов в Aspose.Tasks

## Введение
В этом уроке мы узнаем, как остановить и возобновить назначение ресурсов с помощью Aspose.Tasks для Java. Aspose.Tasks — это мощный Java API, который позволяет разработчикам работать с файлами Microsoft Project без необходимости установки Microsoft Project в их системах. Мы разобьем процесс на управляемые этапы, чтобы вам было легко следовать за ним.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлен Java Development Kit (JDK).
-  Скачана библиотека Aspose.Tasks для Java. Вы можете скачать его с[здесь](https://releases.aspose.com/tasks/java/).
- Базовое понимание программирования на Java.
## Импортировать пакеты
Для начала давайте импортируем необходимые пакеты в наш Java-проект:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Шаг 1. Загрузите файл проекта
```java
// Путь к каталогу документов.
String dataDir = "Your Data Directory";
// Загрузите файл проекта
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 На этом этапе мы загружаем файл проекта в`Project` объект, используя путь к файлу.
## Шаг 2. Повторение назначений ресурсов
```java
// Определить минимальную дату
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Перебирать назначения ресурсов
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Здесь мы определяем минимальную дату и начинаем перебирать каждое назначение ресурсов в проекте.
## Шаг 3. Проверьте даты остановки и возобновления
```java
    // Проверить дату остановки
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Проверить дату возобновления
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
На этом этапе мы проверяем, находятся ли даты остановки и возобновления каждого назначения ресурсов перед минимальной датой. Если это так, мы печатаем «NA», в противном случае мы печатаем соответствующие даты.
## Заключение
В этом уроке мы узнали, как остановить и возобновить назначение ресурсов в Aspose.Tasks для Java. Следуя предоставленным инструкциям, вы сможете легко реализовать эту функциональность в своих проектах Java.

## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Tasks без установленного Microsoft Project?
Да, Aspose.Tasks позволяет вам работать с файлами Microsoft Project без необходимости установки Microsoft Project в вашей системе.
### Где я могу найти дополнительную документацию?
 Вы можете найти подробную документацию[здесь](https://reference.aspose.com/tasks/java/).
### Доступна ли бесплатная пробная версия?
 Да, вы можете получить бесплатную пробную версию[здесь](https://releases.aspose.com/).
### Как я могу получить поддержку, если у меня возникнут какие-либо проблемы?
Вы можете получить поддержку сообщества[здесь](https://forum.aspose.com/c/tasks/15).
### Могу ли я приобрести временную лицензию?
 Да, вы можете приобрести временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
