---
date: 2026-10-31
description: Узнайте, как сохранить проект в PDF и прочитать базу данных Microsoft
  Project с помощью Aspose.Tasks для Java, а также подключиться к Project Server,
  преобразовать проект в HTML и экспортировать проект в XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Чтение данных проекта из базы данных Microsoft Project в Aspose.Tasks
og_description: Сохранить проект в PDF и прочитать базу данных Microsoft Project с
  помощью Aspose.Tasks для Java. Узнайте, как подключиться к Project Server, экспортировать
  в HTML, XML и CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Сохранить проект в PDF и прочитать базу данных Microsoft Project с помощью
  Aspose.Tasks для Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Сохранить проект в PDF и прочитать базу данных Microsoft Project с помощью
  Aspose.Tasks для Java
url: /ru/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сохранить проект в PDF и прочитать базу данных Microsoft Project с помощью Aspose.Tasks для Java

## Введение
В этом руководстве вы узнаете, как **читать базу данных Microsoft Project** напрямую с сервера Microsoft Project Server и затем **сохранить проект в PDF** с помощью Java‑API Aspose.Tasks. Независимо от того, нужно ли вам генерировать печатные отчёты, мигрировать устаревшие данные или встраивать информацию о проекте в пользовательский портал, это руководство проведёт вас через каждый шаг — от настройки соединения JDBC до экспорта проекта в PDF, XML или HTML. По завершении у вас будет готовое к производству решение, работающее на любом Java‑сервере без установки Microsoft Project.

## Быстрые ответы
- **Что делает Aspose.Tasks?** Предоставляет чистый Java‑API для чтения, записи и манипулирования файлами и базами данных Microsoft Project.  
- **Нужен ли установленный Microsoft Project?** Нет, Aspose.Tasks работает независимо от Microsoft Project.  
- **Какие типы баз данных поддерживаются?** Microsoft SQL Server — бекенд Project Server.  
- **Можно ли экспортировать в другие форматы?** Да — PDF, XML, HTML, CSV, PNG, JPEG и др.  
- **Какие основные предварительные требования?** JDK 8 или новее, библиотека Aspose.Tasks для Java, драйвер JDBC для SQL Server и действительные учётные данные Project Server.

## Что означает «чтение базы данных Microsoft Project»?
Чтение базы данных Microsoft Project подразумевает подключение к репозиторию SQL Server сервера Project Server, извлечение хранящихся данных проекта и загрузку их в объект `Project`, которым может управлять Aspose.Tasks. Такой подход идеален для автоматизированной отчётности, миграции данных или пользовательской аналитики.

## Почему использовать Aspose.Tasks для Java?
Aspose.Tasks для Java позволяет работать с данными Microsoft Project без необходимости настольного приложения, предлагая чистое Java‑решение, работающее на любой платформе. Он предоставляет обширную объектную модель для задач, ресурсов, календарей и пользовательских полей и способен эффективно обрабатывать крупные корпоративные проекты, что делает его идеальным для автоматизированных отчётов, миграции и интеграционных сценариев.

- **Отсутствие зависимости от Microsoft Project** — работает на любом сервере или в CI‑среде.  
- **Богатая объектная модель** — программный доступ к задачам, ресурсам, назначениям, календарям и пользовательским полям.  
- **Множественные варианты экспорта** — Aspose.Tasks поддерживает экспорт в **более чем 20 форматов файлов**, включая PDF, XML, HTML, CSV, PNG и JPEG, одним вызовом API.  
- **Высокая производительность** — библиотека может обработать проекты, содержащие **до 10 000 задач**, менее чем за минуту и использует потоковую передачу данных, чтобы избежать загрузки всего файла в память.

## Предварительные требования
Перед началом убедитесь, что у вас есть:

1. Рабочая среда разработки Java (JDK 8 или новее).  
2. Библиотека Aspose.Tasks для Java, добавленная в classpath вашего проекта.  
3. Учётные данные для доступа к базе данных SQL Server Project Server (имя сервера, порт, имя базы, имя пользователя, пароль).  
4. Microsoft JDBC Driver для SQL Server (например, `sqljdbc4.jar`).  

## Импорт пакетов
Сначала импортируйте необходимые классы. Список включает основные классы Aspose.Tasks и стандартные утилиты Java.

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## Как подключиться к Project Server
Надёжное соединение — фундамент для чтения данных проекта. Убедитесь, что экземпляр SQL Server доступен с вашего Java‑хоста и что используемый логин имеет права **SELECT** на схему Project Server. Также проверьте сетевую задержку и при необходимости настройте SSL для обеспечения безопасной передачи данных.

