---
title: Формулы MS Project с Aspose.Tasks для Java
linktitle: Работа с формулами в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как манипулировать файлами MS Project на Java с помощью библиотеки Aspose.Tasks. С легкостью создавайте, изменяйте и рассчитывайте атрибуты.
weight: 11
url: /ru/java/formulas/work-with-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Формулы MS Project с Aspose.Tasks для Java

## Введение
В этом уроке мы углубимся в работу с формулами MS Project с использованием Aspose.Tasks для Java. Aspose.Tasks — это мощная библиотека, которая позволяет разработчикам программно манипулировать файлами Microsoft Project. Благодаря его обширным функциям вы можете легко создавать, читать, изменять и конвертировать файлы проектов в приложениях Java.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас настроены следующие предварительные условия:
### Среда разработки Java
Убедитесь, что в вашей системе установлен Java Development Kit (JDK). Вы можете загрузить и установить последнюю версию JDK с веб-сайта Oracle.
### Библиотека Aspose.Tasks
Вам необходимо добавить библиотеку Aspose.Tasks в ваш Java-проект. Вы можете скачать библиотеку с сайта[Страница загрузки Aspose.Tasks для Java](https://releases.aspose.com/tasks/java/) и включите его в зависимости вашего проекта.

## Импортировать пакеты
Прежде чем углубляться в примеры, импортируйте необходимые пакеты в свой Java-код:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Давайте разобьем приведенный пример на несколько этапов:
## Шаг 1. Создайте тестовый проект с настраиваемым полем
```java
Project project = CreateTestProjectWithCustomField();
```
 Сначала создайте тестовый проект с настраиваемым полем, используя команду`CreateTestProjectWithCustomField()` метод. Этот метод вернет объект Project, представляющий вновь созданный проект.
## Шаг 2. Определите определение расширенного атрибута
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Получите определение расширенного атрибута из проекта и задайте его псевдоним и формулу. В этом примере мы определяем атрибут для расчета количества дней от даты окончания до крайнего срока.
## Шаг 3. Установите крайний срок для задачи
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Создайте объект Calendar и установите дату крайнего срока. Затем извлеките задачу из проекта и установите ее крайний срок с помощью объекта Calendar.
## Шаг 4. Сохраните проект
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Наконец, сохраните проект в файл с указанным именем и форматом. В данном случае мы сохраняем его как файл MPP.

## Заключение
В этом уроке мы научились работать с формулами MS Project, используя Aspose.Tasks для Java. Выполнив эти шаги, вы сможете эффективно манипулировать файлами проекта программно, добавляя настраиваемые поля и вычисляя атрибуты на основе формул.

## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks с другими языками программирования?
О: Да, Aspose.Tasks поддерживает различные языки программирования, включая Java, .NET и другие.
### Вопрос: Доступна ли бесплатная пробная версия Aspose.Tasks?
 О: Да, вы можете скачать бесплатную пробную версию Aspose.Tasks с сайта[здесь](https://releases.aspose.com/).
### Вопрос: Где я могу найти документацию для Aspose.Tasks?
 О: Вы можете найти документацию для Aspose.Tasks.[здесь](https://reference.aspose.com/tasks/java/).
### Вопрос: Как я могу получить поддержку Aspose.Tasks?
 О: Для получения поддержки вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Вопрос: Нужна ли мне временная лицензия для использования Aspose.Tasks?
О: Если вам требуются дополнительные функции, вы можете получить временную лицензию на сайте[здесь](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
