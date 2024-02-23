---
title: Извлеките информацию о проекте MS в Aspose.Tasks
linktitle: Извлечение информации о проекте в Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Узнайте, как легко извлекать информацию MS Project с помощью Aspose.Tasks для .NET. Погрузитесь в наше подробное руководство.
type: docs
weight: 20
url: /ru/net/project-management-integration/project-information/
---
## Введение
Вы хотите эффективно извлекать информацию из файлов Microsoft Project с помощью Aspose.Tasks для .NET? В этом уроке мы шаг за шагом проведем вас через этот процесс. Но прежде чем мы углубимся в детали реализации, давайте сначала убедимся, что у вас есть все необходимое.
## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующее:
### 1. Aspose.Tasks для .NET
 Убедитесь, что вы установили библиотеку Aspose.Tasks для .NET. Если вы еще этого не сделали, вы можете скачать его с сайта[Веб-сайт Aspose.Tasks для .NET](https://releases.aspose.com/tasks/net/).
### 2. Учетные данные для SharePoint
Вам потребуются учетные данные для доступа к SharePoint, где хранятся файлы MS Project. Убедитесь, что у вас есть следующая информация:
- Адрес домена SharePoint
- Имя пользователя
- Пароль
## Импорт пространств имен
После того, как вы разобрались с предварительными условиями, пришло время импортировать необходимые пространства имен в ваш проект.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Теперь давайте разобьем процесс извлечения информации MS Project на несколько этапов.
## Шаг 1. Предоставьте учетные данные
Во-первых, вам необходимо предоставить свои учетные данные SharePoint для доступа к Project Server.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Шаг 2. Инициализация диспетчера сервера проектов
 Далее инициализируйте`ProjectServerManager` экземпляр с предоставленными учетными данными.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Шаг 3: Получить список проектов
Теперь вы можете получить список проектов с Project Server.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Шаг 4. Распечатайте информацию о проекте
Наконец, просмотрите список проектов и распечатайте их информацию.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Заключение
Поздравляем! Вы успешно научились извлекать информацию MS Project с помощью Aspose.Tasks для .NET. Обладая этими знаниями, вы теперь можете легко интегрировать эту функциональность в свои приложения .NET.
## Часто задаваемые вопросы
### Вопрос 1. Могу ли я использовать Aspose.Tasks для .NET с любой версией Microsoft Project?
О: Да, Aspose.Tasks для .NET поддерживает различные версии Microsoft Project, включая 2003, 2007, 2010, 2013, 2016 и 2019.
### Вопрос 2. Совместим ли Aspose.Tasks для .NET с платформами Windows и Linux?
О: Да, Aspose.Tasks for .NET совместим с платформами Windows и Linux, что делает его универсальным для различных сред разработки.
### Вопрос 3. Могу ли я извлечь зависимости задач с помощью Aspose.Tasks для .NET?
А: Абсолютно! Aspose.Tasks для .NET обеспечивает надежную функциональность для извлечения не только базовой информации о проекте, но также зависимостей задач и других сложных деталей.
### Вопрос 4: Предлагает ли Aspose.Tasks для .NET техническую поддержку?
 О: Да, вы можете получить техническую поддержку для Aspose.Tasks для .NET через[Форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15), где можно задать вопросы и обратиться за помощью к специалистам.
### Вопрос 5: Могу ли я попробовать Aspose.Tasks для .NET перед его покупкой?
 А: Конечно! Вы можете воспользоваться бесплатной пробной версией Aspose.Tasks для .NET на сайте[страница релизов](https://releases.aspose.com/), что позволит вам изучить его возможности перед принятием решения о покупке.