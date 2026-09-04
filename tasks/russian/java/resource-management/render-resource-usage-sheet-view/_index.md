---
date: 2026-06-15
description: Узнайте, как конвертировать mpp в pdf и отобразить представления Resource
  Usage и Sheet с помощью Aspose.Tasks для Java. Следуйте нашему пошаговому руководству,
  чтобы установить timescale и без усилий создавать подробные PDF‑отчёты.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: Конвертировать MPP в PDF и отобразить представление Resource Usage – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Конвертировать MPP в PDF и отобразить представление Resource Usage – Aspose.Tasks
url: /ru/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Конвертировать MPP в PDF и отобразить представление использования ресурсов – Aspose.Tasks

В этом руководстве вы узнаете **как конвертировать mpp в pdf**, одновременно отображая представления использования ресурсов и листа файла Microsoft Project. Использование Aspose.Tasks для Java устраняет необходимость в Microsoft Project на сервере, предоставляя быстрый и надёжный способ создания PDF‑отчётов из файлов MPP. Мы также покажем вам **как установить масштаб времени**, чтобы вывод соответствовал вашим требованиям к отчетности.

## Быстрые ответы
- **Что делает Aspose.Tasks?** Он читает, изменяет и конвертирует файлы Microsoft Project (MPP) без необходимости установки MS Project.  
- **Можно ли конвертировать MPP в PDF одной строкой кода?** Да — загрузите Project, задайте SaveOptions и вызовите `save`.  
- **Какие масштабы времени поддерживаются?** Days, ThirdsOfMonths, and Months.  
- **Нужна ли лицензия для продакшна?** Для не‑тестовых развертываний требуется коммерческая лицензия.  
- **Совместима ли библиотека с Java 8+?** Абсолютно — она поддерживает Java 8 и более поздние версии.

## Что такое конвертация mpp в pdf?
*Convert mpp to pdf* относится к процессу взятия файла Microsoft Project (.mpp) и создания версии в формате Portable Document Format (PDF), которая точно воспроизводит таблицы, графики, диаграммы и распределение ресурсов проекта. Полученный PDF легко делиться, печатать и архивировать без необходимости установки Microsoft Project на машине получателя.

## Почему конвертировать Project в PDF с помощью Aspose.Tasks?
Aspose.Tasks поддерживает **более 50 форматов ввода и вывода** и может отрисовывать проекты в несколько сотен страниц без загрузки всего файла в память, снижая использование ОЗУ до 70 %. PDF‑вывод сохраняет таблицы, диаграммы и распределение ресурсов, что делает его идеальным для распространения среди заинтересованных сторон и архивирования.

## Предварительные требования
1. **Java Development Kit (JDK)** — Java 8 или новее, установленный на вашем компьютере.  
2. **Aspose.Tasks for Java** — скачайте последнюю JAR‑файл со [страницы загрузки](https://releases.aspose.com/tasks/java/).  

## Как конвертировать mpp в pdf с помощью Aspose.Tasks для Java?
Загрузите ваш исходный файл MPP, настройте желаемый масштаб времени, установите формат представления в **ResourceUsage** и сохраните результат как PDF. Этот сквозной процесс требует всего несколько вызовов API и выполняется менее чем за секунду для типичных размеров проектов.

### Шаг 1: Чтение исходного проекта
Класс `Project` представляет файл Microsoft Project, загруженный в память, предоставляя доступ к его данным и структуре.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### Шаг 2: Определить SaveOptions с требуемыми настройками TimeScale
`SaveOptions` настраивает способ сохранения проекта, позволяя задавать специфичные для формата параметры, такие как масштаб времени.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Шаг 3: Установить формат представления в ResourceUsage
`PresentationFormat` определяет, какое представление проекта (например, ResourceUsage) будет отрисовано в выходном документе.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Шаг 4: Сохранить проект как PDF
`project.save` записывает проект в файл, используя предоставленные `SaveOptions`, создавая окончательный PDF.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Шаг 5: Отрисовать представления для других настроек TimeScale
Повторите предыдущие шаги, изменив значение `TimeScale`, чтобы отрисовать дополнительные представления с другим масштабом времени.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### Шаг 6: Опционально – Конвертировать несколько проектов пакетно
Если вам нужно **конвертировать проект в pdf** для множества файлов, разместите вышеуказанную логику внутри цикла, который проходит по каталогу файлов *.mpp*. Этот подход **сохраняет ms project pdf** файлы массово с минимальными изменениями кода.  
Следующий код демонстрирует полный пример конвертации файла MPP в PDF с нужными настройками.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Распространённые проблемы и решения
- **Missing fonts in PDF** – Убедитесь, что необходимые шрифты установлены на сервере, или внедрите их через `PdfSaveOptions`.  
- **Large project files cause OutOfMemoryError** – Используйте `LoadOptions.setLoadAllResources(false)`, чтобы загружать ресурсы по требованию.  
- **Incorrect timescale rendering** – Проверьте, что `options.setTimeScale(TimeScale.Days)` (или другое значение enum) соответствует требуемой гранулярности.

## Часто задаваемые вопросы

**Q: Может ли Aspose.Tasks отрисовывать другие представления, помимо Resource Usage и Sheet?**  
A: Да, он также поддерживает Gantt Chart, Task Usage, Calendar и многие дополнительные представления.

**Q: Совместима ли Aspose.Tasks с разными версиями файлов Microsoft Project?**  
A: Абсолютно — она работает с форматами MPP, MPT и XML от Project 2000 до Project 2021.

**Q: Могу ли я настроить внешний вид отрисованных представлений?**  
A: Да, вы можете изменять цвета, шрифты и макеты столбцов через `PdfSaveOptions` и `PresentationOptions`.

**Q: Требуется ли для Aspose.Tasks установка Microsoft Project?**  
A: Нет, это автономная библиотека, работающая в любой среде, совместимой с Java.

**Q: Где я могу получить техническую поддержку?**  
A: Поддержка доступна через [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15/).

---

**Последнее обновление:** 2026-06-15  
**Тестировано с:** Aspose.Tasks 24.12 for Java  
**Автор:** Aspose

## Связанные руководства

- [Отрисовать представление использования ресурсов и лист в Aspose.Tasks](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Как экспортировать PDF в Aspose.Tasks – Save As PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [Как создать файлы MPP с помощью Aspose.Tasks для Java](/tasks/java/project-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}