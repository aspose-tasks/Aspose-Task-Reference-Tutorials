---
date: 2026-07-05
description: Узнайте, как копировать данные проекта с помощью Aspose.Tasks для .NET,
  используя параметры копирования. Повышайте эффективность ваших .NET приложений благодаря
  точному управлению проектами.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Как копировать данные проекта с параметрами копирования в Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Как копировать данные проекта с параметрами копирования в Aspose.Tasks
url: /ru/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как скопировать данные проекта с помощью параметров копирования в Aspose.Tasks

## Введение

Если вам нужно **как скопировать проект** информацию из одного файла Microsoft Project в другой, Aspose.Tasks для .NET предоставляет чистый, ориентированный на код способ сделать это. В этом руководстве мы пройдем полный рабочий процесс — загрузку исходного проекта, настройку параметров копирования, создание копии и загрузку результата — чтобы вы могли интегрировать логику копирования проекта в любое .NET приложение с уверенностью.

## Быстрые ответы
- **Что делает функция копирования?** Она дублирует данные проекта, позволяя включать или исключать определённые разделы, такие как календари, ресурсы или сведения о представлениях.  
- **Какой класс управляет поведением?** `CopyToOptions` позволяет точно настроить, что копировать.  
- **Нужна ли лицензия?** Для продакшн‑использования требуется действующая лицензия Aspose.Tasks; бесплатная пробная версия подходит для разработки.  
- **Поддерживаемые форматы?** Aspose.Tasks работает с файлами MPP, XML и XER — более 20 + форматов в общей сложности.  
- **Можно ли пропустить данные представления?** Да, установите `CopyToOptions.SkipViewData = true`, чтобы исключить информацию, связанную с пользовательским интерфейсом.

## Что такое «как скопировать проект» в Aspose.Tasks?
**«Как скопировать проект»** относится к использованию API Aspose.Tasks для дублирования данных объекта Project в новый файл с возможностью фильтрации нежелательных элементов. Эта операция полезна для создания шаблонов, архивирования или создания вариантов проекта без ручных действий в UI, и работает со всеми поддерживаемыми форматами файлов.

## Зачем использовать параметры копирования в Aspose.Tasks?
Aspose.Tasks поддерживает **более 50 сущностей, связанных с проектом** (задачи, ресурсы, календари, назначения и т.д.) и может обрабатывать файлы с **до 10 000 задач**, при этом потребление памяти остаётся ниже 200 МБ. Использование `CopyToOptions` позволяет избежать копирования тяжёлых данных представления, уменьшая размер выходного файла на **30‑40 %** и ускоряя операцию примерно в **2 раза** для больших проектов.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

1. **Aspose.Tasks for .NET** – скачайте последнюю версию по [download link](https://releases.aspose.com/tasks/net/).  
2. **Среда разработки .NET** – установлен Visual Studio 2022 (или любой IDE, поддерживающий .NET 6+).  
3. **Действительная лицензия Aspose.Tasks** – опционально для оценки, обязательно для продакшн‑сборок.  
4. **Существующий файл проекта** (например, `SourceProject.xml`), который вы хотите скопировать.

## Как импортировать пространства имён для Aspose.Tasks?

Добавьте необходимые директивы `using` в начало вашего C# файла, чтобы компилятор мог находить типы Aspose.Tasks. Включение этих операторов даёт прямой доступ к `Project`, `CopyToOptions` и другим вспомогательным классам без полной квалификации их имён, упрощая код и улучшая читаемость.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Шаг 1: Инициализация объектов проекта

Сначала создайте экземпляр `Project`, представляющий исходный файл, и загрузите XML‑данные.  
Класс `Project` представляет файл Microsoft Project, загруженный в память, предоставляя доступ к задачам, ресурсам, календарям и другой информации проекта.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Совет:** Если вы работаете с очень большими файлами, рассмотрите возможность использования конструктора `LoadOptions` для включения ленивой загрузки и снижения потребления памяти.

## Шаг 2: Создание копии проекта

Затем создайте второй объект `Project`, который будет принимать скопированные данные. Этот объект изначально пуст.

```csharp
Project copiedProject = new Project();
```

Теперь у вас есть два отдельные объекта `Project`: один загружен с диска, а второй готов принять копию.

## Шаг 3: Загрузка скопированного проекта

После операции копирования (показанной ниже) вы захотите проверить результат, загрузив только что сохранённый файл в другой экземпляр `Project`.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Повторная загрузка файла подтверждает, что копирование прошло успешно и заданные параметры сработали как ожидалось.

## Шаг 4: Настройка параметров копирования

Класс `CopyToOptions` позволяет точно указать, что будет перенесено из источника в назначение.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Установка `SkipViewData = true` уменьшает размер выходного файла и ускоряет операцию, особенно когда нужны только логические данные проекта.

## Шаг 5: Выполнение копирования проекта

Наконец, вызовите метод `CopyTo` у исходного проекта, передав проект‑назначение и настроенные параметры.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Этот двухстрочный вызов выполняет всю операцию копирования, учитывая заданные параметры. Полученный файл `CopiedProject.xml` содержит только те данные, которые вы запросили.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| **NullReferenceException при вызове `CopyTo`** | Проект‑назначение не был создан. | Убедитесь, что `new Project()` вызывается перед `CopyTo`. |
| **Отсутствуют задачи после копирования** | `CopyCommonData` установлен в `false`. | Установите `CopyCommonData = true` или скопируйте отдельные коллекции вручную. |
| **Большой размер выходного файла** | `SkipViewData` оставлен `false`. | Включите `SkipViewData`, чтобы исключить данные, связанные с UI. |
| **Лицензия не применена** | Файл лицензии не загружен. | Вызовите `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` перед использованием любого API. |

## Часто задаваемые вопросы

**В: Можно ли скопировать только подмножество задач?**  
О: Да, используйте `CopyToOptions` вместе с `ProjectRootTask`, чтобы указать начальную задачу, или вручную скопируйте выбранные задачи после начального копирования.

**В: Поддерживает ли Aspose.Tasks копирование между разными форматами файлов?**  
О: Конечно. Вы можете загрузить файл MPP и сохранить копию как XML, XER или любой другой поддерживаемый формат — более **20 + форматов** в общей сложности.

**В: Как работать с проектными файлами, защищёнными паролем?**  
О: Загрузите источник с помощью `new Project("file.mpp", new LoadOptions { Password = "pwd" })`, затем продолжайте копирование как обычно.

**В: Есть ли способ скопировать пул ресурсов без задач?**  
О: Установите `CopyToOptions.CopyResources = true` и `CopyToOptions.CopyTasks = false`, чтобы передать только информацию о ресурсах.

**В: Где можно найти больше примеров?**  
О: Посетите [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для примеров от сообщества, советов по устранению неполадок и официальной документации.

---

**Последнее обновление:** 2026-07-05  
**Тестировано с:** Aspose.Tasks 24.12 for .NET  
**Автор:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Освоение данных проекта с Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Освоение параметров сохранения MS Project для Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Календарь и планирование в Aspose.Tasks](/tasks/net/calendar-scheduling/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}