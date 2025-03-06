---
title: Рендеринг использования ресурсов и просмотр листа в Aspose.Tasks
linktitle: Рендеринг использования ресурсов и просмотр листа в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как отображать использование ресурсов MS Project и представления листов в Aspose.Tasks для Java. Следуйте нашему пошаговому руководству, чтобы легко создавать подробные отчеты в формате PDF.
weight: 16
url: /ru/java/resource-management/render-resource-usage-sheet-view/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Рендеринг использования ресурсов и просмотр листа в Aspose.Tasks

## Введение
В этом уроке мы узнаем, как использовать Aspose.Tasks для Java для рендеринга представлений использования ресурсов MS Project и листов. Aspose.Tasks — это мощная библиотека Java, которая позволяет разработчикам работать с файлами Microsoft Project без необходимости установки Microsoft Project.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас установлены и настроены следующие необходимые компоненты:
1. Java Development Kit (JDK): убедитесь, что в вашей системе установлен Java Development Kit. Вы можете загрузить и установить последнюю версию JDK с веб-сайта Oracle.
2.  Aspose.Tasks for Java: Загрузите и установите библиотеку Aspose.Tasks for Java из[страница загрузки](https://releases.aspose.com/tasks/java/).

## Импортировать пакеты
Сначала вам необходимо импортировать необходимые пакеты в ваш Java-проект:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Шаг 1. Прочтите исходный проект
```java
// Путь к каталогу документов.
String dataDir = "Your Data Directory";
// Читать исходный проект
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
На этом этапе мы указываем путь к исходному файлу проекта (`ResourceUsageView.mpp` ) и используйте`Project` класс, чтобы прочитать это.
## Шаг 2. Определите SaveOptions с необходимыми настройками TimeScale
```java
// Определите SaveOptions с необходимыми настройками TimeScale как дни.
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Здесь мы определяем`SaveOptions` с необходимым`TimeScale` настройки. В этом примере мы устанавливаем`TimeScale` до Дней.
## Шаг 3. Установите для формата презентации значение ResourceUsage.
```java
// Установите формат презентации ResourceUsage.
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 Мы установили формат представления`ResourceUsage`, указывая, что мы хотим отобразить представление использования ресурсов.
## Шаг 4. Сохраните проект
```java
// Сохранить проект
project.save(dataDir + days, options);
```
Наконец, мы сохраняем проект с указанными параметрами. В этом примере выходной файл будет сохранен как`result_days.pdf`.
## Шаг 5. Отрисовка представлений для других настроек шкалы времени
Повторите шаги 2–4 для визуализации представлений с различными настройками TimeScale (ThirdsOfMonths и Months).
```java
// Установите для параметров шкалы времени значение ThirdsOfMonths.
options.setTimescale(Timescale.ThirdsOfMonths);
// Сохранить проект
project.save(thirds, options);
// Установите для параметра «Шкала времени» значение «Месяцы».
options.setTimescale(Timescale.Months);
// Сохранить проект
project.save(dataDir + months, options);
```
 Обязательно измените`Timescale` настройки соответственно для каждого вида.

## Заключение
В этом руководстве мы рассмотрели, как использовать Aspose.Tasks для Java для визуализации использования ресурсов MS Project и представлений листов. Следуя шагам, описанным выше, вы сможете эффективно создавать эти представления в формате PDF, что позволит улучшить визуализацию и анализ данных вашего проекта.
## Часто задаваемые вопросы
### Может ли Aspose.Tasks отображать другие представления, кроме использования ресурсов и листа?
Aspose.Tasks поддерживает отображение различных представлений, таких как диаграмма Ганта, использование задач и представление календаря, среди других.
### Совместим ли Aspose.Tasks с различными версиями файлов Microsoft Project?
Да, Aspose.Tasks поддерживает широкий спектр форматов файлов Microsoft Project, включая форматы MPP, MPT и XML.
### Могу ли я настроить внешний вид отображаемых представлений с помощью Aspose.Tasks?
Абсолютно! Aspose.Tasks предоставляет широкие возможности для настройки внешнего вида и расположения отображаемых представлений в соответствии с вашими конкретными требованиями.
### Требуется ли для Aspose.Tasks установка Microsoft Project в системе?
Нет, Aspose.Tasks — это отдельная библиотека, для работы которой не требуется установка Microsoft Project.
### Доступна ли техническая поддержка для пользователей Aspose.Tasks?
 Да, пользователи Aspose.Tasks могут воспользоваться технической поддержкой через[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
