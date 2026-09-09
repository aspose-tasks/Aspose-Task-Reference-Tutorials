---
date: 2026-09-09
description: Узнайте, как изменить символ валюты в проектах Aspose.Tasks на Java,
  установить коды валют, настроить символы и применить пользовательские форматы для
  файлов Microsoft Project.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Установить свойства валюты в проектах Aspose.Tasks
og_description: Как изменить символ валюты в Aspose.Tasks с помощью Java. Узнайте
  пошаговые инструкции, требования и советы по настройке форматирования стоимости
  проекта.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Как изменить символ валюты в Aspose.Tasks – руководство по Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Как изменить символ валюты в проектах Aspose.Tasks – руководство по Java
url: /ru/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как изменить символ валюты в Aspose.Tasks – руководство для Java

## Введение
В этом руководстве вы узнаете **как изменить символ валюты** для файла Microsoft Project, используя Aspose.Tasks Java API. Независимо от того, готовите ли вы отчёты для зарубежного клиента, консолидируете бюджеты в нескольких регионах или просто нужно соответствовать бухгалтерским стандартам вашей компании, настройка символа валюты гарантирует, что каждое поле, связанное с затратами, отображает правильный денежный знак. Руководство проходит каждый шаг, от настройки среды разработки до сохранения изменений в новом или существующем файле проекта.

## Быстрые ответы
- **Какая библиотека требуется?** Aspose.Tasks for Java.  
- **Могу ли я изменить символ валюты?** Да – установите `Prj.CURRENCY_SYMBOL` и выберите `CurrencySymbolPositionType`.  
- **Какие форматы файлов поддерживаются?** XML, MPP и многие другие через `SaveFileFormat`.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; лицензия требуется для продакшн.  
- **Сколько времени занимает реализация?** Около 5‑10 минут для базовой настройки.

## Как изменить символ валюты в Aspose.Tasks с помощью Java?
Загрузите целевой проект (или создайте новый), установите нужные свойства валюты и сохраните файл. Вся операция состоит из трёх вызовов API: создать или загрузить объект `Project`, задать код валюты, символ и позицию, затем вызвать `project.save`. Такой подход работает как для новых проектов, так и для существующих файлов без необходимости установки Microsoft Project.

## Почему использовать Aspose.Tasks для изменения валюты?
Aspose.Tasks предоставляет **полное покрытие API более чем 30‑ти свойств, связанных с валютой**, позволяя определить код, символ, количество десятичных знаков и позицию в одном месте. Библиотека обрабатывает многосотстраничные файлы Project менее чем за секунду на типичном серверном оборудовании и работает на Windows, Linux и macOS без дополнительных зависимостей.

## Требования
Прежде чем начать, убедитесь, что у вас есть:

