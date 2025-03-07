---
title: Сохраните параметры проекта MS Primavera с помощью Aspose.Tasks
linktitle: Параметры сохранения Primavera для Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как легко сохранить параметры MS Project для Primavera с помощью Aspose.Tasks для .NET. Следуйте нашему пошаговому руководству.
weight: 14
url: /ru/net/saving-options/primavera-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сохраните параметры проекта MS Primavera с помощью Aspose.Tasks

## Введение
Aspose.Tasks for .NET — это мощная библиотека, которая позволяет разработчикам беспрепятственно работать с файлами Microsoft Project в своих .NET-приложениях. Одной из ключевых функций, которые он предлагает, является возможность сохранять параметры MS Project для Primavera, популярного программного обеспечения для управления проектами. В этом уроке мы углубимся в то, как этого добиться с помощью Aspose.Tasks.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
- Базовое понимание C# и .NET framework.
-  Aspose.Tasks для .NET установлен в вашей среде разработки. Если нет, то вы можете скачать его[здесь](https://releases.aspose.com/tasks/net/).
- Образец файла MS Project для экспериментов.

## Импортировать пространства имен
Сначала давайте импортируем необходимые пространства имен в наш код C#:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Шаг 1. Загрузите файл проекта MS
 Начните с загрузки файла MS Project, с которым вы собираетесь работать, в приложение C#. Вы можете сделать это, используя`Project` класс, предоставленный Aspose.Tasks.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Шаг 2. Определите параметры сохранения Primavera
Затем создайте параметры сохранения Primavera и настройте их в соответствии со своими требованиями. Этот шаг включает в себя указание таких параметров, как префикс идентификатора действия, суффикс, приращение и необходимость перенумерации идентификаторов действия.
```csharp
var options = new PrimaveraSaveOptions
{
    ActivityIdPrefix = "TEST",
    ActivityIdSuffix = 10000,
    ActivityIdIncrement = 5,
    RenumberActivityIds = true
};
```
## Шаг 3. Сохраните параметры проекта MS для Primavera
 Теперь, когда вы загрузили файл проекта и определили параметры сохранения Primavera, пришло время сохранить параметры Primavera. Использовать`Save` метод, предусмотренный`Project` класс, передав желаемый путь к выходному файлу и параметры сохранения Primavera.
```csharp
project.Save(DataDir + "WorkWithPrimaveraSaveOptions_out.xer", options);
```

## Заключение
В заключение, использование Aspose.Tasks для .NET позволяет разработчикам беспрепятственно манипулировать файлами MS Project, включая параметры сохранения для Primavera. Следуя шагам, описанным в этом руководстве, вы сможете эффективно интегрировать эту функцию в свои приложения .NET.
## Часто задаваемые вопросы
### Вопрос: Могу ли я настроить другие параметры, помимо идентификаторов активности, при сохранении параметров MS Project для Primavera?
О: Да, Aspose.Tasks предоставляет широкий спектр возможностей настройки, включая распределение ресурсов и планирование задач.
### Вопрос: Поддерживает ли Aspose.Tasks другое программное обеспечение для управления проектами, кроме Primavera?
О: Да, Aspose.Tasks поддерживает различные форматы, совместимые с популярными инструментами управления проектами, такими как Oracle Primavera, Microsoft Project Server и другими.
### Вопрос: Подходит ли Aspose.Tasks как для небольших, так и для корпоративных проектов?
О: Конечно, Aspose.Tasks предназначен для удовлетворения потребностей разработчиков, работающих над проектами любого размера, предлагая масштабируемость и надежную производительность.
### Вопрос: Могу ли я бесплатно попробовать Aspose.Tasks перед покупкой?
 О: Да, вы можете скачать бесплатную пробную версию Aspose.Tasks с сайта[здесь](https://releases.aspose.com/) изучить его особенности и возможности.
### Вопрос: Где я могу получить поддержку, если у меня возникнут проблемы или возникнут вопросы при использовании Aspose.Tasks?
 О: Вы можете обратиться за помощью к сообществу Aspose.Tasks и команде поддержки на[Форум](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
