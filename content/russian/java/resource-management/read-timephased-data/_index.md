---
title: Чтение повременных данных для ресурсов в Aspose.Tasks
linktitle: Чтение повременных данных для ресурсов в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как извлекать повременные данные из ресурсов MS Project с помощью Aspose.Tasks для Java. Пошаговое руководство.
type: docs
weight: 15
url: /ru/java/resource-management/read-timephased-data/
---
## Введение
В этом руководстве мы покажем вам процесс чтения повременных данных для ресурсов MS Project с помощью Aspose.Tasks для Java. Эта библиотека предоставляет мощные функции для программного управления файлами Microsoft Project.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1.  Java Development Kit (JDK): убедитесь, что в вашей системе установлен JDK. Вы можете скачать его с сайта[Веб-сайт](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) и следуйте инструкциям по установке.
2.  Библиотека Aspose.Tasks для Java: загрузите библиотеку Aspose.Tasks для Java с сайта[страница загрузки](https://releases.aspose.com/tasks/java/) и следуйте инструкциям по установке, приведенным в документации.

## Импортировать пакеты
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Шаг 1. Настройте каталог данных.
Сначала определите каталог, в котором находится ваш файл MS Project.
```java
String dataDir = "Your Data Directory";
```
## Шаг 2. Прочтите файл шаблона проекта MS.
Укажите имя файла шаблона MS Project.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Шаг 3. Считайте входной файл как проект
Прочитайте входной файл с помощью Aspose.Tasks и загрузите его как объект Project.
```java
Project project = new Project(dataDir + fileName);
```
## Шаг 4. Получите ресурс по идентификатору
Получите нужный ресурс из проекта по его уникальному идентификатору (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Шаг 5. Печать повременных данных для работы с ресурсами
Распечатайте повременные данные для работы ресурса.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Шаг 6. Распечатайте повременные данные о стоимости ресурсов
Распечатайте повременные данные о стоимости ресурсов.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Заключение
В этом уроке мы научились читать повременные данные для ресурсов MS Project с помощью Aspose.Tasks для Java. Следуя этим шагам, вы сможете эффективно извлекать ценную информацию из файлов проекта программными средствами.
## Часто задаваемые вопросы
### Может ли Aspose.Tasks обрабатывать файлы проектов других типов, кроме Microsoft Project?
Да, Aspose.Tasks поддерживает различные форматы файлов, включая MPP, XML и CSV.
### Совместим ли Aspose.Tasks с различными средами разработки Java?
Да, Aspose.Tasks совместим со всеми основными IDE и платформами Java.
### Могу ли я манипулировать данными проекта с помощью Aspose.Tasks?
Безусловно, Aspose.Tasks предоставляет обширные API для создания, изменения и анализа данных проекта.
### Подходит ли Aspose.Tasks для проектов корпоративного уровня?
Да, Aspose.Tasks широко используется в корпоративных средах благодаря своей надежности и масштабируемости.
### Где я могу найти поддержку, если у меня возникнут проблемы при использовании Aspose.Tasks?
 Вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) за помощь со стороны сообщества и команды поддержки.