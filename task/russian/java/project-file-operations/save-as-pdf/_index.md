---
title: Сохранить как PDF в Aspose.Tasks
linktitle: Сохранить как PDF в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как конвертировать файлы проекта в PDF с помощью Aspose.Tasks для Java. Простые шаги для эффективного преобразования.
type: docs
weight: 17
url: /ru/java/project-file-operations/save-as-pdf/
---
## Введение
В этом уроке мы покажем вам процесс сохранения проекта в формате PDF с помощью Aspose.Tasks для Java. С помощью Aspose.Tasks вы можете эффективно конвертировать файлы проекта в формат PDF, обеспечивая совместимость и простоту совместного использования. Давайте углубимся в шаги:
## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующее:
1. Комплект разработки Java (JDK): убедитесь, что в вашей системе установлен JDK.
2.  Aspose.Tasks для библиотеки Java: Загрузите и установите библиотеку Aspose.Tasks. Вы можете найти ссылку для скачивания[здесь](https://releases.aspose.com/tasks/java/).
3. Файл проекта: подготовьте файл проекта (например, HomeMovePlan.mpp), который вы хотите преобразовать в PDF.

## Импортировать пакеты
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Шаг 1. Прочтите входной файл проекта
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Обязательно замените`"Your Data Directory"` с путем к вашему каталогу данных, содержащему файл проекта.
## Шаг 2. Сохраните проект в формате PDF.
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Этот фрагмент кода сохраняет проект в виде PDF-файла с именем «Project5.pdf».
## Шаг 3. Подгонка содержимого по размеру ячейки
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Здесь мы устанавливаем параметры сохранения PDF-файла, включая настройку содержимого, временной шкалы и формата презентации.
## Шаг 4. Скройте легенды
```java
o.setLegendOnEachPage(false);
```
Этот шаг скрывает легенды на каждой странице PDF-файла.
## Шаг 5. Сохраните проект с примененными параметрами
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Наконец, этот код сохраняет проект с примененными параметрами в файл PDF.

## Заключение
В этом уроке мы узнали, как использовать Aspose.Tasks для Java для сохранения проекта в формате PDF. Следуя этим простым шагам, вы сможете эффективно конвертировать файлы проекта для удобного обмена и распространения.
## Часто задаваемые вопросы
### Вопрос: Совместим ли Aspose.Tasks со всеми версиями Java?
О: Да, Aspose.Tasks поддерживает версии Java, начиная с JDK 6 и выше.
### Вопрос: Могу ли я настроить внешний вид PDF-файла?
А: Абсолютно! Aspose.Tasks предоставляет различные возможности для настройки вывода PDF в соответствии с вашими требованиями.
### Вопрос: Поддерживает ли Aspose.Tasks другие форматы файлов для конвертации?
О: Да, Aspose.Tasks поддерживает широкий спектр форматов файлов, включая MPP, XML, XLSX и другие.
### Вопрос: Доступна ли пробная версия для Aspose.Tasks?
 О: Да, вы можете получить бесплатную пробную версию Aspose.Tasks на сайте[здесь](https://releases.aspose.com/).
### Вопрос: Где я могу получить поддержку для Aspose.Tasks?
 О: Для получения поддержки и помощи вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).