---
date: 2026-02-10
description: Узнайте, как получать значения валют, читать файл MS Project и конвертировать
  проектный файл в Java с помощью Aspose.Tasks. Пошаговое руководство по извлечению
  цифр валюты.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как получить валюту из MS Project с помощью Aspose.Tasks
url: /ru/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как получить валюту из MS Project с помощью Aspose.Tasks

## Введение
Если вы задаётесь вопросом **как получить валюту** из файла Microsoft Project, вы попали в нужное место. В этом полном руководстве вы узнаете **как работать со значениями валюты ms project** с использованием библиотеки Aspose.Tasks для Java. Независимо от того, создаёте ли вы инструмент отчётности, утилиту миграции или просто нужно прочитать настройки валюты из **java project file**, это руководство проведёт вас через каждый шаг — от загрузки файла *.mpp* до извлечения цифр валюты. К концу вы будете уверенно обрабатывать данные валюты ms project в своих приложениях.

## Быстрые ответы
- **Какая библиотека читает файлы MS Project?** Aspose.Tasks for Java.  
- **Сколько строк кода нужно, чтобы получить цифры валюты?** Всего три лаконичные строки после загрузки проекта.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшна требуется коммерческая лицензия.  
- **Какая версия Java поддерживается?** Java 8 или выше (любой JDK, который поддерживает Aspose.Tasks).  
- **Можно ли получить другие свойства Project?** Да — Aspose.Tasks предоставляет полный набор полей Project (например, дату начала, ставки затрат и т.д.).

## Что такое ms project currency?
`ms project currency` относится к числовой точности (количеству знаков после запятой), которую Microsoft Project использует при отображении денежных значений. Он хранится в файле Project как свойство **CURRENCY_DIGITS** и определяет, будут ли суммы отображаться как целые числа, с одним знаком после запятой, двумя знаками и т.д.

## Почему стоит использовать Aspose.Tasks для работы с ms project currency?
- **No Microsoft Project installation required** – без необходимости установки Microsoft Project — работайте напрямую с файлами *.mpp* на любой платформе, поддерживающей Java.  
- **Strong type safety** – обеспечение строгой типовой безопасности — API возвращает строго типизированные значения, уменьшая ошибки парсинга.  
- **Performance‑optimized** – оптимизировано по производительности — быстро загружайте большие проекты и извлекайте только нужные поля.  
- **Cross‑platform** – кросс‑платформенно — работает на Windows, Linux или macOS без модификаций.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

1. **Java Development Environment** – установлен и настроен JDK 8 или новее.  
2. **Aspose.Tasks for Java** – скачайте последнюю JAR‑файл с официального сайта: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – базовые знания Java — вы должны уметь создавать Java‑проект, добавлять внешние библиотеки и запускать `main`‑метод.  

## Импорт пакетов
Сначала импортируйте необходимые классы.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Шаг 1: Определите каталог данных
Укажите папку, содержащую ваш **java project file** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Замените `"Your Data Directory"` на абсолютный или относительный путь, где находится `project.mpp`.

## Шаг 2: Загрузите файл MPP
Теперь мы посмотрим **как загрузить mpp** файлы с помощью Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Убедитесь, что имя файла точно совпадает; иначе будет выброшено `IOException`.

## Шаг 3: Получите цифры валюты
После загрузки проекта извлечение цифр **ms project currency** — это однострочник:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Вызов возвращает `Integer`, представляющий количество знаков после запятой (например, `2` для центов). Значение выводится в консоль, но вы также можете сохранить его в переменной для дальнейшей обработки.

## Распространённые проблемы и советы
- **File not found** – проверьте путь `dataDir` и убедитесь, что имя файла указано правильно, включая расширение `.mpp`.  
- **Unsupported file version** – Aspose.Tasks поддерживает форматы Project 2000‑2024; более старые или повреждённые файлы могут потребовать конвертации.  
- **License not set** – во время разработки работает пробная версия, но для продакшна необходимо применить действующую лицензию, чтобы избежать водяных знаков оценки.

## Часто задаваемые вопросы

**Q: Can Aspose.Tasks handle other Project attributes besides currency digits?**  
A: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate various aspects of Project files, such as tasks, resources, and custom fields.

**Q: Is Aspose.Tasks suitable for enterprise‑level applications?**  
A: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade projects, offering high performance and scalability.

**Q: Does Aspose.Tasks support cross‑platform development?**  
A: Yes, you can use Aspose.Tasks for Java on any platform that supports the Java Runtime Environment (Windows, Linux, macOS).

**Q: Can I try Aspose.Tasks before purchasing?**  
A: Yes, you can download a free trial version from [here](https://releases.aspose.com/).

**Q: Where can I get support for Aspose.Tasks?**  
A: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Заключение
Теперь вы знаете **как получить цифры валюты** из файла MS Project с помощью Aspose.Tasks для Java. Процесс прост: загрузите проект, вызовите `project.get(Prj.CURRENCY_DIGITS)`, и используйте результат в вашем приложении. Не стесняйтесь исследовать другие свойства проекта тем же способом и интегрировать эту логику в более крупные решения для отчётности или миграции.

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.Tasks for Java (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}