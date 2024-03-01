---
title: Шкала скорости чтения и записи для назначения ресурсов в Aspose.Tasks
linktitle: Шкала скорости чтения и записи для назначения ресурсов в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Из этого подробного руководства вы узнаете, как эффективно управлять масштабированием скорости назначения ресурсов в Aspose.Tasks для Java.
type: docs
weight: 20
url: /ru/java/resource-assignments/read-write-rate-scale/
---
## Введение
В этом руководстве мы углубимся в управление шкалой ставок назначения ресурсов с помощью Aspose.Tasks для Java, надежной библиотеки для программной работы с файлами Microsoft Project. Выполнив эти шаги, вы сможете эффективно манипулировать настройками шкалы ставок для назначений ресурсов в ваших Java-приложениях.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1. Среда разработки Java: убедитесь, что в вашей системе установлен Java Development Kit (JDK).
2.  Библиотека Aspose.Tasks для Java: Загрузите и установите библиотеку Aspose.Tasks для Java с сайта[здесь](https://releases.aspose.com/tasks/java/).

## Импортировать пакеты
Во-первых, вам необходимо импортировать необходимые пакеты для работы с функциями Aspose.Tasks. 
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
## Шаг 1. Настройте свой проект
Начните с настройки проекта Java и включите библиотеку Aspose.Tasks в свои зависимости.
## Шаг 2. Загрузите файл проекта
Загрузите файл проекта, с которым хотите работать, в свое Java-приложение.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Шаг 3. Добавьте задачу
Добавьте новую задачу в свой проект.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Шаг 4: Определите ресурсы
Дайте определение материальных и нематериальных ресурсов и укажите их виды.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Шаг 5. Назначьте ресурсы задаче
Назначьте задаче ранее определенные ресурсы вместе с их типами шкалы ставок.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Шаг 6: Сохраните проект
Сохраните проект с измененными назначениями ресурсов.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Шаг 7. Получение назначений ресурсов
Перезагрузите сохраненный проект и получите назначения ресурсов, чтобы проверить настройки шкалы ставок.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Заключение
Управление масштабом распределения ресурсов в Aspose.Tasks for Java имеет решающее значение для эффективного управления проектами. Следуя этому пошаговому руководству, вы сможете легко манипулировать настройками шкалы ставок для назначений ресурсов в ваших Java-приложениях.
## Часто задаваемые вопросы
### Вопрос 1: Могу ли я использовать Aspose.Tasks для Java с любой Java IDE?
О: Да, Aspose.Tasks for Java совместим со всеми основными Java IDE, включая IntelliJ IDEA, Eclipse и NetBeans.
### Вопрос 2. Поддерживает ли Aspose.Tasks другие форматы файлов, кроме MPP?
О: Да, Aspose.Tasks поддерживает различные форматы файлов, включая MPP, XML и HTML.
### Вопрос 3: Подходит ли Aspose.Tasks для управления проектами на уровне предприятия?
О: Конечно, Aspose.Tasks предлагает комплексные функции для управления проектами любого масштаба, что делает его подходящим для управления проектами на уровне предприятия.
### Вопрос 4. Могу ли я настраивать назначения ресурсов, выходя за рамки шкалы ставок?
О: Да, Aspose.Tasks предоставляет широкие возможности для настройки назначения ресурсов, включая корректировку стоимости, работы и продолжительности.
### Вопрос 5: Существует ли форум сообщества для поддержки Aspose.Tasks?
 О: Да, вы можете найти поддержку и пообщаться с другими пользователями на форуме Aspose.Tasks.[здесь](https://forum.aspose.com/c/tasks/15).