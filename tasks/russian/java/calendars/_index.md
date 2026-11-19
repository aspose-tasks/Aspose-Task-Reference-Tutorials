---
date: 2026-11-19
description: Узнайте, как создать custom calendar Java с использованием Aspose.Tasks.
  Это руководство показывает, как define working days, set working hours и modify
  MS Project calendars programmatically.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: Календари
og_description: Узнайте, как создать custom calendar Java с Aspose.Tasks. Освойте
  defining working days, setting working hours и modifying MS Project calendars efficiently.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Как создать custom calendar Java с Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: Как создать custom calendar Java с Aspose.Tasks
url: /ru/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Календари

## Введение

Если вы разработчик Java и хотите **create custom calendar Java** решения, вы попали в нужное место. Этот центр собирает все учебные материалы Aspose.Tasks for Java, демонстрирующие, как **define working days MS Project**, **set working hours MS Project**, и программно настраивать параметры календаря. Независимо от того, создаёте ли вы новый движок планирования или расширяете существующий план, освоение этих API даёт точный контроль над шаблонами рабочих дней, праздниками и пользовательскими сменами — без необходимости открывать пользовательский интерфейс MS Project.

## Быстрые ответы
- **Какова основная цель определения будних дней?**  
  Сообщить MS Project, какие дни являются рабочими и какие у них рабочие часы.  
- **Какая библиотека обрабатывает определение будних дней в Java?**  
  Aspose.Tasks for Java предоставляет удобный API для работы с календарями.  
- **Нужна ли лицензия?**  
  Бесплатная оценочная лицензия подходит для тестирования; для продакшн требуется коммерческая лицензия.  
- **Могу ли я определить несколько календарей для разных команд?**  
  Да — каждый проект может содержать несколько календарей, каждый со своими настройками будних дней.  
- **Есть ли пример проекта для начала?**  
  Учебник «Define Weekdays in Calendar», ссылка ниже, содержит готовый к запуску пример.

## Как создать пользовательский календарь Java?

Загрузите проект, создайте или получите календарь, добавьте определения будних дней и сохраните файл — всё в нескольких вызовах API. Такой подход устраняет ручные шаги в UI, позволяет автоматизировать создание календарей в десятках проектов и обеспечивает согласованные шаблоны рабочих дней по всей организации.

## Что такое класс Project?

Класс `Project` — центральный объект для загрузки, редактирования и сохранения файлов MS Project. Он содержит коллекции задач, ресурсов и календарей, предоставляя методы, позволяющие программно читать и изменять любой аспект проекта. С помощью этого класса вы можете получить доступ к коллекции календарей проекта, настроить рабочее время и сохранить изменения в файл MPP или XML.

## Как определить будние дни в календарях MS Project?

