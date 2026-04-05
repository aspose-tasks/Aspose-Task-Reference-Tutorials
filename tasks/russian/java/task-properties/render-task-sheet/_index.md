---
date: 2026-02-26
description: Узнайте, как сохранить проект в формате PDF и отобразить лист задач с
  помощью Aspose.Tasks для Java. Быстро экспортируйте MPP в PDF с помощью этого пошагового
  руководства.
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Сохранить проект в PDF – отобразить лист задач с Aspose.Tasks для Java
url: /ru/java/task-properties/render-task-sheet/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сохранить проект в PDF – отобразить лист задач в Aspose.Tasks

## Introduction
В этом подробном руководстве вы узнаете, как **save project as PDF** и создать лист задач с помощью Aspose.Tasks для Java. Независимо от того, нужно ли вам экспортировать файл Microsoft Project (MPP) в PDF для обзоров заинтересованных сторон или просто отобразить чистый лист задач для отчётности, этот учебник проведёт вас через каждый шаг, объяснит, почему каждый параметр важен, и покажет точный код, который необходимо выполнить.

## Quick Answers
- **Что делает «save project as pdf»?** Он преобразует файл Microsoft Project (MPP) в документ PDF, при необходимости оформляя его как лист задач.  
- **Какой формат используется для PDF листа задач?** Параметр `PresentationFormat.TaskSheet` в `PdfSaveOptions`.  
- **Нужна ли лицензия для выполнения кода?** Для продакшн‑использования требуется временная или полная лицензия; бесплатная пробная версия подходит для оценки.  
- **Каковы основные предварительные требования?** Java JDK, библиотека Aspose.Tasks for Java и действительный файл проекта (например, *.mpp).  
- **Можно ли настроить макет PDF?** Да, Aspose.Tasks предоставляет множество свойств `PdfSaveOptions` для стилизации и настройки страниц.

## What is “save project as pdf”?
Сохранение проекта в PDF преобразует внутренние данные проекта в переносимый документ только для чтения. Это идеально подходит для обмена расписаниями, листами задач или статусными отчётами с заинтересованными сторонами, у которых нет установленного Microsoft Project.

## Why render a task sheet?
Лист задач отображает каждую задачу в табличном виде, показывая идентификаторы, названия, даты начала/окончания и другие поля. Экспорт в PDF обеспечивает единообразное форматирование на разных платформах и упрощает печать или встраивание в другие документы.

## Prerequisites
Before you start, make sure you have:

1. **Java Development Kit (JDK)** – установлена последняя версия и `java`/`javac` доступны в PATH.  
2. **Aspose.Tasks for Java** – скачайте библиотеку с официального сайта [здесь](https://releases.aspose.com/tasks/java/).  
3. Действительный **файл проекта** (`*.mpp`), который вы хотите конвертировать, например, `NewProductDev.mpp`.  

## Import Packages
Сначала импортируйте необходимые классы Aspose.Tasks. Эти импорты предоставляют доступ к параметрам сохранения PDF, форматам представления и основному объекту `Project`.

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## Step‑by‑Step Guide

### Step 1: Set Your Document Directory
Укажите папку, в которой находится исходный файл MPP и куда будет записан сгенерированный PDF. Можно использовать абсолютный или относительный путь; просто убедитесь, что папка существует.

```java
String dataDir = "Your Document Directory";
```

### Step 2: Load the Project File
Создайте экземпляр `Project`, загрузив существующий файл MPP. Этот объект представляет всю структуру проекта в памяти.

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### Step 3: Configure Save Options – Export MPP to PDF
Создайте экземпляр `PdfSaveOptions` и укажите Aspose.Tasks, что вы хотите отобразить PDF как **лист задач**. Это ключевой шаг для сценария *export project pdf*.

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### Step 4: Save the Project as a Task Sheet – Save Project as PDF
Вызовите метод `save` у объекта `Project`, передав имя целевого файла и настроенные параметры. Это действие **преобразует файл MPP в PDF**, отформатированный как лист задач.

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### Step 5: Review the Result
Перейдите в указанный вами каталог (`dataDir`). Вы должны увидеть `taskSheet.pdf`, содержащий аккуратно отформатированный список всех задач. Откройте его в любом PDF‑просмотрщике, чтобы убедиться, что конвертация прошла успешно.

## Common Issues and Solutions
- **FileNotFoundException** – Убедитесь, что `dataDir` заканчивается разделителем пути (`/` или `\\`) и имя файла MPP указано правильно.  
- **LicenseException** – Если появляются ошибки лицензирования, примените временную или приобретённую лицензию перед вызовом любого API Aspose.Tasks.  
- **Blank PDF** – Убедитесь, что проект действительно содержит задачи; пустой проект приведёт к пустому PDF.

## Frequently Asked Questions

**В: Совместим ли Aspose.Tasks со всеми версиями Java?**  
О: Да, Aspose.Tasks работает с широким спектром версий Java. См. [документацию](https://reference.aspose.com/tasks/java/) для деталей.

**В: Можно ли попробовать Aspose.Tasks перед покупкой?**  
О: Конечно! Исследуйте бесплатную пробную версию [здесь](https://releases.aspose.com/).

**В: Где можно получить поддержку по Aspose.Tasks?**  
О: Присоединяйтесь к сообществу Aspose.Tasks на [форуме](https://forum.aspose.com/c/tasks/15) для поддержки и обсуждений.

**В: Как получить временную лицензию для Aspose.Tasks?**  
О: Получите временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

**В: Где можно приобрести Aspose.Tasks for Java?**  
О: Приобретите Aspose.Tasks for Java [здесь](https://purchase.aspose.com/buy).

## Conclusion
Следуя этим шагам, вы узнали, как **save project as PDF**, конкретно отобразив лист задач, используя Aspose.Tasks для Java. Эта возможность позволяет быстро *export MPP to PDF*, делиться читаемыми снимками проекта и интегрировать данные проекта в более широкие процессы отчётности.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}