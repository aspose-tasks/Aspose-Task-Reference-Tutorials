---
date: 2025-12-15
description: Изучите, как считывать данные MS Project Online с помощью Aspose.Tasks
  для Java. В этом руководстве показано, как получить список проектов, список проектов
  SharePoint и количество ресурсов.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'aspose tasks java: Легкое чтение данных MS Project Online'
url: /ru/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: Легкое чтение данных MS Project Online

## Введение
В сфере управления проектами эффективная работа с данными Microsoft Project Online имеет решающее значение для упрощения процессов. **aspose tasks java** предоставляет мощный, простой в использовании API, позволяющий читать данные Project Online без необходимости заниматься низкоуровневыми HTTP‑вызовами. В этом руководстве мы пройдемся по тому, как получить список проектов, перечислить проекты SharePoint и получить количество ресурсов в каждом проекте — всё это с помощью нескольких строк кода на Java.

## Быстрые ответы
- **Что делает aspose tasks java?** Читает и манипулирует файлами Microsoft Project и данными Project Online программно.  
- **Нужна ли лицензия для пробного использования?** Доступна бесплатная пробная версия; для использования в продакшн‑среде требуется лицензия.  
- **Какие учетные данные требуются?** Домен SharePoint, имя пользователя и пароль (или токен Azure AD).  
- **Можно ли вывести список проектов SharePoint?** Да — используйте `ProjectServerManager.getProjectList()` для их получения.  
- **Как получить количество ресурсов?** Загрузите каждый объект `Project` и вызовите `project.getResources().size()`.

## Что такое aspose tasks java?
**aspose tasks java** — это библиотека, ориентированная на разработчиков, которая абстрагирует сложности форматов файлов Microsoft Project и REST‑API Project Server. Она позволяет читать, создавать и изменять данные проектов напрямую из Java‑приложений, упрощая интеграцию с существующими корпоративными системами.

## Почему стоит использовать aspose tasks java для чтения MS Project Online?
- **Без ручной работы с HTTP** — библиотека берёт на себя аутентификацию и REST‑вызовы.  
- **Строгая типобезопасность** — работайте с `Project`, `ProjectInfo` и другими POJO вместо сырого JSON.  
- **Кроссплатформенность** — работает в любой среде, совместимой с JVM.  
- **Богатый набор функций** — помимо чтения, вы также можете обновлять задачи, ресурсы и временные линии.

## Предварительные требования
Перед тем как приступить, убедитесь, что у вас есть:

1. **Java Development Kit (JDK)** — установлен JDK 8 или новее.  
2. **Aspose.Tasks for Java** — скачайте библиотеку [здесь](https://releases.aspose.com/tasks/java/).  
3. **Учётная запись Microsoft Project Online** — с правами чтения проектов.  
4. **Адрес домена SharePoint** — где размещён ваш экземпляр Project Online.  
5. **Имя пользователя и пароль** — либо соответствующие учётные данные Azure AD для аутентификации.

## Импорт пакетов
Сначала импортируем основные классы Aspose.Tasks, которые будем использовать в ходе руководства:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Шаг 1: Установка домена SharePoint, имени пользователя и пароля
Определите параметры подключения к вашему окружению Project Online. Замените значения‑заполнители на свои собственные учётные данные.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## Шаг 2: Аутентификация с помощью учётных данных Project Server
Создайте объект `ProjectServerCredentials` и инициализируйте `ProjectServerManager`. Этот менеджер будет обрабатывать все последующие вызовы к Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Шаг 3: Получение списка проектов и вывод информации
Используйте менеджер для **получения списка проектов** (перечисления проектов SharePoint) и выведите базовые детали, такие как имя, дата создания и дата последнего сохранения.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Шаг 4: Загрузка отдельных проектов и вывод количества ресурсов
Для каждого проекта, полученного на предыдущем шаге, загрузите полный объект `Project` и отобразите **количество ресурсов**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Распространённые проблемы и их решения
| Проблема | Причина | Решение |
|----------|----------|----------|
| **Ошибка аутентификации** | Неправильный домен, имя пользователя или пароль. | Проверьте учётные данные и убедитесь, что у аккаунта есть права чтения в Project Online. |
| **SSLHandshakeException** | В среде Java отсутствует требуемая версия TLS. | Обновите JDK до последней версии или включите поддержку TLS 1.2+. |
| **`reader.getProjectList()` возвращает пустой список** | У аккаунта нет доступа к проектам. | Проверьте права доступа в Project Online или используйте учётную запись администратора. |
| **Большие проекты вызывают OutOfMemoryError** | Одновременная загрузка множества проектов потребляет слишком много памяти. | Загружайте проекты по одному и освобождайте ссылки после использования. |

## Часто задаваемые вопросы
### В: Можно ли использовать aspose tasks java для изменения данных MS Project Online?
О: Да, Aspose.Tasks предоставляет обширные возможности как для чтения, **так и** для изменения данных Project Online программно.

### В: Поддерживает ли Aspose.Tasks другие форматы файлов управления проектами?
О: Абсолютно. Библиотека работает с MPP, XML, Primavera и многими другими форматами, обеспечивая совместимость в разных проектных экосистемах.

### В: Есть ли бесплатная пробная версия Aspose.Tasks for Java?
О: Да, вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/) для изучения функций и возможностей Aspose.Tasks.

### В: Где найти полную документацию по Aspose.Tasks for Java?
О: Подробную документацию можно посмотреть [здесь](https://reference.aspose.com/tasks/java/) для получения всесторонних рекомендаций по использованию Aspose.Tasks в ваших Java‑проектах.

### В: Какие варианты поддержки доступны для Aspose.Tasks for Java?
О: При возникновении вопросов или проблем вы можете обратиться за помощью на форум сообщества Aspose.Tasks [здесь](https://forum.aspose.com/c/tasks/15).

---

**Последнее обновление:** 2025-12-15  
**Тестировано с:** Aspose.Tasks for Java 24.11 (на момент написания)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}