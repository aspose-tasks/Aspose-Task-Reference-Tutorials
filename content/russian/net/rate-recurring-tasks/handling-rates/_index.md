---
title: Управление ставками проектов MS с помощью Aspose.Tasks для .NET
linktitle: Обработка скоростей в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Освойте управление ставками проектов MS с легкостью, используя Aspose.Tasks для .NET. Эффективно автоматизируйте задачи, чтобы упростить рабочие процессы проекта.
type: docs
weight: 10
url: /ru/net/rate-recurring-tasks/handling-rates/
---
## Введение
Добро пожаловать в наше руководство по управлению ставками MS Project с использованием Aspose.Tasks для .NET! В этом руководстве мы шаг за шагом проведем вас через весь процесс, гарантируя, что вы сможете эффективно управлять ставками в документах MS Project. Aspose.Tasks для .NET предоставляет мощные функции для программного управления файлами MS Project, что позволяет вам легко оптимизировать задачи управления проектами.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:
1. Установленная Visual Studio: убедитесь, что в вашей системе установлена Visual Studio.
2.  Библиотека Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks для .NET. Вы можете найти ссылку для скачивания[здесь](https://releases.aspose.com/tasks/net/).
3. Базовое понимание C#: ознакомьтесь с основами языка программирования C#.
## Импортировать пространства имен
Во-первых, вам необходимо импортировать необходимые пространства имен в ваш проект C#. Эти пространства имен обеспечат доступ к классам и методам, необходимым для обработки ставок MS Project.
## Шаг 1. Импортируйте пространство имен Aspose.Tasks.
```csharp
using Aspose.Tasks;
using System;

```
Теперь давайте разобьем приведенный пример на несколько шагов и подробно разберем каждый шаг.
## Шаг 1. Загрузите файл проекта
```csharp
// Путь к каталогу документов.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 На этом этапе мы загружаем существующий файл MS Project с именем «Project1.mpp», используя`Project` класс, предоставленный Aspose.Tasks.
## Шаг 2. Добавьте ресурс и настройте работу
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Здесь мы добавляем в проект новый ресурс с именем «Ресурс 1» и устанавливаем его тип «Работа». Также определяем продолжительность работы данного ресурса.
## Шаг 3. Установите стандартную ставку
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
На этом этапе мы устанавливаем стандартную ставку для ресурса на уровне 20 долларов в час.
## Шаг 4: Определите тарифные периоды
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Здесь мы определяем тарифные периоды для ресурса. Ставка 1 установлена с 1 января 2019 г. по 11 ноября 2019 г. с указанием стандартных ставок и ставок за сверхурочную работу.
## Шаг 5. Добавьте еще один тарифный период
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
На этом последнем этапе мы добавляем еще один тарифный период, начиная с 12 ноября 2019 г. по 31 декабря 2019 г., с другой стандартной ставкой и стоимостью за использование.
Поздравляем! Вы успешно обработали ставки MS Project с помощью Aspose.Tasks для .NET.
## Заключение
Программное управление ставками MS Project может значительно улучшить рабочий процесс управления проектами. С Aspose.Tasks для .NET у вас есть возможность эффективно автоматизировать задачи обработки ставок, экономя время и ресурсы.
## Часто задаваемые вопросы
### Вопрос: Может ли Aspose.Tasks обрабатывать сложные структуры проектов?
О: Да, Aspose.Tasks предоставляет надежные функции, позволяющие легко обрабатывать сложные структуры проектов.
### Вопрос: Совместим ли Aspose.Tasks со всеми версиями файлов MS Project?
О: Aspose.Tasks поддерживает различные версии файлов MS Project, обеспечивая совместимость на разных платформах.
### Вопрос: Могу ли я изменить существующие тарифы в файле MS Project с помощью Aspose.Tasks?
А: Абсолютно! Aspose.Tasks позволяет изменять существующие тарифы, добавлять новые тарифы и динамически управлять ими.
### Вопрос: Предлагает ли Aspose.Tasks поддержку расчета пользовательских ставок?
О: Да, вы можете реализовать собственные расчеты ставок с помощью Aspose.Tasks для удовлетворения конкретных требований проекта.
### Вопрос: Есть ли форум сообщества или поддержка для пользователей Aspose.Tasks?
 О: Да, вы можете посетить[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15)для обращения за помощью и взаимодействия с другими пользователями.