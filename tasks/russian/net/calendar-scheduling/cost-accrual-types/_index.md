---
date: 2026-07-05
description: Узнайте, как отслеживать бюджет проекта и управлять затратами проекта
  с помощью Aspose.Tasks для .NET. Определите cost accrual types для точного отслеживания
  расходов.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Cost Accrual Types в Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Отслеживание бюджета проекта с Cost Accrual Types в Aspose.Tasks
url: /ru/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Отслеживание бюджета проекта с типами начисления затрат в Aspose.Tasks

## Введение

Точное **отслеживание бюджета проекта** является основой успешного выполнения проекта. Когда информация о затратах фиксируется в нужные моменты, вы можете прогнозировать перерасход, корректировать ресурсы и информировать заинтересованные стороны. Aspose.Tasks для .NET предоставляет разработчикам тонкий контроль над начислением затрат, позволяя решать *когда* фиксировать затраты — будь то в начале работы, постоянно или только после завершения работы. Этот учебник проведёт вас через концепции, покажет, как установить тип начисления, и продемонстрирует лучшие практики надёжного отслеживания бюджета.

## Быстрые ответы
- **Какова основная цель типов начисления затрат?** Они определяют момент в жизненном цикле задачи, когда затраты признаются, обеспечивая точное отслеживание бюджета.  
- **Какое значение перечисления откладывает затраты до завершения работы?** `CostAccrualType.End`.  
- **Нужна ли лицензия для выполнения кода?** Да, для использования в продакшене требуется действительная лицензия Aspose.Tasks.  
- **Можно ли изменить типы начисления для многих ресурсов одновременно?** Да — пройдите в цикле по коллекции `Resources` и назначьте нужный тип.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое тип начисления затрат?
Тип **начисления затрат** сообщает Aspose.Tasks, когда применять стоимость ресурса к бюджету проекта. Он представлен перечислением `CostAccrualType` и может быть установлен для каждого ресурса или задачи. Выбор правильного типа гарантирует, что данные о затратах соответствуют политике выставления счетов вашей организации, будь то фиксация затрат в начале работы, пропорционально длительности или только после завершения.

## Почему отслеживать бюджет проекта с помощью типов начисления затрат?
Aspose.Tasks поддерживает **четыре** варианта начисления — `Start`, `Prorated`, `Duration` и `End` — охватывающие весь спектр типичных сценариев учёта в проектах. Выбор подходящего варианта позволяет согласовать признание затрат с контрактными циклами выставления счетов, уменьшить отклонения в финансовых отчётах и сформировать отчёты о затратах, которые легко интегрируются с ERP‑системами, при этом сохраняя низкое потребление памяти для крупных проектов.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть следующие предварительные требования:

### 1. Установите Aspose.Tasks для .NET
Чтобы начать, вам необходимо установить Aspose.Tasks для .NET в вашей среде разработки. Вы можете скачать библиотеку со [страницы загрузки](https://releases.aspose.com/tasks/net/) и следовать предоставленным инструкциям по установке.

### 2. Знание .NET Framework
Для работы с примерами в этом учебнике требуется базовое знание .NET Framework и языка программирования C#.

## Как установить тип начисления затрат для ресурса?

Загрузите проект, найдите целевой ресурс и назначьте желаемый `CostAccrualType`. Ниже представленный двухстрочный шаблон — стандартный подход: создать экземпляр `Project`, получить ресурс по его ID, затем установить `CostAccrualType`. Эта лаконичная последовательность гарантирует точное **отслеживание бюджета проекта** с момента добавления ресурса.

### Шаг 1: Импорт пространств имён
Начнём с импорта необходимых пространств имён для доступа к функционалу Aspose.Tasks в нашем .NET‑проекте:

```csharp

```

Теперь, когда пространства имён готовы, мы можем перейти к загрузке файла проекта.

### Шаг 2: Загрузка файла проекта
Класс `Project` представляет файл Microsoft Project и предоставляет доступ к его задачам, ресурсам и другим данным.

```csharp
var project = new Project("Project2.mpp");
```

Сначала нам нужно загрузить файл проекта в приложение. Мы создаём новый объект `Project` и инициализируем его путем к нашему файлу проекта.

### Шаг 3: Доступ к ресурсу
Коллекция `Resources` содержит все ресурсы, определённые в проекте. Метод `GetById` получает ресурс по его уникальному идентификатору.

```csharp
var resource = project.Resources.GetById(1);
```

Далее мы получаем ресурс, к которому хотим применить тип начисления затрат. Мы используем метод `GetById` коллекции `Resources` и передаём в него ID ресурса. Это демонстрирует **доступ к ресурсу по id**, распространённую задачу при автоматизации обновления затрат.

### Шаг 4: Установка типа начисления затрат
Метод `Set` присваивает значение полю ресурса.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Здесь мы устанавливаем тип начисления затрат для ресурса. В этом примере мы задаём значение `CostAccrualType.End`, что означает, что затраты не будут начисляться, пока оставшаяся работа не станет нулевой. Выбор `End` идеален, когда вы хотите **отслеживать бюджет проекта** только после полного завершения задачи.

### Шаг 5: Продолжение работы с проектом
После установки типа начисления затрат вы можете продолжать работу с проектом по мере необходимости, выполняя дополнительные операции или расчёты, такие как генерация отчётов о затратах, обновление назначений или экспорт файла.

## Распространённые подводные камни и профессиональные советы
- **Совет:** Всегда вызывайте `project.Save` после изменения типов начисления, чтобы сохранить изменения.  
- **Подводный камень:** Установка `CostAccrualType.Start` для ресурса, который никогда не начинает работу, приведёт к завышению бюджетных отчётов — сначала проверьте расписание задач.  
- **Совет:** Используйте `project.Resources.ToList()` когда необходимо пакетно обновлять множество ресурсов; это избегает повторных поисков в коллекции и повышает производительность на больших проектах.

## Часто задаваемые вопросы

**Q: Можно ли изменить тип начисления затрат для нескольких ресурсов одновременно?**  
A: Да, пройдите в цикле по `project.Resources` и назначьте желаемый `CostAccrualType` каждому ресурсу внутри цикла `foreach`.

**Q: Какие другие типы начисления затрат доступны, помимо `End`?**  
A: Aspose.Tasks предоставляет `Start`, `Prorated` и `Duration` — каждый соответствует различной стратегии выставления счетов.

**Q: Как определить текущий тип начисления затрат для конкретного ресурса?**  
A: Получите значение через `resource.Get(TskResource.CostAccrualType)`; он возвращает перечисление, представляющее текущую настройку.

**Q: Можно ли применить разные типы начисления затрат к разным задачам в одном проекте?**  
A: Конечно. И задачи, и ресурсы имеют свойство `CostAccrualType`, позволяющее независимо настраивать его для каждой сущности.

**Q: Поддерживает ли Aspose.Tasks пользовательские типы начисления затрат?**  
A: Нет, библиотека в текущий момент поддерживает только четыре встроенных типа; при необходимости пользовательскую логику нужно реализовывать внешне.

---

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.Tasks 24.8 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные учебные материалы

- [Календарь и планирование Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [Работа с тарифами MS Project в Aspose.Tasks для .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Легкое управление ресурсами MS Project с Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}