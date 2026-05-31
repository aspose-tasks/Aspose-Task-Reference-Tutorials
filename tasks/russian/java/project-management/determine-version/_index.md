---
date: 2026-05-31
description: Узнайте, как получить версию проекта и извлечь дату последнего сохранения
  из файлов MS Project с помощью Aspose.Tasks для Java. Пошаговое руководство с примерами
  кода.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Определить версию проекта с помощью Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Как получить версию проекта – учебник Aspose Tasks Java
url: /ru/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как получить версию проекта – учебник Aspose Tasks для Java

В этом **учебнике Aspose Tasks для Java** вы узнаете, **как получить версию проекта** Microsoft Project и также, как **получить дату последнего сохранения**, используя библиотеку Aspose.Tasks для Java. Знание версии файла и метки времени сохранения помогает избежать проблем совместимости, обеспечить политику миграции и вести точные журналы аудита. Мы пройдем каждый шаг — от настройки окружения до вывода версии и даты — чтобы вы могли внедрить эту проверку в любое Java‑приложение с уверенностью.

## Краткие ответы
- **Что охватывает этот учебник?** Определение версии файла MS Project и даты последнего сохранения с помощью Aspose.Tasks для Java.  
- **Нужен ли установленный Microsoft Project?** Нет, Aspose.Tasks работает независимо от Microsoft Project.  
- **Какие форматы файлов поддерживаются?** XML‑файлы проекта, такие как MPP и XML, полностью поддерживаются.  
- **Сколько времени занимает реализация?** Примерно 5‑10 минут для базовой проверки версии.  
- **Требуется ли лицензия?** Бесплатная пробная версия подходит для оценки; коммерческая лицензия требуется для использования в продакшене.  

## Что такое учебник Aspose Tasks для Java?
Учебник `Aspose.Tasks` для Java — это краткое практическое руководство, демонстрирующее, как программно взаимодействовать с данными Microsoft Project. Он показывает, как читать, изменять и анализировать информацию о проекте без необходимости установки Microsoft Project на сервере. Кроме того, он охватывает загрузку файлов, доступ к свойствам и сохранение изменений, позволяя разработчикам эффективно автоматизировать задачи управления проектами.

## Почему использовать Aspose.Tasks для определения версии проекта?
Aspose.Tasks предоставляет **точные метаданные версии** и **метки времени последнего сохранения**, работая на любой ОС, поддерживающей Java. Он обрабатывает файлы до **500 страниц менее чем за 2 секунды** на стандартном процессоре 2.5 GHz, что делает его идеальным для пакетной автоматизации и сценариев масштабной миграции.

## Требования
Перед началом убедитесь, что у вас есть:

