---
title: Управление учетными данными MS Project Server в Aspose.Tasks
linktitle: Управление учетными данными Project Server в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как легко управлять учетными данными MS Project Server с помощью Aspose.Tasks для .NET. Повышайте эффективность управления проектами.
weight: 22
url: /ru/net/project-management-integration/project-server-credentials/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Управление учетными данными MS Project Server в Aspose.Tasks

## Введение
В сфере управления проектами эффективная координация и бесперебойная коммуникация имеют решающее значение для успешного выполнения проекта. Aspose.Tasks для .NET предоставляет комплексное решение для управления учетными данными Microsoft Project Server, позволяющее пользователям безопасно получать доступ к данным проекта и манипулировать ими. В этом руководстве рассматривается процесс управления учетными данными MS Project Server с помощью Aspose.Tasks для .NET, помогая пользователям пройти каждый шаг для обеспечения бесперебойной работы.
## Предварительные условия
Прежде чем приступить к управлению учетными данными MS Project Server с помощью Aspose.Tasks для .NET, убедитесь, что выполнены следующие предварительные условия:
### 1. Установка Aspose.Tasks для .NET
 Для начала скачайте и установите Aspose.Tasks для .NET из прилагаемого[ссылка для скачивания](https://releases.aspose.com/tasks/net/). Следуйте инструкциям по установке, чтобы легко интегрировать библиотеку в вашу среду .NET.
### 2. Доступ к учетным данным
Соберите необходимые учетные данные, необходимые для доступа к MS Project Server. Сюда входят адрес домена SharePoint, имя пользователя и пароль, связанные с Project Server.

## Импортировать пространства имен
В свой проект .NET импортируйте необходимые пространства имен, чтобы эффективно использовать функциональные возможности, предоставляемые Aspose.Tasks для .NET.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## Шаг 1. Определите путь к каталогу документов
```csharp
String DataDir = "Your Document Directory";
```
## Шаг 2. Установите адрес домена SharePoint, имя пользователя и пароль
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## Шаг 3. Создайте учетные данные Project Server
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Шаг 4. Загрузите файл проекта
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Шаг 5. Инициализация диспетчера сервера проектов
```csharp
var manager = new ProjectServerManager(credentials);
```
## Шаг 6: Создайте новый проект
```csharp
manager.CreateNewProject(newProject);
```
## Шаг 7: Получите список проектов
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Шаг 8. Перебор списка проектов
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Заключение
Эффективное управление учетными данными MS Project Server имеет первостепенное значение для оптимизации управления проектами. Aspose.Tasks для .NET упрощает этот процесс, предоставляя надежный набор функций. Следуя пошаговому руководству, изложенному в этом руководстве, пользователи могут легко интегрировать Aspose.Tasks для .NET в свои проекты, обеспечивая безопасный доступ и манипулирование данными проекта.
## Часто задаваемые вопросы
### Вопрос: Совместим ли Aspose.Tasks для .NET со всеми версиями Microsoft Project Server?
О: Aspose.Tasks for .NET разработан с учетом совместимости с различными версиями Microsoft Project Server, обеспечивая универсальность и гибкость для пользователей.
### Вопрос: Могу ли я интегрировать Aspose.Tasks для .NET в свой существующий проект .NET?
О: Да, Aspose.Tasks для .NET можно легко интегрировать в существующие проекты .NET, обеспечивая эффективные возможности управления проектами.
### Вопрос: Предоставляет ли Aspose.Tasks для .NET поддержку доступа к ресурсам проекта?
О: Конечно, Aspose.Tasks для .NET предлагает комплексную поддержку доступа к ресурсам проекта и управления ими, повышая эффективность управления проектами.
### Вопрос: Существуют ли какие-либо варианты лицензирования для Aspose.Tasks для .NET?
О: Да, Aspose.Tasks для .NET предлагает гибкие варианты лицензирования, включая временные лицензии для пробных целей и полные лицензии для коммерческого использования.
### Вопрос: Где я могу получить помощь или поддержку по Aspose.Tasks для .NET?
 О: По любым вопросам или помощи относительно Aspose.Tasks для .NET вы можете посетить форум поддержки по адресу:[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Полный исходный код
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
