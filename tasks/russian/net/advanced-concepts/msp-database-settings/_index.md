---
title: Настройки базы данных Microsoft Project в Aspose.Tasks
linktitle: Настройки базы данных Microsoft Project в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как настроить параметры базы данных Microsoft Project с помощью Aspose.Tasks для плавной интеграции с приложениями .NET.
weight: 19
url: /ru/net/advanced-concepts/msp-database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Настройки базы данных Microsoft Project в Aspose.Tasks

## Введение

Если вы работаете с базами данных Microsoft Project в своих приложениях .NET с помощью Aspose.Tasks, вам необходимо настроить необходимые параметры для беспрепятственного импорта данных проекта. Это руководство шаг за шагом проведет вас через этот процесс.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

1.  Aspose.Tasks для .NET: Загрузите и установите библиотеку Aspose.Tasks с сайта[здесь](https://releases.aspose.com/tasks/net/).
2. Доступ к базе данных Microsoft Project. У вас должен быть доступ к базе данных Microsoft Project для импорта данных.

## Импортировать пространства имен

Сначала убедитесь, что вы импортировали необходимые пространства имен в свой проект:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Шаг 1. Создайте строку подключения

Создайте строку подключения к базе данных Microsoft Project. Вот пример:

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

Обязательно замените значения заполнителей фактическими учетными данными базы данных.

## Шаг 2. Настройте параметры MspDbSettings.

 Создайте экземпляр`MspDbSettings` и укажите строку подключения вместе с GUID проекта:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## Шаг 3. Загрузите данные проекта

 Создать экземпляр`Project` объект с использованием настроенных параметров:

```csharp
var project = new Project(settings);
```

## Шаг 4. Сохраните данные проекта

Сохраните загруженные данные проекта в файл:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## Заключение

В этом руководстве вы узнали, как настроить параметры доступа к базам данных Microsoft Project с помощью Aspose.Tasks для .NET. Выполнив эти шаги, вы сможете легко импортировать данные проекта в свои приложения, что облегчит эффективное управление проектами.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.Tasks с разными версиями баз данных Microsoft Project?

О1: Да, Aspose.Tasks поддерживает различные версии баз данных Microsoft Project, что обеспечивает гибкость интеграции.

### Вопрос 2. Как устранить проблемы с подключением к базе данных?

 A2: Убедитесь, что строка подключения правильно настроена с соответствующими учетными данными и сведениями о базе данных. Вы также можете обратиться к документации или обратиться за поддержкой в[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### В3: Доступна ли пробная версия для Aspose.Tasks?

 О3: Да, вы можете получить доступ к бесплатной пробной версии на[здесь](https://releases.aspose.com/).

### Вопрос 4. Могу ли я настроить схему взаимодействия с базой данных?

 A4: Да, вы можете указать схему для`MspDbSettings` объект в соответствии со структурой вашей базы данных.

### Вопрос 5: Где я могу найти более подробную документацию по использованию Aspose.Tasks?

 A5: Вы можете изучить подробную документацию.[здесь](https://reference.aspose.com/tasks/net/) для получения подробной информации о функциях Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
