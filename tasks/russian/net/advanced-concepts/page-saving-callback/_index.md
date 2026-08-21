---
date: 2026-03-16
description: Узнайте, как реализовать обратный вызов сохранения страниц в Aspose.Tasks
  для .NET, позволяющий настраивать обработку потоков вывода многостраничных документов.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Реализовать обратный вызов сохранения страницы в Aspose.Tasks
url: /ru/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Реализация обратного вызова сохранения страниц в Aspose.Tasks

## Введение

В этом руководстве вы узнаете, как **реализовать обратный вызов сохранения страниц** в Aspose.Tasks для .NET. Эта мощная функция позволяет направлять каждую страницу многостраничного документа в поток по вашему выбору, предоставляя полный контроль над тем, как сохраняется вывод или обрабатывается дальше.

## Быстрые ответы
- **Что делает обратный вызов сохранения страниц?** Он захватывает каждую отрисованную страницу в отдельный поток, чтобы вы могли обрабатывать их по отдельности.  
- **В какой формат я могу экспортировать?** Любой формат, поддерживаемый `ImageSaveOptions`, например PNG, JPEG, PDF.  
- **Нужна ли лицензия?** Для использования в продакшене требуется действительная лицензия Aspose.Tasks.  
- **Можно ли использовать это с .NET Core?** Да, Aspose.Tasks полностью поддерживает .NET Core и .NET 5/6+.  
- **Является ли обратный вызов потокобезопасным?** Обратный вызов выполняется в том же потоке, который осуществляет рендеринг, поэтому применяются обычные правила потокобезопасности.

## Что такое **реализация обратного вызова сохранения страниц**?
Шаблон **реализации обратного вызова сохранения страниц** позволяет внедрить пользовательскую логику в конвейер сохранения Aspose.Tasks. Вместо прямой записи в файл вы получаете объект `Stream` для каждой страницы, что даёт возможность хранить его в памяти, загружать в облачное хранилище или выполнять дополнительную обработку.

## Почему экспортировать проект в PNG с использованием обратного вызова?
Экспорт проекта в PNG даёт растровое изображение каждой страницы диаграммы Ганта, что идеально подходит для отчётов, электронных писем или встраивания в веб‑страницы. Использование обратного вызова позволяет сохранять каждую страницу в отдельный `MemoryStream`, не создавая временных файлов на диске.

## Предварительные требования

1. **Знание C#** – базовое знакомство с классами, интерфейсами и потоками.  
2. **Aspose.Tasks для .NET** – скачайте и установите с [здесь](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider или любой совместимый с .NET редактор.

## Импорт пространств имён

Для начала импортируйте необходимые пространства имён:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Шаг 1: Создание объекта Project

Загрузите существующий файл MPP в экземпляр `Project`:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Шаг 2: Настройка Image Save Options

Настройте `ImageSaveOptions` для вывода PNG и присоедините пользовательский обратный вызов:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Pro tip:** Установка `RenderToSinglePage = false` гарантирует, что каждая страница диаграммы Ганта будет отрисована отдельно, что необходимо, чтобы обратный вызов получал отдельные потоки.

## Шаг 3: Сохранение проекта с обратным вызовом

Вызовите метод `Save`, передавая `Stream.Null`, поскольку реальные потоки предоставляются обратным вызовом:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Шаг 4: Обработка сохранённых потоков страниц

После завершения операции сохранения обратный вызов содержит коллекцию объектов `MemoryStream` — по одному на страницу. Теперь вы можете перебрать их:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Шаг 5: Реализация пользовательского обратного вызова сохранения страниц

Создайте sealed‑класс, реализующий `IPageSavingCallback`. Этот класс захватывает поток каждой страницы и сохраняет его в список для последующего использования.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Распространённые ошибки и устранение неполадок

| Проблема | Причина | Решение |
|----------|---------|---------|
| **Страницы не возвращаются** | `RenderToSinglePage` оставлен `true`. | Установите `RenderToSinglePage = false`, чтобы генерировать отдельные страницы. |
| **Потоки пусты** | `KeepStreamOpen` установлен `true` без последующего освобождения. | Оставьте `false` (по умолчанию) и позвольте обратному вызову автоматически закрывать потоки. |
| **Ошибки «Out‑of‑memory»** | Очень большие проекты генерируют множество PNG высокого разрешения. | Обрабатывайте потоки по одному или увеличьте лимиты памяти виртуальной машины. |

## Часто задаваемые вопросы

**Q1: Что такое обратный вызов сохранения страниц в Aspose.Tasks?**  
A: Обратный вызов сохранения страниц позволяет перехватывать процесс сохранения каждой страницы многостраничного документа, предоставляя пользовательский `Stream` для этой страницы.

**Q2: Можно ли использовать разные форматы для сохранения страниц с этим обратным вызовом?**  
A: Да. Изменив `SaveFileFormat`, вы можете экспортировать в PNG, JPEG, PDF, SVG и т.д.

**Q3: Совместим ли Aspose.Tasks с .NET Core?**  
A: Абсолютно. Aspose.Tasks поддерживает .NET Core, .NET 5 и .NET 6.

**Q4: Как обрабатывать ошибки во время процесса сохранения страниц?**  
A: Оберните логику обратного вызова в блоки try/catch и фиксируйте исключения. Метод `OnFinish` — хорошее место для финальной очистки.

**Q5: Где можно найти дополнительные ресурсы и поддержку по Aspose.Tasks?**  
A: Вы можете посетить [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для получения помощи, ознакомиться с документацией [здесь](https://reference.aspose.com/tasks/net/), либо изучить дополнительные возможности и варианты лицензирования на [веб‑сайте Aspose.Tasks](https://purchase.aspose.com/buy).

**Последнее обновление:** 2026-03-16  
**Тестировано с:** Aspose.Tasks 24.12 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}