---
date: 2026-01-15
description: Узнайте, как сохранить проект в формате PDF и отобразить представления
  Resource Usage и Sheet в MS Project с помощью Aspose.Tasks для Java. Следуйте нашему
  пошаговому руководству, чтобы легко экспортировать проект в PDF.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Сохранить проект в PDF – отобразить использование ресурсов и листовой вид в
  Aspose.Tasks
url: /ru/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сохранить проект как PDF – отобразить представления использования ресурсов и листа в Aspose.Tasks

## Introduction
В этом руководстве вы узнаете, как **сохранить проект как PDF**, одновременно отрисовывая представления использования ресурсов и листа файла Microsoft Project. Независимо от того, нужно ли вам создать печатный отчет для заинтересованных сторон или конвертировать файлы MPP в универсальный формат, Aspose.Tasks for Java делает процесс простым — без необходимости установки Microsoft Project.

## Quick Answers
- **Что делает «save project as pdf»?** Он преобразует файл проекта (MPP) в документ PDF, сохраняя выбранное представление.  
- **Какое представление можно экспортировать?** Resource Usage, Sheet, Gantt, Task Usage и другие.  
- **Можно ли изменить масштаб времени в PDF?** Да — доступны варианты Days, ThirdsOfMonths и Months.  
- **Нужна ли установка Microsoft Project?** Нет, Aspose.Tasks работает независимо.  
- **Требуется ли лицензия для продакшн?** Да, для использования не в режиме пробной версии необходима коммерческая лицензия.

## What is “save project as PDF”?
Сохранение проекта как PDF создаёт статическое, высоко‑разрешённое представление выбранного представления Project. Это идеально для обмена с клиентами, архивирования или печати без раскрытия исходного файла проекта.

## Why use Aspose.Tasks to export project to PDF?
- **Нет внешних зависимостей** — работает на любой платформе, поддерживающей Java.  
- **Тонкий контроль** — вы можете выбрать представление, масштаб времени и макет.  
- **Высокая точность** — PDF отражает внешний вид оригинального представления Project.  
- **Готово к автоматизации** — интегрировать в CI‑конвейеры, службы отчетности или пакетные конвертеры.

## Prerequisites
Before we dive in, ensure you have:

1. **Java Development Kit (JDK)** — рекомендуется последняя версия.  
2. **Aspose.Tasks for Java** — загрузите со [страницы загрузки](https://releases.aspose.com/tasks/java/).  

## Import Packages
First, import the necessary classes into your Java project:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Step‑by‑Step Guide

### Step 1: Read the Source Project
Load the MPP file you want to convert.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Step 2: Define SaveOptions with Required Timescale (Export Project to PDF)
Configure the PDF export options and set the desired timescale.  
*Here we use **Days** as an example.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Step 3: Set the Presentation Format to ResourceUsage
Choose the view you want to render. In this case, the **Resource Usage** view.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Step 4: Save the Project (Convert MPP to PDF)
Execute the conversion and generate the PDF file.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Step 5: Render Views for Other Timescale Settings (Change Timescale PDF)
Repeat the previous steps to produce PDFs with different timescales such as **ThirdsOfMonths** and **Months**.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Common Issues and Solutions
- **Ошибки «файл не найден»** — проверьте, что `dataDir` указывает на правильную папку и что имя файла MPP точно совпадает.  
- **Пустой PDF‑файл** — убедитесь, что `PresentationFormat` соответствует представлению, содержащему данные (например, ResourceUsage).  
- **Неправильный масштаб времени** — проверьте, что `options.setTimescale()` вызывается перед каждым `project.save()`.

## Frequently Asked Questions

### Может ли Aspose.Tasks отрисовывать другие представления, кроме Resource Usage и Sheet?
Aspose.Tasks поддерживает отрисовку различных представлений, таких как Gantt Chart, Task Usage и Calendar, среди прочих.

### Совместим ли Aspose.Tasks с разными версиями файлов Microsoft Project?
Да, Aspose.Tasks поддерживает широкий спектр форматов файлов Microsoft Project, включая MPP, MPT и XML.

### Могу ли я настроить внешний вид отрисованных представлений с помощью Aspose.Tasks?
Абсолютно! Aspose.Tasks предоставляет обширные возможности для настройки внешнего вида и макета отрисованных представлений в соответствии с вашими требованиями.

### Требуется ли для Aspose.Tasks установка Microsoft Project на системе?
Нет, Aspose.Tasks — автономная библиотека и не требует установки Microsoft Project для своей работы.

### Доступна ли техническая поддержка для пользователей Aspose.Tasks?
Да, пользователи Aspose.Tasks могут получить техническую поддержку через [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose