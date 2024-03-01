---
title: Запишите обновленные данные ресурсов в Aspose.Tasks
linktitle: Запишите обновленные данные ресурсов в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как легко обновлять данные ресурсов в файлах MS Project с помощью Aspose.Tasks для Java.
type: docs
weight: 21
url: /ru/java/resource-management/write-updated-resource-data/
---
## Введение
В этом руководстве мы покажем вам, как обновить данные ресурсов Microsoft Project с помощью Aspose.Tasks для Java. Aspose.Tasks — это мощный Java API, который позволяет вам манипулировать файлами Microsoft Project, не требуя установки Microsoft Project в вашей системе.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1. В вашей системе установлен Java Development Kit (JDK).
2.  Aspose.Tasks для библиотеки Java. Вы можете скачать его с[здесь](https://releases.aspose.com/tasks/java/).
3. Базовые знания Java-программирования.

## Импортировать пакеты

Во-первых, вам необходимо импортировать необходимые пакеты для работы с Aspose.Tasks в ваш Java-код. Добавьте в файл Java следующие операторы импорта:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Шаг 1. Настройте каталог данных

Определите каталог, в котором расположены ваши файлы данных:

```java
String dataDir = "Your Data Directory";
```

## Шаг 2. Укажите входные и выходные файлы

Определите пути для входного файла MS Project и результирующего обновленного файла:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Тестовый файл с одним rsc для обновления
String resultFile = dataDir + "OutputMPP.mpp"; // Файл для написания тестового проекта
```

## Шаг 3. Загрузите проект

 Загрузите файл MS Project в`Project` объект:

```java
Project project = new Project(file);
```

## Шаг 4. Добавьте ресурс и установите атрибуты

Добавьте в проект новый ресурс и установите его атрибуты, такие как стандартная ставка, ставка за сверхурочную работу и группа:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Шаг 5: Сохраните проект

Сохраните обновленный проект с измененными данными ресурса:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Заключение

В этом руководстве мы продемонстрировали, как обновить данные ресурсов MS Project с помощью Aspose.Tasks для Java. Выполнив эти шаги, вы сможете эффективно программно манипулировать информацией о ресурсах в файлах MS Project.

## Часто задаваемые вопросы

### Вопрос 1. Могу ли я обновить несколько ресурсов в одном проекте с помощью Aspose.Tasks для Java?

О1: Да, вы можете обновить несколько ресурсов, просматривая их и соответствующим образом устанавливая их атрибуты.

### Вопрос 2: Поддерживает ли Aspose.Tasks другие форматы файлов, кроме MS Project?

О2: Да, Aspose.Tasks поддерживает различные форматы файлов, включая XML, MPP и другие.

### Вопрос 3. Совместим ли Aspose.Tasks с различными версиями Java?

О3: Aspose.Tasks совместим с Java версии 6 и выше.

### Вопрос 4: Могу ли я выполнять другие операции с файлами MS Project с помощью Aspose.Tasks?

О4: Да, вы можете выполнять широкий спектр операций, таких как чтение, запись и управление задачами, ресурсами и календарями.

### Вопрос 5: Где я могу найти дополнительную помощь или поддержку для Aspose.Tasks?

 A5: Вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для любой помощи или вопросов.
