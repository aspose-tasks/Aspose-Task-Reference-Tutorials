---
title: Сохранить как CSV, текст и шаблон в Aspose.Tasks
linktitle: Сохранить как CSV, текст и шаблон в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как сохранять файлы Microsoft Project в форматах CSV, Text и Template с помощью Aspose.Tasks для Java.
type: docs
weight: 16
url: /ru/java/project-file-operations/save-csv-text-template/
---
## Введение
В этом уроке мы рассмотрим, как сохранять файлы проекта в различных форматах, таких как CSV, текст и шаблон, с помощью Aspose.Tasks для Java. Aspose.Tasks — это мощная библиотека Java, которая позволяет разработчикам работать с файлами Microsoft Project без необходимости установки Microsoft Project.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1. В вашей системе установлен Java Development Kit (JDK).
2.  Библиотека Aspose.Tasks for Java загружена и настроена в вашем Java-проекте. Вы можете скачать его с[здесь](https://releases.aspose.com/tasks/java/).
3. Базовые знания языка программирования Java.

## Импортировать пакеты
Сначала вам необходимо импортировать необходимые пакеты в ваш Java-файл:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Сохранить проект как CSV
Давайте разберем шаги по сохранению проекта в формате CSV:
### Шаг 1. Загрузите проект
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Шаг 2. Сохраните в формате CSV.
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Сохранить проект как текст
Вот как вы можете сохранить проект как текст:
### Шаг 1. Загрузите проект
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Шаг 2. Сохранить как текст
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Сохранить проект как шаблон
Сохранение проекта в качестве шаблона включает в себя следующие шаги:
### Шаг 1. Загрузите проект
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Шаг 2. Установите параметры шаблона
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Шаг 3. Сохранить как шаблон.
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Заключение
В этом уроке мы узнали, как сохранять файлы Microsoft Project в формате CSV, текста и шаблона с помощью Aspose.Tasks для Java. С помощью этих простых шагов вы сможете эффективно управлять файлами проекта в различных форматах, повышая свою продуктивность как разработчика Java.
## Часто задаваемые вопросы
### Вопрос: Может ли Aspose.Tasks for Java обрабатывать сложные файлы проектов?
А: Абсолютно! Aspose.Tasks для Java позволяет легко обрабатывать проекты различной сложности, обеспечивая полную поддержку форматов файлов Microsoft Project.
### Вопрос: Доступна ли пробная версия Aspose.Tasks для Java?
 О: Да, вы можете получить бесплатную пробную версию Aspose.Tasks для Java на сайте[здесь](https://releases.aspose.com/).
### Вопрос: Где я могу найти поддержку Aspose.Tasks для Java?
 О: Вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для любой помощи или вопросов, касающихся Aspose.Tasks для Java.
### Вопрос: Могу ли я приобрести временную лицензию на Aspose.Tasks для Java?
 О: Да, вы можете приобрести временную лицензию на сайте[здесь](https://purchase.aspose.com/temporary-license/), позволяющий оценить весь потенциал библиотеки.
### Вопрос: Совместим ли Aspose.Tasks для Java с различными операционными системами?
О: Да, Aspose.Tasks для Java совместим с различными операционными системами, включая Windows, macOS и Linux.