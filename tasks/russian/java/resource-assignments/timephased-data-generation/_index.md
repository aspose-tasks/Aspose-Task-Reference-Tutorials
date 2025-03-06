---
title: Генерация повременных данных в Aspose.Tasks
linktitle: Генерация повременных данных для назначения ресурсов в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как генерировать повременные данные для назначения ресурсов с помощью Aspose.Tasks для Java. Повысьте эффективность управления проектами с помощью этого подробного руководства.
type: docs
weight: 24
url: /ru/java/resource-assignments/timephased-data-generation/
---
## Введение
В этом руководстве мы рассмотрим процесс генерации повременных данных для назначения ресурсов с помощью Aspose.Tasks для Java. Повременные данные дают ценную информацию о том, как ресурсы распределяются во времени в рамках проекта, помогая менеджерам проектов принимать обоснованные решения.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1.  Java Development Kit (JDK): убедитесь, что в вашей системе установлен JDK. Вы можете загрузить и установить JDK с сайта[здесь](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Библиотека Aspose.Tasks для Java: вам необходима библиотека Aspose.Tasks для Java. Вы можете скачать его с сайта[Веб-сайт](https://releases.aspose.com/tasks/java/).

## Импортировать пакеты
Для начала импортируем необходимые пакеты для работы с Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Шаг 1. Прочтите исходный файл MPP.
```java
// Путь к каталогу документов.
String dataDir = "Your Data Directory";
// Прочтите исходный файл MPP
Project project = new Project(dataDir + "project.mpp");
```
## Шаг 2. Получите назначение задач и ресурсов
```java
// Получите первое задание Проекта
Task task = project.getRootTask().getChildren().getById(1);
// Получите первое назначение ресурсов проекта.
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Шаг 3. Сгенерируйте повременные данные с плоским контуром
```java
// Плоский контур — контур по умолчанию.
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Шаг 4: Измените контур на черепаху
```java
// Изменить контур на Черепаху
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Шаг 5. Измените контур на BackLoaded
```java
// Изменить контур на BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Шаг 6. Измените Contour на FrontLoaded
```java
// Изменить контур на FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Шаг 7: Измените контур на колокольчик
```java
// Изменить контур на Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Шаг 8: Измените контур на EarlyPeak
```java
// Изменить контур на EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Шаг 9: измените контур на LatePeak
```java
// Изменить контур на LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Шаг 10: Измените контур на DoublePeak
```java
// Изменить контур на DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Заключение
В этом руководстве мы рассмотрели, как генерировать повременные данные для назначения ресурсов с помощью Aspose.Tasks для Java. Понимание различных контуров работы может помочь менеджерам проектов эффективно управлять распределением ресурсов и планированием в своих проектах.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Tasks с другими библиотеками Java?
Да, Aspose.Tasks можно интегрировать с другими библиотеками Java для расширения возможностей управления проектами.
### Подходит ли Aspose.Tasks для крупномасштабных корпоративных проектов?
Безусловно, Aspose.Tasks предназначен для реализации проектов любого размера, включая крупномасштабные корпоративные проекты.
### Обеспечивает ли Aspose.Tasks поддержку различных форматов файлов проекта?
Да, Aspose.Tasks поддерживает различные форматы файлов проектов, включая MPP, XML и MPX.
### Могу ли я настроить рабочие контуры в соответствии с требованиями моего проекта?
Да, Aspose.Tasks позволяет пользователям определять собственные контуры работы в соответствии с потребностями их конкретных проектов.
### Есть ли форум сообщества, где я могу получить помощь по Aspose.Tasks?
 Да, вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) за поддержку и обсуждения.