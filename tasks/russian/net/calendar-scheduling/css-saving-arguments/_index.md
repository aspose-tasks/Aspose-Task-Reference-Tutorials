---
title: CSS-сохранение аргументов в Aspose.Tasks
linktitle: CSS-сохранение аргументов в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как сохранить аргументы CSS в Aspose.Tasks для .NET, чтобы настроить вывод HTML. Улучшите презентацию с помощью индивидуальных настроек CSS.
weight: 20
url: /ru/net/calendar-scheduling/css-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# CSS-сохранение аргументов в Aspose.Tasks

## Введение

В этом уроке мы углубимся в процесс сохранения аргументов CSS с помощью Aspose.Tasks для .NET. Каскадные таблицы стилей (CSS) имеют решающее значение для определения представления элементов HTML. Aspose.Tasks позволяет нам эффективно манипулировать и сохранять эти атрибуты CSS.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

1.  Установка: Убедитесь, что вы установили Aspose.Tasks для .NET. Вы можете скачать его с сайта[Веб-сайт](https://releases.aspose.com/tasks/net/).

2. Базовые знания: рекомендуется знание среды разработки C# и .NET.

## Импортировать пространства имен

Для начала импортируйте необходимые пространства имен:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## Шаг 1. Определите обратные вызовы сохранения CSS

Во-первых, мы определяем методы обратного вызова сохранения CSS для обработки сохранения файлов CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Реализуйте здесь логику сохранения CSS.
    }
}
```

## Шаг 2. Реализуйте обратные вызовы для сохранения шрифтов и изображений

Затем аналогичным образом реализуйте методы обратного вызова для сохранения шрифта и изображения:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Реализуйте здесь логику сохранения шрифтов.
}

public void ImageSaving(ImageSavingArgs args)
{
    // Реализуйте здесь логику сохранения изображений.
}
```

## Шаг 3. Настройте параметры сохранения

Теперь настройте параметры сохранения HTML для использования реализованных обратных вызовов:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //Настройте параметры сохранения HTML
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Шаг 4. Сохраните проект с настроенным CSS

Наконец, сохраните проект с настроенными настройками CSS:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Заключение

В этом уроке мы рассмотрели, как сохранять аргументы CSS с помощью Aspose.Tasks для .NET. Определив обратные вызовы для сохранения CSS и настроив параметры сохранения HTML, мы можем эффективно манипулировать атрибутами CSS в соответствии с нашими требованиями.

## Часто задаваемые вопросы

### Вопрос 1. Что такое Aspose.Tasks для .NET?

A1: Aspose.Tasks for .NET — это мощный API .NET, который позволяет разработчикам программно работать с файлами Microsoft Project.

### Вопрос 2. Могу ли я настроить атрибуты CSS при сохранении HTML-файлов с помощью Aspose.Tasks?

О2: Да, вы можете определить обратные вызовы для сохранения CSS, чтобы настроить атрибуты CSS в соответствии с вашими потребностями.

### Вопрос 3. Совместим ли Aspose.Tasks для .NET со всеми версиями файлов Microsoft Project?

A3: Aspose.Tasks for .NET поддерживает различные версии файлов Microsoft Project, обеспечивая совместимость в различных средах.

### Вопрос 4. Где я могу найти подробную документацию по Aspose.Tasks для .NET?

A4: Вы можете обратиться к[документация](https://reference.aspose.com/tasks/net/) для получения подробной информации и примеров.

### Вопрос 5: Предлагает ли Aspose.Tasks для .NET поддержку разработчиков?

 О5: Да, вы можете получить поддержку от сообщества Aspose.Tasks через[Форум](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