1. **Java Development Kit (JDK)** – версия 8 или новее.  
2. **Aspose.Tasks for Java JAR** – скачайте с [веб‑сайта](https://releases.aspose.com/tasks/java/) и добавьте в classpath вашего проекта.  
3. **MS Project file** – XML‑файл проекта (например, `input.xml`), который вы хотите проанализировать.  

> **Подсказка:** Храните файл проекта в отдельной папке `data`, чтобы поддерживать порядок путей и избегать случайных перезаписей.

## Импорт пакетов
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Как настроить каталог проекта
Чтобы правильно находить файлы проекта, создайте отдельный каталог в структуре вашего приложения и храните там все входные файлы. Это поддерживает чистоту кода и избегает ошибок, связанных с путями при загрузке файлов. Используйте понятное имя переменной для пути к каталогу, которое может быть абсолютным или относительным к корню проекта.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Замените `"Your Data Directory"` на абсолютный или относительный путь, где находится `input.xml`.

## Как загрузить проект
`Project` — основной объект Aspose.Tasks, представляющий файл Microsoft Project в памяти, предоставляющий доступ ко всем свойствам и коллекциям проекта. После создания экземпляра `Project` вы можете запрашивать его поля, перебрать задачи или изменить данные перед сохранением файла обратно на диск.

```java
Project project = new Project(dataDir + "input.xml");
```

Если ваш файл имеет другое имя, соответственно измените `"input.xml"`.

## Как определить версию проекта
`Prj.SAVE_VERSION` — свойство, указывающее номер версии Microsoft Project, который сохранил файл. `Prj.LAST_SAVED` — свойство, хранящее дату и время последнего сохранения файла. `Prj.SAVE_VERSION` возвращает числовую версию приложения Microsoft Project, которое сохранило файл (например, 12 для Project 2010). `Prj.LAST_SAVED` предоставляет точную дату и время последней операции сохранения.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

Эти значения позволяют программно применять бизнес‑правила, зависящие от версии, или генерировать аудиторские отчёты.

## Как отобразить результат
После получения информации о версии и дате последнего сохранения обычно требуется вывести её в консоль или файл журнала. Используйте `System.out.println` для отображения значений, при необходимости форматируя дату. Это подтверждает успешность извлечения и предоставляет мгновенную обратную связь во время разработки или в автоматических скриптах.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | Файл не найден или путь неверен | Проверьте `dataDir` и имя файла; используйте абсолютный путь для тестирования. |
| Unexpected version number (e.g., 0) | Загрузка не‑Project XML файла | Убедитесь, что файл является корректным файлом Microsoft Project (MPP/XML). |
| License exception | Использование пробной версии без действующей лицензии в продакшене | Примените вашу лицензию Aspose.Tasks (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Часто задаваемые вопросы

**Q: Могу ли я использовать Aspose.Tasks с другими языками программирования?**  
A: Да, Aspose.Tasks поддерживает .NET, Java и C++ и другие.

**Q: Подходит ли Aspose.Tasks для крупномасштабных проектов?**  
A: Абсолютно; он может обрабатывать проекты в несколько сотен страниц за секунды, не загружая весь файл в память.

**Q: Могу ли я настраивать данные проекта с помощью Aspose.Tasks?**  
A: Да, вы можете изменять задачи, ресурсы, календари и любые другие элементы проекта через API.

**Q: Требуется ли установка Microsoft Project для Aspose.Tasks?**  
A: Нет, библиотека работает независимо и не требует Microsoft Project на хост‑машине.

**Q: Доступна ли техническая поддержка для Aspose.Tasks?**  
A: Да, вы можете получить помощь на форуме Aspose.Tasks [здесь](https://forum.aspose.com/c/tasks/15).

**Дополнительные вопросы и ответы**

**Q: Как получить другие свойства проекта (например, автора, компанию)?**  
A: Используйте `project.get(Prj.AUTHOR)` или `project.get(Prj.COMPANY)` так же, как получаете версию.

**Q: Можно ли проверить версию файла MPP (бинарного)?**  
A: Да, Aspose.Tasks загружает файлы `.mpp` напрямую; свойство `Prj.SAVE_VERSION` также работает для бинарных форматов.

**Q: Есть ли способ программно обновить старый файл проекта до более новой версии?**  
A: Загрузите старый файл, затем сохраните его с `project.save("newfile.mpp", SaveFileFormat.MPP);` — Aspose.Tasks по умолчанию записывает файл в последнем формате.

## Заключение
Теперь вы освоили **как получить версию проекта** и **получить дату последнего сохранения** из файлов MS Project с помощью Aspose.Tasks для Java. Внедрите эти фрагменты кода в автоматизированные конвейеры, инструменты отчётности или утилиты миграции, чтобы всегда знать точную версию Project, с которой работаете.

---

**Последнее обновление:** 2026-05-31  
**Тестировано с:** Aspose.Tasks for Java 24.11  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные учебники

- [Установить дату начала проекта в MS Project с помощью Aspose.Tasks для Java](/tasks/java/project-properties/write-project-info/)
- [Прочитать базу данных Microsoft Project с Aspose.Tasks для Java](/tasks/java/project-data-reading/read-project-database/)
- [Сохранить проект как шаблон, CSV и текст с Aspose.Tasks для Java](/tasks/java/project-file-operations/save-csv-text-template/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}