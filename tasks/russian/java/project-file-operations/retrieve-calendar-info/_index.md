---
title: Получить информацию о календаре проекта MS в Aspose.Tasks
linktitle: Получить информацию о календаре в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как получить информацию календаря MS Project с помощью Aspose.Tasks для Java. Пошаговое руководство по программному доступу к сведениям календаря.
weight: 14
url: /ru/java/project-file-operations/retrieve-calendar-info/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Получить информацию о календаре проекта MS в Aspose.Tasks

## Введение
В этом руководстве мы рассмотрим, как получить информацию календаря из файлов Microsoft Project с помощью библиотеки Aspose.Tasks для Java. Aspose.Tasks предоставляет мощные функции для управления данными проекта, включая доступ к данным календаря, таким как рабочие дни и часы.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
- Базовые знания Java-программирования.
- В вашей системе установлен Java Development Kit (JDK).
-  Aspose.Tasks для библиотеки Java. Вы можете скачать его с[здесь](https://releases.aspose.com/tasks/java/).
## Импортировать пакеты
Во-первых, вам необходимо импортировать необходимые пакеты в ваш Java-код, чтобы использовать функциональные возможности Aspose.Tasks.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Теперь давайте разобьем приведенный пример на несколько шагов для лучшего понимания.
## Шаг 1. Установите каталог данных
```java
String dataDir = "Your Data Directory";
```
 Заменять`"Your Data Directory"` с путем к каталогу файлов вашего проекта.
## Шаг 2: Определите единицы времени
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Эти константы представляют собой единицы времени в микросекундах.
## Шаг 3. Создайте экземпляр проекта
```java
Project project = new Project(dataDir + "project.mpp");
```
 Эта строка создает экземпляр`Project` класс, инициализируя его путем к файлу проекта (`project.mpp`).
## Шаг 4. Получение информации о календарях
```java
CalendarCollection alCals = project.getCalendars();
```
Здесь мы получаем коллекцию календарей, присутствующих в файле проекта.
## Шаг 5. Перебор календарей
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Информация о календаре
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Перебор дней недели
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Время в миллисекундах
            double time = ts / (OneHour); // Перевести в часы
            if (wd.getDayWorking()) {
                // Отображение рабочих дней и часов
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Этот цикл перебирает каждый календарь и печатает его UID, имя и рабочие дни с соответствующими рабочими часами.
## Шаг 6: Отображение сообщения о завершении
```java
System.out.println("Process completed Successfully");
```
Наконец, отображается сообщение, указывающее на завершение процесса.
## Заключение
В этом уроке мы узнали, как получить информацию календаря из файлов MS Project с помощью Aspose.Tasks для Java. Выполнив эти шаги, вы сможете эффективно получать доступ к данным проекта и манипулировать ими в своих приложениях Java.

## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks с другими языками программирования?
О: Да, Aspose.Tasks поддерживает множество платформ и языков программирования, включая .NET, C.++, Python и Java.
### Вопрос: Доступна ли бесплатная пробная версия Aspose.Tasks?
 О: Да, вы можете скачать бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).
### Вопрос: Как я могу получить поддержку Aspose.Tasks?
О: Вы можете получить поддержку на форуме сообщества Aspose.Tasks.[здесь](https://forum.aspose.com/c/tasks/15).
### Вопрос: Могу ли я приобрести временную лицензию для Aspose.Tasks?
 О: Да, временные лицензии доступны для приобретения.[здесь](https://purchase.aspose.com/temporary-license/).
### Вопрос: Где я могу найти подробную документацию по Aspose.Tasks?
 О: Вы можете обратиться к документации[здесь](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