## Шаг 1: настройка соединения с базой данных
Класс `MspDbSettings` инкапсулирует детали JDBC‑соединения, необходимые для доступа к базе данных Microsoft Project Server. Создайте экземпляр `MspDbSettings`, содержащий строку подключения JDBC. Замените значения‑заполнители на реальные параметры вашего сервера.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Храните строку подключения в защищённом конфигурационном файле или переменной окружения, а не в коде.

## Шаг 2: добавить JDBC‑драйвер
Загрузите драйвер Microsoft SQL Server JDBC во время выполнения, чтобы JVM могла взаимодействовать с базой данных.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** Убедитесь, что версия драйвера соответствует версии вашего SQL Server. Несовместимый драйвер может привести к сбоям соединения.

## Шаг 3: чтение данных проекта
Класс `Project` представляет файл Microsoft Project, загруженный в память, и предоставляет доступ к задачам, ресурсам и назначениям. Создайте объект `Project`, передав `MspDbSettings`. Aspose.Tasks автоматически извлечёт данные проекта из базы.

```java
Project project = new Project(settings);
```

На этом этапе вы можете исследовать объект `project` — перечислять задачи, ресурсы или изменять поля по необходимости.

## Шаг 4: сохранить проект в PDF
Перечисление `SaveFileFormat` определяет формат вывода для метода `Project.save`, например PDF, XML или HTML. Экспортируйте загруженный проект в выбранный формат. Пример ниже сохраняет проект как **PDF**, что идеально подходит для печатных отчётов. Вы также можете **экспортировать проект в XML** или **конвертировать проект в HTML**, изменив значение перечисления `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Если нужен XML, замените `SaveFileFormat.Pdf` на `SaveFileFormat.Xml`. Для вывода в HTML используйте `SaveFileFormat.Html`.

## Распространённые проблемы и решения
| Проблема | Типичная причина | Решение |
|----------|------------------|---------|
| **Connection timeout** | Неправильный сервер/порт или блокировка брандмауэром | Проверьте адрес сервера, откройте порт 1433 и протестируйте соединение простой JDBC‑программой. |
| **Authentication error** | Неверное имя пользователя/пароль или SQL Server не настроен для SQL‑аутентификации | Используйте корректный SQL‑логин или включите смешанный режим аутентификации на сервере. |
| **Driver not found** | JDBC‑jar не находится в classpath | Убедитесь, что `addJDBCDriver` указывает на правильный файл `.jar`, и путь использует двойные обратные слеши (`\\`). |
| **Empty project after load** | Недостаточные права для чтения таблиц Project Server | Предоставьте логину права SELECT на схему базы данных Project Server. |

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Tasks для чтения данных проекта из других баз, помимо Microsoft Project?**  
A: Да, Aspose.Tasks поддерживает чтение данных проекта из XML‑файлов, баз Primavera и других стандартных форматов проектов.

**Q: Совместим ли Aspose.Tasks с разными версиями Microsoft Project?**  
A: Да, библиотека работает с Microsoft Project 2007 вплоть до последних выпусков 2024 года, обеспечивая бесшовную интеграцию между версиями.

**Q: Можно ли изменять данные проекта перед сохранением?**  
A: Абсолютно, вы можете добавлять, обновлять или удалять задачи, ресурсы и пользовательские поля с помощью богатого API перед экспортом.

**Q: Поддерживает ли Aspose.Tasks несколько форматов вывода?**  
A: Да, проекты можно сохранять как PDF, XML, HTML, CSV, PNG, JPEG и др. — более 20 форматов в общей сложности.

**Q: Где можно получить дополнительную поддержку или помощь по Aspose.Tasks?**  
A: Для дополнительной помощи посетите **форум Aspose.Tasks** или изучите документацию на сайте [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Заключение
Следуя этому пошаговому руководству, вы теперь знаете, как **читать базу данных Microsoft Project**, **сохранить проект в PDF** и экспортировать его в другие форматы с помощью Aspose.Tasks для Java. Такой подход устраняет зависимость от Microsoft Project, упрощает автоматизированную отчётность и открывает возможности для мощных пользовательских интеграций.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Author:** Aspose

## Связанные руководства

- [Как сохранить проект в PDF с Aspose.Tasks – Руководство по экспорту](/tasks/java/project-file-operations/save-as-pdf/)
- [Сохранить проект в PDF – Отрисовка листа задач с Aspose.Tasks для Java](/tasks/java/task-properties/render-task-sheet/)
- [Экспорт проекта в PDF и уменьшение промежутка между списком задач и нижним колонтитулом в Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}