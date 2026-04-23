---
date: 2026-02-07
description: Узнайте, как задать код валюты Java в проектах Aspose.Tasks, изменить
  символ валюты и применить пользовательский формат валюты для файлов Microsoft Project.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Код валюты Java – Как задать в проектах Aspose.Tasks
url: /ru/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить код валюты в Aspose.Tasks – руководство по Java

## Introduction
В этом руководстве вы узнаете **как установить код валюты java** для файла Microsoft Project с помощью Aspose.Tasks Java API. Независимо от того, нужно ли вам *изменить валюту* для международных команд, скорректировать *символ валюты*, или применить **пользовательский формат валюты**, ниже приведённые шаги проведут вас через процесс с понятными объяснениями и готовым к запуску кодом.

## Quick Answers
- **Какая библиотека требуется?** Aspose.Tasks for Java.  
- **Могу ли я изменить символ валюты?** Да – используйте `CurrencySymbolPositionType` и `Prj.CURRENCY_SYMBOL`.  
- **Какие форматы файлов поддерживаются?** XML, MPP и многие другие через `SaveFileFormat`.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; лицензия требуется для продакшн.  
- **Сколько времени занимает реализация?** Около 5‑10 минут для базовой настройки.

## Как установить код валюты Java в Aspose.Tasks
Валюта проекта определяет, как отображаются значения затрат — код (например, `AUD`), количество десятичных знаков, символ (`$`) и позицию символа. Установка этих свойств гарантирует, что каждое поле, связанное со стоимостью (ставки ресурсов, бюджеты задач и т.д.), будет отображать правильный денежный формат для вашей аудитории.

## Почему использовать Aspose.Tasks для изменения валюты?
- **Не требуется установка Microsoft Project** — манипулируйте файлами на любом сервере.  
- **Полное покрытие API** — все поля, связанные с валютой, доступны через константы `Prj`.  
- **Кроссплатформенный** — работает на Windows, Linux и macOS с любой IDE, совместимой с Java.  
- **Высокая производительность** — быстро и надёжно обрабатывайте большие файлы проектов.  
- **Поддерживает пользовательский формат валюты** — вы можете задавать символы, количество десятичных знаков и позицию, соответствующие региональным стандартам.

## Prerequisites
Перед началом убедитесь, что у вас есть:

1. **Java Development Kit (JDK)** — версия 8 или выше.  
2. **Aspose.Tasks for Java** — скачайте последнюю JAR с [страницы загрузки Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **IDE** — Eclipse, IntelliJ IDEA или любой другой редактор по вашему выбору.  
4. **Папка с правом записи** — куда будет сохранён сгенерированный файл проекта.

## Import Packages
Сначала импортируйте классы, предоставляющие доступ к свойствам проекта и работе с файлами.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define the Data Directory
Укажите папку, содержащую ваши исходные файлы и куда будет записан результат.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Create a New Project Instance
Создайте новый объект `Project`. Этот объект представляет файл Microsoft Project в памяти.

```java
Project project = new Project();
```

### Step 3: Set Currency Properties
Здесь мы **устанавливаем валюту**: детали такие как код, количество цифр, символ и позиция символа.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Совет:** Если вам нужно **изменить валюту проекта** для существующего файла, просто загрузите его с помощью `new Project("file.mpp")` перед применением вышеуказанных настроек.

### Step 4: Save the Updated Project
Запишите проект обратно на диск в нужном формате. В этом примере мы используем формат XML, но вы также можете выбрать `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 5: Confirm Success
Выведите дружелюбное сообщение, чтобы знать, что операция завершилась без ошибок.

```java
System.out.println("Process completed Successfully");
```

## Common Issues & Solutions
| Проблема | Причина | Решение |
|----------|---------|---------|
| **`NullPointerException` on `project.save`** | `dataDir` не является действительным путём или нет прав на запись. | Убедитесь, что каталог существует и процесс Java имеет права записи. |
| **Currency symbol not showing** | Позиция символа установлена неверно для вашей локали. | Используйте `CurrencySymbolPositionType.Before`, если символ должен предшествовать сумме. |
| **Project file does not open in MS Project** | Сохранение в более старом формате с несовместимыми настройками. | Сохраните с помощью `SaveFileFormat.MPP` для полной совместимости с последними версиями MS Project. |

## Frequently Asked Questions

**Q: Могу ли я установить несколько валют в одном проекте, используя Aspose.Tasks?**  
A: Да, Aspose.Tasks позволяет работать с несколькими валютами в одном файле проекта, задавая свойства валюты для каждого ресурса или задачи.

**Q: Совместим ли Aspose.Tasks с разными версиями файлов Microsoft Project?**  
A: Абсолютно. Библиотека поддерживает файлы MPP от Project 2000 до последних релизов, а также XML и другие форматы.

**Q: Предоставляет ли Aspose.Tasks поддержку пользовательских форматов валют?**  
A: Да, вы можете задавать пользовательские символы, количество десятичных знаков и позицию, чтобы соответствовать любым региональным требованиям.

**Q: Могу ли я интегрировать Aspose.Tasks с другими библиотеками или фреймворками Java?**  
A: Конечно. API полностью на Java, поэтому он без проблем работает со Spring, Hibernate, Maven, Gradle и другими экосистемами.

**Q: Где я могу найти дополнительную поддержку или помощь по Aspose.Tasks?**  
A: Посетите [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для помощи сообщества или обратитесь к официальной документации для подробных ссылок на API.

## Conclusion
Теперь вы знаете **как установить код валюты java**, как **изменять значения валюты** и как **изменять символ валюты** с помощью Aspose.Tasks для Java. Эти возможности позволяют адаптировать данные о затратах для глобальных команд, генерировать отчёты, специфичные для локали, и поддерживать согласованность файлов проекта в разных странах.

---

**Последнее обновление:** 2026-02-07  
**Тестировано с:** Aspose.Tasks for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}