Класс `Project` представляет файл MS Project и предоставляет доступ к его структурам данных. Объект `Calendar` хранит определения рабочего времени и исключения для проекта. Загрузите ваш проект с помощью `new Project("myproject.mpp")`, получите (или создайте) объект `Calendar`, а затем вызовите `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. Эта единственная строка создаёт запись рабочего дня понедельника с 8‑часовой сменой. Повторите для остальных дней и, наконец, сохраните проект с помощью `project.save("updated.mpp")`. Такой лаконичный шаблон позволяет определять, изменять или удалять будние дни всего в нескольких вызовах API, исключая необходимость ручного взаимодействия с UI.

## Что такое объект WeekDay?

Объект `WeekDay` представляет одну запись дня недели внутри календаря. Он хранит информацию о том, является ли день рабочим, интервалы рабочего времени для этого дня и флаги поведения по умолчанию. Вы можете привязать один или несколько интервалов `WorkingTime` для моделирования раздельных смен, установить день как нерабочий или унаследовать значения по умолчанию от родительского календаря.

## Как определить рабочие дни в MS Project?

Вы определяете рабочие дни, добавляя объекты `WeekDay` в коллекцию `WeekDays` календаря. Каждый `WeekDay` указывает, является ли день рабочим и какие временные диапазоны считаются рабочими. Например, чтобы сделать субботу полуднём, добавьте `WeekDay` с единственным `WorkingTime` от 10:00 до 14:00. API автоматически обновляет расчёты расписания проекта.

## Как установить рабочие часы в MS Project?

Установите рабочие часы, создав один или несколько интервалов `WorkingTime` для каждого `WeekDay`. `WorkingTime` принимает значения начала часа, начала минуты, конца часа и конца минуты. Вы можете назначать несколько интервалов одному дню для моделирования раздельных смен (например, 08:00‑12:00 и 13:00‑17:00). После настройки всех будних дней вызовите `project.save(...)`, чтобы сохранить изменения.

## Почему стоит использовать Aspose.Tasks for Java для определения будних дней?

- **Full API control** – Нет ограничений UI; вы можете программно создавать, изменять или удалять записи о будних днях.  
- **Cross‑platform** – Работает в любой среде, совместимой с JVM, от настольных приложений до облачных сервисов.  
- **Precision** – Устанавливайте разные рабочие часы для каждого буднего дня, добавляйте исключения для праздников и синхронизируйте календари между несколькими проектами.  
- **Performance** – Обрабатывайте проекты с более чем 500 задачами и календари, содержащие более 100 недель, без загрузки полного UI, достигая времени конвертации менее 2 секунд на стандартном сервере 2.5 GHz (утверждение основано на бенчмарке Aspose).  
- **Broad format support** – Aspose.Tasks поддерживает более 30 API, связанных с календарями, и может импортировать/экспортировать более 20 форматов файлов, обеспечивая бесшовную интеграцию с существующими конвейерами данных проектов.

## Предварительные требования
- Установлен Java 8 или новее.  
- Библиотека Aspose.Tasks for Java (скачана с сайта Aspose или добавлена через Maven/Gradle).  
- Действительная лицензия Aspose.Tasks (оценочная лицензия подходит для обучения).  

## Управление свойствами календаря MS Project в Aspose.Tasks

Откройте полный потенциал управления свойствами календаря MS Project в Java с помощью Aspose.Tasks. Наш учебник проведёт вас через тонкости управления календарём, предлагая ценные инсайты по настройке и оптимизации. От корректировки рабочих часов до определения специальных дат — вы освоите всё.

Готовы взять под контроль сроки вашего проекта? [Explore the tutorial here](./properties/).

## Создание календарей MS Project с помощью Aspose.Tasks

Легко оптимизируйте управление проектами, создавая календари MS Project с помощью Aspose.Tasks for Java. Наш учебник упрощает процесс, позволяя быстро настроить календари под уникальные потребности вашего проекта. Сделайте первый шаг к эффективному планированию и организации.

Готовы создать календари с лёгкостью? [Check out the tutorial](./create/).

## Определение будних дней в календаре с помощью Aspose.Tasks

Настройте календари MS Project, определяя будние дни с помощью Aspose.Tasks for Java. Этот учебник проведёт вас через процесс адаптации рабочих дней и времени, предоставляя гибкость, необходимую для успешного управления проектом. Сделайте ваши календари работающими на вас.

Готовы определить будние дни без усилий? [Get started here](./define-weekdays/).

Переходя по этим учебникам, вы откроете дополнительные темы, такие как извлечение рабочих часов, создание стандартного календаря, чтение рабочих недель и обновление календарей в формат MPP. Каждый учебник создан, чтобы предоставить практические знания, позволяющие сразу применять их в ваших Java‑проектах.

## Получение рабочих часов из календаря с помощью Aspose.Tasks

Упростите задачи управления проектом, извлекая рабочие часы из календарей MS Project с помощью Aspose.Tasks for Java. Этот учебник даст вам навыки, необходимые для эффективной оптимизации сроков проекта.

Готовы извлечь рабочие часы без усилий? [Explore the tutorial](./working-hours/).

## Создание стандартного календаря в Aspose.Tasks

Повышайте возможности управления проектами, изучая, как создать стандартный календарь MS Project в Java с помощью Aspose.Tasks. Пошаговый учебник гарантирует, что вы сможете внедрить стандартизированный подход к срокам проекта.

Готовы создать стандартный календарь? [Check out the tutorial](./make-standard/).

## Чтение рабочих недель из календаря MS Project с Aspose.Tasks

Получите полное представление о чтении рабочих недель из календарей MS Project с помощью Aspose.Tasks for Java. Этот учебник предлагает подробные инструкции, позволяющие эффективно управлять расписанием проекта.

Готовы читать рабочие недели без усилий? [Get started here](./read-work-weeks/).

## Обновление календарей MS Project до формата MPP с Aspose.Tasks

Легко обновляйте календари MS Project до формата MPP, используя Aspose.Tasks for Java. Этот учебник предоставляет бесшовный подход, гарантируя, что ваши данные проекта находятся в правильном формате для оптимальной совместимости.

Готовы обновить календари до формата MPP? [Explore the tutorial](./update-to-mpp/).

Откройте полный потенциал Aspose.Tasks for Java и поднимите навыки управления проектами на новый уровень. Каждый учебник разработан для разработчиков всех уровней, обеспечивая плавный процесс обучения. Погрузитесь и революционизируйте ваш путь управления Java‑проектами уже сегодня!

## Учебники по календарям
### [Управление свойствами календаря MS Project в Aspose.Tasks](./properties/)
Узнайте, как управлять свойствами календаря MS Project в Java с помощью Aspose.Tasks. Предоставляет пошаговое руководство по работе с календарём в ваших Java‑приложениях.
### [Создание календарей MS Project с Aspose.Tasks](./create/)
Узнайте, как создавать календари MS Project с помощью Aspose.Tasks for Java. Упростите управление проектами.
### [Определение будних дней в календаре с Aspose.Tasks](./define-weekdays/)
Узнайте, как определять будние дни в календаре MS Project с помощью Aspose.Tasks for Java. Настраивайте рабочие дни и время без усилий.
### [Получение рабочих часов из календаря с Aspose.Tasks](./working-hours/)
Извлекайте рабочие часы из календарей MS Project легко с Aspose.Tasks for Java. Упростите задачи управления проектом.
### [Создание стандартного календаря в Aspose.Tasks](./make-standard/)
Узнайте, как создать стандартный календарь MS Project в Java с помощью Aspose.Tasks. Расширьте возможности управления проектами с этим пошаговым учебником.
### [Чтение рабочих недель из календаря MS Project с Aspose.Tasks](./read-work-weeks/)
Узнайте, как читать рабочие недели из календаря MS Project с помощью Aspose.Tasks for Java. Получите пошаговые инструкции в этом всестороннем учебнике.
### [Обновление календарей MS Project до формата MPP без усилий с Aspose.Tasks for Java](./update-to-mpp/)
Узнайте, как без усилий обновлять календари MS Project до формата MPP с помощью Aspose.Tasks for Java.

## Часто задаваемые вопросы

**Q: Могу ли я задать разные рабочие часы для каждого буднего дня?**  
A: Да. Aspose.Tasks позволяет задавать время начала и окончания отдельно для каждого дня недели с понедельника по воскресенье.

**Q: Как обрабатывать праздники или нерабочие дни?**  
A: После определения будних дней вы можете добавить исключения (даты), чтобы отметить праздники или пользовательские нерабочие периоды.

**Q: Можно ли скопировать определение буднего дня из одного календаря в другой?**  
A: Конечно. Вы можете получить объект `WeekDay` из существующего календаря и добавить его в другой экземпляр календаря.

**Q: Нужно ли перезагружать проект после обновления будних дней?**  
A: Нет. Изменения применяются непосредственно к объекту `Project` в памяти; просто сохраните проект, когда закончите.

**Q: Какая версия Aspose.Tasks требуется для работы с будними днями?**  
A: Все последние версии (20.10 и новее) поддерживают полный набор API для будних дней. Мы рекомендуем использовать последнюю стабильную версию для лучшей производительности.

---

**Last Updated:** 2026-11-19  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Связанные учебники

- [Добавить календарь в проект с Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Определить рабочие дни и часы с Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Создать пользовательские исключения календаря с Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}