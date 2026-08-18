---
date: 2026-02-18
description: Узнайте, как сохранить проект в формате PDF и читать базу данных Microsoft
  Project с помощью Aspose.Tasks для Java, а также подключиться к Project Server,
  конвертировать проект в HTML и экспортировать проект в XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Сохранить проект в PDF и прочитать базу данных проекта с помощью Aspose.Tasks
  для Java
url: /ru/java/project-data-reading/read-project-database/
weight: 12
---

 answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сохраните проект в PDF и прочитайте базу данных Microsoft Project с помощью Aspose.Tasks для Java

## Introduction
В этом руководстве вы узнаете, как **читать базу данных Microsoft Project** напрямую с сервера Microsoft Project Server и затем **сохранить проект в PDF** с использованием Aspose.Tasks Java API. Независимо от того, нужно ли вам генерировать отчёты, мигрировать данные или интегрировать информацию о проектах в свои приложения, это руководство проведёт вас через каждый шаг — от настройки соединения с базой данных до экспорта проекта в PDF, XML или HTML. К концу вы получите надёжное, готовое к продакшену решение, которое работает без установки Microsoft Project на хост‑машине.

## Quick Answers
- **Что делает Aspose.Tasks?** Предоставляет чистый Java API для чтения, записи и манипулирования файлами и базами данных Microsoft Project.  
- **Нужен ли установленный Microsoft Project?** Нет, Aspose.Tasks работает независимо от Microsoft Project.  
- **Какой тип базы данных поддерживается?** Microsoft SQL Server (бэкенд Project Server).  
- **Можно ли экспортировать в другие форматы?** Да, помимо PDF можно сохранять в XML, HTML, CSV и другие.  
- **Какие основные предпосылки?** JDK, библиотека Aspose.Tasks для Java, драйвер JDBC для SQL Server и учётные данные для **подключения к Project Server**.

## What is “read Microsoft Project database”?
Чтение базы данных Microsoft Project означает подключение к репозиторию SQL Server сервера Project Server, извлечение сохранённых данных проекта и загрузку их в объект `Project`, которым может управлять Aspose.Tasks. Такой подход идеален для автоматизированной генерации отчётов, миграции данных или пользовательской аналитики.

## Why use Aspose.Tasks for Java?
- **Отсутствие зависимости от Microsoft Project** — работает на любом сервере или в CI‑среде.  
- **Богатая объектная модель** — программный доступ к задачам, ресурсам, назначениям, календарям и пользовательским полям.  
- **Множественные варианты экспорта** — PDF, XML, HTML, PNG и др., одним вызовом API.  
- **Высокая производительность** — оптимизировано для крупных корпоративных проектов.

## Prerequisites
Before you begin, make sure you have:

1. Рабочая среда разработки Java (JDK 8 или новее).  
2. Библиотека Aspose.Tasks для Java, добавленная в classpath проекта.  
3. Учётные данные доступа к базе данных SQL сервера Project Server (имя сервера, порт, имя базы, имя пользователя, пароль) **для подключения к Project Server**.  
4. Microsoft JDBC Driver для SQL Server (например, `sqljdbc4.jar`).  

## Import Packages
First, import the classes you’ll need. The list includes Aspose.Tasks core classes and standard Java utilities.

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

## How to connect to Project Server
Установление надёжного соединения — фундамент для чтения данных проекта. Убедитесь, что экземпляр SQL Server доступен с вашего Java‑хоста и что используемый логин имеет права **SELECT** на схему Project Server.

## Step 1: Set Up Database Connection
Создайте экземпляр `MspDbSettings`, содержащий строку подключения JDBC. Замените значения‑заполнители на реальные детали вашего сервера.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Совет:** Храните строку подключения в защищённом конфигурационном файле или переменной окружения, а не жёстко в коде.

## Step 2: Add JDBC Driver
Загрузите драйвер Microsoft SQL Server JDBC во время выполнения, чтобы JVM могла взаимодействовать с базой данных.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Внимание:** Убедитесь, что версия драйвера соответствует версии вашего SQL Server. Несовместимый драйвер может привести к ошибкам подключения.

## Step 3: Read Project Data
Создайте объект `Project`, передав ему `MspDbSettings`. Aspose.Tasks автоматически получит данные проекта из базы данных.

```java
Project project = new Project(settings);
```

На этом этапе вы можете исследовать объект `project` — перечислять задачи, ресурсы или изменять поля по необходимости.

## Step 4: Save project as PDF
Экспортируйте загруженный проект в выбранный формат файла. Пример ниже сохраняет проект как **PDF**, что идеально подходит для печатных отчётов. Вы также можете **экспортировать проект в XML** или **конвертировать проект в HTML**, изменив значение перечисления `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Если предпочтителен XML, замените `SaveFileFormat.Pdf` на `SaveFileFormat.Xml`. Для вывода в HTML используйте `SaveFileFormat.Html`.

## Common Issues & Solutions
| **Тайм‑аут соединения** | **Неправильный сервер/порт или блокировка брандмауэром** | **Проверьте адрес сервера, откройте порт 1433 и протестируйте соединение простым JDBC‑тестом.** |
| **Ошибка аутентификации** | **Неверное имя пользователя/пароль или SQL Server не настроен для SQL‑аутентификации** | **Используйте корректный SQL‑логин или включите смешанный режим аутентификации на сервере.** |
| **Драйвер не найден** | **JDBC‑jar не находится в classpath** | **Убедитесь, что `addJDBCDriver` указывает на правильный файл `.jar` и путь использует двойные обратные слеши (`\\`).** |
| **Пустой проект после загрузки** | **Недостаточные права для чтения таблиц Project Server** | **Предоставьте логину права SELECT на схему базы данных Project Server.** |

## Frequently Asked Questions

**В: Можно ли использовать Aspose.Tasks для чтения данных проекта из других баз данных, помимо Microsoft Project?**  
**О:** Да, Aspose.Tasks поддерживает чтение данных проекта из различных источников, включая XML‑файлы, Primavera и базы данных Microsoft Project.

**В: Совместим ли Aspose.Tasks с разными версиями Microsoft Project?**  
**О:** Да, Aspose.Tasks разработан для работы с множеством версий Microsoft Project, обеспечивая бесшовную интеграцию.

**В: Можно ли изменить данные проекта перед сохранением?**  
**О:** Абсолютно, Aspose.Tasks предоставляет богатый API для добавления задач, обновления ресурсов и установки свойств проекта перед экспортом.

**В: Поддерживает ли Aspose.Tasks несколько форматов вывода?**  
**О:** Да, вы можете сохранять проекты как PDF, XML, HTML, CSV, PNG, JPEG и другие.

**В: Где можно получить дополнительную поддержку или помощь по Aspose.Tasks?**  
**О:** Для дополнительной помощи посетите форум Aspose.Tasks или изучите документацию, доступную на сайте [here](https://forum.aspose.com/c/tasks/15).

## Conclusion
Следуя этому пошаговому руководству, вы теперь знаете, как **читать базу данных Microsoft Project**, **сохранять проект в PDF** и экспортировать в другие форматы с помощью Aspose.Tasks для Java. Этот подход устраняет зависимость от Microsoft Project, упрощает автоматизированную генерацию отчётов и открывает возможности для мощных пользовательских интеграций.

---

**Последнее обновление:** 2026-02-18  
**Тестировано с:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}