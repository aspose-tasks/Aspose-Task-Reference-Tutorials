---
date: 2026-03-14
description: Узнайте, как задавать схему базы данных для Microsoft Project с помощью
  Aspose.Tasks и как импортировать данные проекта в приложения .NET.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Укажите схему базы данных для Project DB с Aspose.Tasks
url: /ru/net/advanced-concepts/msp-database-settings/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Настройки базы данных Microsoft Project в Aspose.Tasks

## Введение

Если вы работаете с базами данных Microsoft Project в ваших .NET‑приложениях с использованием Aspose.Tasks, вам потребуется **указать схему базы данных** и настроить необходимые параметры для **импорта проекта** без проблем. Этот учебник проведёт вас через процесс шаг за шагом, показывая, как **настроить параметры подключения**, **создать .NET‑строку подключения**, и в конце **сохранить проект как MPP**.

## Быстрые ответы
- **Какова основная цель?** Указать схему базы данных и импортировать базу данных Project в .NET‑приложение.  
- **Какая библиотека требуется?** Aspose.Tasks for .NET.  
- **Как подключиться к Project Server?** Сформировав корректную строку подключения SQL и используя `MspDbSettings`.  
- **Какой формат файла создаётся?** Файл MPP, сохраняемый с помощью `SaveFileFormat.Mpp`.  
- **Можно ли изменить имя схемы?** Да, задайте свойство `Schema` в `MspDbSettings`.

## Как указать схему базы данных для Project DB

Понимание того, почему может потребоваться **указать схему базы данных**, является важным. Во многих корпоративных средах база данных Project Server находится в пользовательской схеме (например, `dbo`, `psdata`). Явно задав схему, вы гарантируете, что Aspose.Tasks будет обращаться к правильным таблицам, предотвращая ошибки выполнения и обеспечивая точный импорт данных.

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Aspose.Tasks for .NET: Скачайте и установите библиотеку Aspose.Tasks с [здесь](https://releases.aspose.com/tasks/net/).  
2. Доступ к базе данных Microsoft Project: У вас должен быть доступ к базе данных Microsoft Project для импорта данных.

## Импорт пространств имён

Сначала убедитесь, что импортировали необходимые пространства имён в ваш проект:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Шаг 1: Создание строки подключения

Сформируйте строку подключения к вашей базе данных Microsoft Project. Здесь вы **создаёте .NET‑строку подключения** и также определяете, как **подключиться к Project Server**.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **Совет:** Тщательно проверьте значения `DataSource` и `InitialCatalog`; они должны соответствовать адресу вашего сервера и имени опубликованной базы данных.

## Шаг 2: Настройка MspDbSettings

Создайте экземпляр `MspDbSettings`, передайте строку подключения и **укажите схему базы данных**, задав свойство `Schema`. Это сообщает Aspose.Tasks, какую схему использовать при запросах.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Здесь также указывается GUID проекта, который идентифицирует конкретный проект, который вы хотите загрузить.

## Шаг 3: Загрузка данных проекта

Создайте объект `Project`, используя настроенные параметры. Этот шаг фактически **импортирует данные проекта** из базы данных в объект .NET.

```csharp
var project = new Project(settings);
```

## Шаг 4: Сохранение данных проекта

Наконец, сохраните загруженный проект в файл MPP на диске. Это демонстрирует, как **сохранить проект как MPP** с помощью API Aspose.Tasks.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

После выполнения кода вы найдёте файл `ImportProjectDataFromDatabase_out.mpp` в выходном каталоге, готовый к открытию в Microsoft Project.

## Заключение

В этом учебнике вы узнали, как **указать схему базы данных** для Microsoft Project, **настроить подключение**, **импортировать данные проекта** и **сохранить проект как MPP** с помощью Aspose.Tasks for .NET. Эти шаги позволяют без проблем интегрировать данные Project Server в ваши пользовательские приложения, помогая создавать надёжные решения для управления проектами.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.Tasks с разными версиями баз данных Microsoft Project?
**Ответ:** Да, Aspose.Tasks поддерживает различные версии баз данных Microsoft Project, обеспечивая гибкость интеграции.

### Вопрос 2: Как решить проблемы с подключением к базе данных?
**Ответ:** Убедитесь, что строка подключения правильно настроена с соответствующими учётными данными и деталями базы данных. Вы также можете обратиться к документации или получить поддержку на форуме [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Вопрос 3: Доступна ли пробная версия Aspose.Tasks?
**Ответ:** Да, бесплатную пробную версию можно получить [здесь](https://releases.aspose.com/).

### Вопрос 4: Можно ли настроить схему для взаимодействия с базой данных?
**Ответ:** Да, вы можете указать схему для объекта `MspDbSettings` в соответствии со структурой вашей базы данных.

### Вопрос 5: Где найти более подробную документацию по использованию Aspose.Tasks?
**Ответ:** Подробную документацию можно изучить [здесь](https://reference.aspose.com/tasks/net/), где представлены детальные сведения о функциях Aspose.Tasks.

**Вопрос:** Работает ли этот подход с базами данных Azure SQL?  
**Ответ:** Абсолютно. Просто измените `DataSource` на имя вашего сервера Azure и убедитесь, что включены настройки TLS/SSL.

**Вопрос:** Как обрабатывать большие базы данных Project без тайм‑аутов?  
**Ответ:** Увеличьте значение `ConnectTimeout` в строке подключения и при необходимости загружайте проекты пакетами.

---

**Last Updated:** 2026-03-14  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}