1. **Java Development Kit (JDK) 8 или выше** – API требует как минимум JDK 8.  
2. **Aspose.Tasks for Java** – скачайте последнюю JAR с [страницы загрузки Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA или любой редактор, поддерживающий Java.  
4. **Папка с правом записи** – куда будет сохранён сгенерированный файл проекта.

## Импорт пакетов
Следующие классы дают доступ к свойствам проекта, работе с файлами и настройкам валюты.

`Project` – представляет файл Microsoft Project в памяти.  
`Prj` – содержит константы для всех свойств уровня проекта, включая поля валюты.  
`CurrencySymbolPositionType` – перечисляет возможные позиции символа валюты (до или после суммы).

Эти импорты необходимы перед тем, как любой код сможет работать с проектом.

## Пошаговое руководство

### Шаг 1: Определите каталог данных
Выберите папку, в которой находятся исходные файлы и куда будет записан вывод. Убедитесь, что каталог существует и ваш процесс Java имеет права на запись.

### Шаг 2: Создайте новый экземпляр проекта
Класс `Project` — это объект верхнего уровня Aspose.Tasks, представляющий один файл Project в памяти. Его создание создает пустой проект, готовый к настройке.

### Шаг 3: Установите свойства валюты
Здесь вы настраиваете код валюты, количество десятичных знаков, сам символ и позицию символа.

- **Currency code** – трехбуквенный код ISO 4217, например `AUD` или `USD`.  
- **Decimal digits** – обычно 2 для большинства валют.  
- **Currency symbol** – символ или строка, отображаемая вместе со суммами, например `$` или `€`.  
- **Symbol position** – `CurrencySymbolPositionType.Before` размещает символ перед числом; `After` — после.

Эти настройки влияют на каждое поле, связанное с затратами (ставки ресурсов, бюджеты задач и т.д.) в проекте.

> **Pro tip:** Если вам нужно изменить валюту в существующем файле, загрузите его с помощью `new Project("file.mpp")` перед применением вышеуказанных настроек.

### Шаг 4: Сохраните обновлённый проект
Запишите проект обратно на диск в нужном формате. Формат XML читаем человеком, а `SaveFileFormat.MPP` сохраняет полную совместимость с Microsoft Project.

### Шаг 5: Подтвердите успех
Выведите короткое сообщение или запись в журнал, чтобы знать, что операция завершилась без ошибок. Это особенно полезно в автоматизированных конвейерах.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|---------|
| **`NullPointerException` on `project.save`** | `dataDir` не является действительным путём или у него нет прав на запись. | Убедитесь, что каталог существует и ваш процесс Java имеет доступ на запись. |
| **Символ валюты не отображается** | Позиция символа установлена неверно для вашей локали. | Используйте `CurrencySymbolPositionType.Before`, если символ должен предшествовать сумме. |
| **Файл проекта не открывается в MS Project** | Сохранение в более старом формате с несовместимыми настройками. | Сохраните с помощью `SaveFileFormat.MPP` для полной совместимости с последними версиями MS Project. |

## Часто задаваемые вопросы

**Q: Можно ли установить несколько валют в одном проекте с помощью Aspose.Tasks?**  
**A:** Да, вы можете назначать разные настройки валюты отдельным ресурсам или задачам, изменяя их соответствующие поля стоимости после определения валюты уровня проекта.

**Q: Совместим ли Aspose.Tasks с разными версиями файлов Microsoft Project?**  
**A:** Абсолютно. Библиотека поддерживает файлы MPP от Project 2000 до последних выпусков, а также XML и другие форматы обмена.

**Q: Предоставляет ли Aspose.Tasks поддержку пользовательских форматов валют?**  
**A:** Да, вы можете определить пользовательские символы, количество десятичных знаков и позицию, чтобы соответствовать любым региональным требованиям, и эти настройки сохраняются в файле.

**Q: Можно ли интегрировать Aspose.Tasks с другими Java‑фреймворками?**  
**A:** Конечно. API полностью на Java, поэтому он без проблем работает со Spring, Hibernate, Maven, Gradle и другими экосистемами.

**Q: Где можно найти дополнительную помощь или примеры?**  
**A:** Посетите [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для получения помощи от сообщества или обратитесь к официальной документации для подробных ссылок на API.

## Заключение
Теперь вы знаете **как изменить символ валюты** в проектах Aspose.Tasks с использованием Java, как задать код валюты, настроить количество десятичных знаков и применить пользовательский символ. Эти возможности позволяют генерировать отчёты о затратах, специфичные для локали, согласовывать бюджеты проектов с региональными бухгалтерскими стандартами и поддерживать согласованность файлов Microsoft Project в глобальных командах.

---

**Последнее обновление:** 2026-09-09  
**Тестировано с:** Aspose.Tasks for Java 24.11  
**Автор:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Связанные руководства

- [Свойства проекта Java – Извлечение символа валюты из MPP с помощью Aspose.Tasks для Java](/tasks/java/currency/currency-symbols/)
- [Чтение свойств валюты Java с проектами Aspose.Tasks](/tasks/java/currency-properties/read-properties/)
- [Управление кодами валют Java с Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}