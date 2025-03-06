---
title: Получить коды структуры проекта MS в Aspose.Tasks
linktitle: Получение структурных кодов в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как программно получить структурные коды Microsoft Project с помощью Aspose.Tasks для Java. Расширьте свои возможности управления проектами.
weight: 15
url: /ru/java/project-file-operations/retrieve-outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Получить коды структуры проекта MS в Aspose.Tasks

## Введение
В этом уроке мы узнаем, как получить структурные коды Microsoft Project с помощью Aspose.Tasks для Java. Коды структуры в MS Project обеспечивают структурированный способ категоризации и организации задач, ресурсов и заданий проекта. Aspose.Tasks — это мощная библиотека Java, которая позволяет разработчикам программно манипулировать файлами Microsoft Project и управлять ими.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас настроены следующие предварительные условия:
### 1. Среда разработки Java
Убедитесь, что в вашей системе установлен Java Development Kit (JDK). Вы можете загрузить и установить JDK с веб-сайта Oracle.
### 2. Библиотека Aspose.Tasks
 Загрузите и включите библиотеку Aspose.Tasks в свой Java-проект. Вы можете скачать библиотеку с сайта[Страница загрузки Aspose.Tasks для Java](https://releases.aspose.com/tasks/java/).
## Импортировать пакеты
Сначала импортируйте необходимые пакеты из Aspose.Tasks в свой Java-код:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Теперь давайте разобьем предоставленный пример кода на несколько шагов:
## Шаг 1. Загрузите проект
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 На этом этапе мы загружаем файл Microsoft Project в`Project` объект, используя предоставленное имя файла.
## Шаг 2. Получите структурные коды
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Мы перебираем каждое определение структурного кода в проекте.
## Шаг 3. Доступ к свойствам структурного кода
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Мы извлекаем и печатаем различные свойства определения структурного кода, такие как псевдоним, идентификатор поля и имя поля.
## Шаг 4. Проверьте корпоративный пользовательский код
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Мы проверяем, является ли общий код корпоративным пользовательским кодом, и соответствующим образом печатаем результат.
## Шаг 5. Отображение масок структурного кода
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Мы перебираем каждую маску, связанную с кодом схемы, и печатаем ее уровень и значение маски.
## Шаг 6. Отображение значений кода структуры
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Мы перебираем каждое значение структурного кода и печатаем его описание, идентификатор значения, значение и тип.
## Заключение
В этом уроке мы узнали, как получить структурные коды MS Project с помощью Aspose.Tasks для Java. Следуя предоставленным шагам, вы сможете эффективно получать доступ к структурным кодам в своих приложениях Java и манипулировать ими, обеспечивая расширенные возможности управления проектами.
## Часто задаваемые вопросы
### Вопрос 1: Могу ли я использовать Aspose.Tasks для Java для изменения структурных кодов в файле проекта?
О: Да, Aspose.Tasks for Java предоставляет API для программного изменения структурных кодов в файлах MS Project.
### Вопрос 2: Доступна ли пробная версия Aspose.Tasks для Java?
 О: Да, вы можете скачать бесплатную пробную версию Aspose.Tasks для Java с сайта[Сайт Aspose.Tasks](https://releases.aspose.com/).
### В3: Как я могу получить техническую поддержку для Aspose.Tasks для Java?
 О: Вы можете получить техническую поддержку, посетив[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) и размещайте там свои запросы.
### Вопрос 4: Могу ли я приобрести временную лицензию на Aspose.Tasks для Java?
 О: Да, вы можете приобрести временную лицензию на Aspose.Tasks для Java на сайте[страница покупки](https://purchase.aspose.com/temporary-license/).
### Вопрос 5: Где я могу найти полную документацию по Aspose.Tasks для Java?
 О: Вы можете обратиться к[документация](https://reference.aspose.com/tasks/java/) для получения подробной информации об использовании Aspose.Tasks для Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
