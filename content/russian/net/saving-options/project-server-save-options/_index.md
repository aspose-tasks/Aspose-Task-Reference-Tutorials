---
title: Параметры сохранения проекта MS на сервере для Aspose.Tasks
linktitle: Параметры сохранения Project Server для Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как сохранить параметры Microsoft Project для Aspose.Tasks с помощью интеграции Project Server. Улучшите рабочие процессы управления проектами.
type: docs
weight: 16
url: /ru/net/saving-options/project-server-save-options/
---
## Введение
В этом руководстве мы углубимся в сохранение параметров Microsoft Project для Aspose.Tasks с помощью Project Server. Aspose.Tasks — это мощный .NET API, который позволяет разработчикам программно работать с файлами Microsoft Project. Используя возможности Project Server, мы можем легко интегрировать Aspose.Tasks в наши рабочие процессы управления проектами. Это руководство шаг за шагом проведет вас через этот процесс.
## Предварительные условия
Прежде чем приступить к работе, убедитесь, что у вас есть следующие предварительные условия:
1.  Aspose.Tasks для .NET: Установите Aspose.Tasks для .NET из[ссылка для скачивания](https://releases.aspose.com/tasks/net/).
   
2. Доступ к Project Server: вам потребуются учетные данные для доступа и URL-адрес вашего экземпляра Project Server. Если у вас его нет, вы можете получить бесплатную пробную версию на сайте[здесь](https://releases.aspose.com/).
3. Файл Microsoft Project: подготовьте файл Microsoft Project (.mpp), который вы хотите сохранить с помощью Aspose.Tasks.

## Импортировать пространства имен
Во-первых, вам необходимо импортировать необходимые пространства имен в ваш проект:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Шаг 1. Инициализация проекта и учетных данных
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Обязательно замените`"Your Document Directory"`, `URL`, `Domain`, `UserName` , и`Password` с вашими реальными ценностями.
## Шаг 2. Создайте диспетчер сервера проектов
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Шаг 3: Определите параметры сохранения
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Настроить`ProjectGuid`, `ProjectName`, `Timeout` , и`PollingInterval` согласно вашим требованиям.
## Шаг 4. Сохраните проект на сервере
```csharp
manager.CreateNewProject(project, options);
```
Это позволит сохранить проект на Project Server с указанными параметрами.

## Заключение
В этом руководстве мы узнали, как сохранить параметры Microsoft Project для Aspose.Tasks с помощью интеграции Project Server. Следуя этим шагам, вы сможете легко включить Aspose.Tasks в рабочие процессы управления проектами, повысив эффективность и производительность.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.Tasks с разными версиями Microsoft Project?
О: Да, Aspose.Tasks поддерживает различные версии Microsoft Project, обеспечивая совместимость в различных средах.
### Вопрос: Доступна ли пробная версия для Aspose.Tasks?
 О: Да, вы можете получить бесплатную пробную версию Aspose.Tasks на сайте[здесь](https://releases.aspose.com/).
### Вопрос: Поддерживает ли Aspose.Tasks многопоточность?
О: Да, Aspose.Tasks спроектирован как поточно-ориентированный, что позволяет осуществлять одновременный доступ к данным проекта.
### Вопрос: Могу ли я настроить параметры сохранения при использовании интеграции с Project Server?
О: Да, вы можете настроить параметры сохранения, такие как имя проекта, время ожидания и интервал опроса, в соответствии с вашими требованиями.
### Вопрос: Где я могу найти поддержку Aspose.Tasks?
 О: Вы можете найти поддержку и помощь на[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).