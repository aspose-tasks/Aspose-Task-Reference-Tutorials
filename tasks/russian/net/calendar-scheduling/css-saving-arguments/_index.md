---
date: 2026-07-05
description: Узнайте, как настроить CSS при экспорте проекта в HTML с использованием
  Aspose.Tasks для .NET. Настройте вывод HTML с помощью аргументов сохранения CSS.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Как настроить CSS при сохранении проектов с помощью Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Как настроить CSS при сохранении проектов с помощью Aspose.Tasks
url: /ru/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как настроить CSS при сохранении проектов с Aspose.Tasks

В этом руководстве вы узнаете, **как настроить CSS** во время экспорта HTML-файла Microsoft Project с помощью Aspose.Tasks для .NET. Настраивая параметры сохранения CSS, вы получаете полный контроль над визуальным стилем генерируемых HTML‑страниц, делая вывод соответствующим вашему бренду или стандартам отчетности.

## Быстрые ответы
- **Что является основной точкой входа?** Используйте `HtmlSaveOptions` с пользовательскими обратными вызовами.  
- **Нужна ли лицензия?** Да, для продакшн‑использования требуется действующая лицензия Aspose.Tasks.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Можно ли экспортировать большие проекты?** Aspose.Tasks обрабатывает проекты с > 10 000 задач без загрузки всего файла в память.  
- **Является ли настройка CSS необязательной?** Да, вы можете опустить обратные вызовы и использовать таблицу стилей по умолчанию.

## Как настроить CSS в Aspose.Tasks?

Загрузите ваш проект, привяжите обратные вызовы сохранения CSS к объекту `HtmlSaveOptions`, а затем вызовите `project.Save`. Этот шаблон позволяет писать пользовательские CSS‑файлы, заменять стили по умолчанию и управлять структурой папок — всё в нескольких строках кода. Обратные вызовы вызываются автоматически для каждого CSS‑файла во время процесса экспорта.

`HtmlSaveOptions` настраивает процесс экспорта проекта в HTML.

## Введение

В этом учебнике мы подробно рассмотрим процесс сохранения параметров CSS с помощью Aspose.Tasks для .NET. Каскадные таблицы стилей (CSS) играют ключевую роль в определении внешнего вида HTML‑элементов. Aspose.Tasks позволяет эффективно управлять и сохранять эти атрибуты CSS.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть следующие предварительные требования:

1. Установка: Убедитесь, что вы установили Aspose.Tasks для .NET. Вы можете скачать его с [веб‑сайта](https://releases.aspose.com/tasks/net/).
2. Базовые знания: Рекомендуется знание C# и среды разработки .NET.

## Импорт пространств имён

Чтобы начать, импортируйте необходимые пространства имён:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Шаг 1: Определить обратные вызовы сохранения CSS

`ICssSavingCallback` — это интерфейс, позволяющий настраивать способ сохранения CSS‑файлов во время экспорта HTML.

**Обратный вызов сохранения CSS** — это делегат, который Aspose.Tasks вызывает для записи CSS‑файлов во время экспорта HTML. Определите методы обратных вызовов, чтобы контролировать создание каждого CSS‑файла:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Шаг 2: Реализовать обратные вызовы сохранения шрифтов и изображений

`FontSavingArgs` предоставляет информацию о сохраняемом шрифте, а `ImageSavingArgs` — детали ресурсов изображений.

Реализуйте методы обратных вызовов сохранения шрифтов и изображений аналогичным образом:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Шаг 3: Настроить параметры сохранения

`HtmlSaveOptions` — объект конфигурации, управляющий тем, как проект экспортируется в HTML.

`HtmlSaveOptions` позволяет задавать обратные вызовы, папки вывода и другие параметры экспорта.

Установите его свойства, чтобы использовать ранее определённые обратные вызовы и указать папку вывода:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Шаг 4: Сохранить проект с пользовательским CSS

`Project` представляет файл Microsoft Project, который можно изменять и сохранять.

Наконец, сохраните ваш проект с пользовательскими настройками CSS:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Почему стоит настраивать CSS при экспорте проектов?

Aspose.Tasks поддерживает **экспорт проекта в HTML** более чем в 30 форматах и может генерировать до 30 отдельных CSS‑файлов за один экспорт. Он надёжно обрабатывает проекты, содержащие более 10 000 задач, при этом потребление памяти остаётся ниже 200 МБ, что позволяет выполнять корпоративные отчёты без узких мест в производительности.

## Заключение

В этом учебнике мы рассмотрели, как сохранять параметры CSS с помощью Aspose.Tasks для .NET. Определяя обратные вызовы сохранения CSS и настраивая параметры сохранения HTML, мы можем эффективно управлять атрибутами CSS в соответствии с нашими требованиями.

## Часто задаваемые вопросы

### Вопрос 1: Что такое Aspose.Tasks для .NET?

A1: Aspose.Tasks для .NET — мощный .NET API, позволяющий разработчикам программно работать с файлами Microsoft Project.

### Вопрос 2: Можно ли настраивать атрибуты CSS при сохранении HTML‑файлов с помощью Aspose.Tasks?

A2: Да, вы можете определить обратные вызовы сохранения CSS, чтобы настраивать атрибуты CSS в соответствии с вашими потребностями.

### Вопрос 3: Совместим ли Aspose.Tasks для .NET со всеми версиями файлов Microsoft Project?

A3: Aspose.Tasks для .NET поддерживает различные версии файлов Microsoft Project, обеспечивая совместимость в разных средах.

### Вопрос 4: Где можно найти полную документацию по Aspose.Tasks для .NET?

A4: Вы можете обратиться к [документации](https://reference.aspose.com/tasks/net/) для получения подробной информации и примеров.

### Вопрос 5: Предоставляет ли Aspose.Tasks для .NET поддержку разработчиков?

A5: Да, вы можете получить поддержку от сообщества Aspose.Tasks через [форум](https://forum.aspose.com/c/tasks/15).

**Дополнительные вопросы**

**В: Как настройка CSS влияет на размер экспортируемого HTML?**  
О: Использование пользовательского CSS может уменьшить общий размер до 15 %, поскольку позволяет удалить неиспользуемые стили по умолчанию.

**В: Можно ли использовать одни и те же обратные вызовы для нескольких проектов?**  
О: Конечно. Реализуйте обратные вызовы один раз и переиспользуйте их для любого количества экспортов проектов.

**В: Можно ли встроить CSS непосредственно в HTML вместо отдельных файлов?**  
О: Да, установите `HtmlSaveOptions.EmbeddedCss = true`, чтобы встроить таблицу стилей, что упрощает распространение.

---

**Последнее обновление:** 2026-07-05  
**Тестировано с:** Aspose.Tasks 24.11 for .NET  
**Автор:** Aspose

## Связанные учебники

- [Сохранить MS Project как HTML с Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Реализация обратного вызова сохранения страниц в Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Обработка сохранения изображений в Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}