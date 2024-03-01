---
title: Управление MS Project Server с помощью Aspose.Tasks
linktitle: Управление Project Server с помощью Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Разблокируйте эффективное управление MS Project Server с помощью Aspose.Tasks для .NET. Автоматизируйте задачи проекта без особых усилий.
type: docs
weight: 23
url: /ru/net/project-management-integration/project-server-management/
---
## Введение
В этом руководстве мы углубимся в управление MS Project Server с помощью Aspose.Tasks для .NET. Aspose.Tasks — это мощная библиотека, которая позволяет разработчикам программно работать с файлами Microsoft Project, обеспечивая плавную интеграцию и манипулирование данными проекта.
## Предварительные условия
Прежде чем мы углубимся в управление MS Project Server с помощью Aspose.Tasks, убедитесь, что у вас настроены следующие предварительные условия:
1. Microsoft Project Server: вам необходим доступ к экземпляру Microsoft Project Server, где у вас есть административные привилегии или, по крайней мере, разрешения на создание проектов и управление ими.
2.  Библиотека Aspose.Tasks для .NET: убедитесь, что вы загрузили и установили библиотеку Aspose.Tasks для .NET. Вы можете скачать его с сайта[Веб-сайт](https://releases.aspose.com/tasks/net/).
3. Учетные данные: получите необходимые учетные данные для аутентификации на вашем экземпляре MS Project Server. Обычно это включает имя пользователя и пароль.
## Импортировать пространства имен
Прежде чем начать, убедитесь, что вы импортировали необходимые пространства имен в свой код C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## Шаг 1. Настройте учетные данные для аутентификации
Во-первых, вам необходимо настроить учетные данные аутентификации для подключения к вашему экземпляру MS Project Server. Сюда входят адрес домена, имя пользователя и пароль.
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## Шаг 2. Загрузите проект
Затем загрузите файл MS Project, которым вы хотите управлять с помощью Aspose.Tasks.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## Шаг 3. Создайте диспетчер сервера проектов
 Создать экземпляр`ProjectServerManager` объект, используя ранее определенные учетные данные.
```csharp
var manager = new ProjectServerManager(credentials);
```
## Шаг 4: Определите параметры сохранения
Определите любые конкретные параметры сохранения для вашего проекта. Например, вы можете установить таймаут для операции.
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## Шаг 5. Создайте или обновите проект
Наконец, создайте или обновите проект на сервере MS Project Server.
```csharp
manager.CreateNewProject(project, options);
```
Поздравляем! Вы успешно управляли MS Project Server с помощью Aspose.Tasks для .NET.

## Заключение
В этом руководстве мы рассмотрели, как программно управлять MS Project Server с помощью Aspose.Tasks для .NET. С помощью предоставленных шагов вы можете легко интегрировать Aspose.Tasks в свои приложения .NET для автоматизации задач управления проектами на MS Project Server.
## Часто задаваемые вопросы
### Вопрос: Совместим ли Aspose.Tasks со всеми версиями Microsoft Project Server?
О: Aspose.Tasks поддерживает интеграцию с различными версиями Microsoft Project Server, обеспечивая совместимость в различных средах.
### Вопрос: Могу ли я выполнять массовые операции над проектами с помощью Aspose.Tasks?
О: Да, Aspose.Tasks позволяет выполнять массовые операции, такие как создание, обновление и удаление проектов на MS Project Server.
### Вопрос: Предоставляет ли Aspose.Tasks поддержку планирования проектов и управления ресурсами?
О: Конечно, Aspose.Tasks предлагает комплексную поддержку планирования проектов, распределения ресурсов и функций управления задачами.
### Вопрос: Можно ли автоматизировать задачи отчетности с помощью Aspose.Tasks?
О: Да, Aspose.Tasks позволяет автоматизировать создание пользовательских отчетов на основе данных проекта, способствуя эффективному мониторингу и анализу проекта.
### Вопрос: Могу ли я попробовать Aspose.Tasks перед покупкой?
 О: Да, вы можете изучить возможности Aspose.Tasks, воспользовавшись бесплатной пробной версией на сайте[Веб-сайт](https://purchase.aspose.com/temporary-license/).