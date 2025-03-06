---
title: Напишите краткое описание проекта MPP в Aspose.Tasks
linktitle: Напишите краткое описание проекта MPP в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как писать резюме проекта MPP на Java с помощью Aspose.Tasks. Устанавливайте и извлекайте информацию о проекте без особых усилий.
type: docs
weight: 27
url: /ru/java/project-file-operations/write-mpp-project-summary/
---
## Введение
В этом уроке мы узнаем, как использовать Aspose.Tasks для Java для написания резюме проекта MPP. Aspose.Tasks — мощная Java-библиотека для работы с файлами Microsoft Project. Выполнив шаги, описанные ниже, вы сможете устанавливать и получать различную сводную информацию о проекте, используя эту библиотеку.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1. Java Development Kit (JDK): убедитесь, что в вашей системе установлен JDK.
2.  Aspose.Tasks для Java: Загрузите и установите библиотеку Aspose.Tasks для Java. Вы можете скачать его с[здесь](https://releases.aspose.com/tasks/java/).
3. Интегрированная среда разработки (IDE). Выберите предпочитаемую среду IDE для разработки на Java, например IntelliJ IDEA, Eclipse или NetBeans.

## Импортировать пакеты
Во-первых, импортируйте необходимые пакеты в ваш класс Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Шаг 1. Настройка проекта и определение сводной информации
```java
// Путь к каталогу документов.
String dataDir = "Your Data Directory";
//Инициализируйте новый объект проекта, указав путь к файлу проекта.
Project project = new Project(dataDir + "project.mpp");
// Установить сводную информацию о проекте
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Установить дату создания проекта
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Задайте ключевые слова для проекта
project.set(Prj.KEYWORDS, "MPP Aspose");
// Установите последнюю распечатанную дату проекта
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Шаг 2. Сохраните сводную информацию о проекте
```java
// Сохраните проект обратно в формате MPP.
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Отображение сообщения об успехе
System.out.println("Process completed Successfully");
```
## Шаг 3. Прочтите краткую информацию о проекте
```java
// Чтение сводной информации о проекте
project = new Project(dataDir + "MppAspose.xml");
// Распечатать автора проекта
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Распечатать последнего автора проекта
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Распечатать номер версии проекта
System.out.println("Revision: " + project.get(Prj.REVISION));
// Распечатать ключевые слова проекта
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Распечатать комментарии проекта
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Распечатать дату создания проекта
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Распечатать ключевые слова проекта (снова)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Распечатать последнюю напечатанную дату проекта
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Заключение
В этом руководстве мы рассмотрели, как писать резюме проекта MPP с использованием Aspose.Tasks для Java. Выполнив эти шаги, вы сможете эффективно устанавливать и получать различную сводную информацию о файлах вашего проекта. Aspose.Tasks упрощает процесс работы с файлами Microsoft Project в приложениях Java, предлагая надежную функциональность и простоту использования.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks для Java с другими библиотеками Java?
О: Да, Aspose.Tasks for Java можно легко интегрировать с другими библиотеками Java, чтобы расширить ваши возможности управления проектами.
### Вопрос: Доступна ли пробная версия Aspose.Tasks для Java?
 О: Да, вы можете скачать бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).
### Вопрос: Как часто обновляется Aspose.Tasks для Java?
О: Aspose.Tasks for Java регулярно обновляется, чтобы обеспечить совместимость с последними версиями файлов Java и Microsoft Project.
### Вопрос: Могу ли я дополнительно настроить сводную информацию о проекте?
О: Конечно, Aspose.Tasks for Java предоставляет широкие возможности для настройки сводной информации проекта в соответствии с вашими конкретными требованиями.
### Вопрос: Где я могу получить поддержку Aspose.Tasks для Java?
О: Вы можете получить поддержку на форуме сообщества Aspose.Tasks.[здесь](https://forum.aspose.com/c/tasks/15).