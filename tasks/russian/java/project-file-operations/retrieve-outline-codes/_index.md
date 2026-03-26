---
date: 2025-12-20
description: Узнайте, как программно получать коды структуры в MS Project с помощью
  Aspose.Tasks для Java. Улучшите свои возможности управления проектами.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Получить коды структуры MS Project в Aspose.Tasks
url: /ru/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Получить коды структуры проекта MS в Aspose.Tasks

## Введение
В этом руководстве вы узнаете **как получить коды структуры проекта MS** с помощью Aspose.Tasks для Java. Коды структуры в MS Project предоставляют мощный способ категоризации задач, ресурсов и назначений, а программный доступ к ним позволяет создавать пользовательские отчёты, автоматизацию или интеграционные решения. Мы пройдём полный пошаговый пример, который вы сможете скопировать в свой проект.

## Быстрые ответы
- **Что делает код?** Он загружает файл проекта и выводит каждое определение кода структуры, его маски и значения.  
- **Какая библиотека требуется?** Aspose.Tasks для Java (любая актуальная версия).  
- **Нужна ли лицензия?** Для разработки подходит пробная версия; для продакшна требуется полная лицензия.  
- **Какая версия Java поддерживается?** Java 8 и выше.  
- **Можно ли изменять коды после их получения?** Да – тот же API позволяет добавлять, редактировать или удалять коды структуры.

## Что такое коды структуры проекта MS?
Коды структуры – это пользовательские поля, позволяющие менеджерам проектов группировать и фильтровать задачи сверх стандартной иерархии. Они могут быть простыми числовыми значениями, строками или даже корпоративными пользовательскими кодами, определёнными на уровне организации. Читая эти коды, вы можете формировать дашборды, экспортировать данные или автоматически применять правила именования.

## Почему получать коды структуры проекта MS с Aspose.Tasks?
- **Автоматизация:** Генерировать отчёты или запускать рабочие процессы без ручного экспорта.  
- **Интеграция:** Синхронизировать коды структуры с ERP, PPM или BI‑инструментами.  
- **Настройка:** Применять бизнес‑правила на основе значений кода (например, распределение затрат).  
- **Кроссплатформенность:** Работает на Windows, Linux и macOS, независимо от пользовательского интерфейса Microsoft Project.

## Предварительные требования
Прежде чем начать, убедитесь, что у вас настроены следующие требования:

### 1. Среда разработки Java
Убедитесь, что на вашей системе установлен Java Development Kit (JDK). Скачать и установить JDK можно с сайта Oracle.

### 2. Библиотека Aspose.Tasks
Скачайте и подключите библиотеку Aspose.Tasks в ваш Java‑проект. Библиотеку можно загрузить со [страницы загрузки Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Импорт пакетов
Сначала импортируйте необходимые пакеты из Aspose.Tasks в ваш Java‑код:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Теперь разберём предоставленный пример кода по шагам:

## Шаг 1: Загрузка проекта
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
На этом шаге мы загружаем файл Microsoft Project в объект `Project`, используя указанное имя файла.

## Шаг 2: Получение кодов структуры
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Мы перебираем каждое определение кода структуры в проекте.

## Шаг 3: Доступ к свойствам кода структуры
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Мы получаем и выводим различные свойства определения кода структуры, такие как Alias, Field ID и Field Name.

## Шаг 4: Проверка корпоративного пользовательского кода
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Мы проверяем, является ли код структуры корпоративным пользовательским кодом, и выводим результат соответственно.

## Шаг 5: Отображение масок кода структуры
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Мы перебираем каждую маску, связанную с кодом структуры, и выводим её уровень и значение маски.

## Шаг 6: Отображение значений кода структуры
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Мы перебираем каждое значение кода структуры и выводим его описание, ID значения, значение и тип.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|----------|----------|
| **Нет вывода** | Неправильный путь к файлу проекта | Убедитесь, что `projectName` указывает на существующий файл `.mpp`. |
| **Null‑значения** | Код структуры не определён в файле | Проверьте, что файл проекта действительно содержит коды структуры (см. в UI MS Project). |
| **LicenseException** | Используется пробная версия без активации | Примените временную или полную лицензию через `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Часто задаваемые вопросы

**В: Можно ли с помощью Aspose.Tasks for Java изменять коды структуры в файле проекта?**  
О: Да, Aspose.Tasks for Java предоставляет API для программного изменения кодов структуры. Вы можете добавлять, редактировать или удалять определения, используя тот же объект `Project`.

**В: Есть ли пробная версия Aspose.Tasks for Java?**  
О: Да, бесплатную пробную версию Aspose.Tasks for Java можно скачать со [сайта Aspose.Tasks](https://releases.aspose.com/).

**В: Как получить техническую поддержку по Aspose.Tasks for Java?**  
О: Техническую поддержку можно получить, посетив [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) и разместив там свой вопрос.

**В: Можно ли приобрести временную лицензию для Aspose.Tasks for Java?**  
О: Да, временную лицензию для Aspose.Tasks for Java можно приобрести на [странице покупки](https://purchase.aspose.com/temporary-license/).

**В: Где найти полную документацию по Aspose.Tasks for Java?**  
О: Полную документацию можно посмотреть в разделе [documentation](https://reference.aspose.com/tasks/java/).

## Заключение
В этом руководстве мы узнали, как получить **коды структуры проекта MS** с помощью Aspose.Tasks для Java. Следуя приведённым шагам, вы сможете эффективно получать доступ к кодам структуры и управлять ими в своих Java‑приложениях, открывая возможности продвинутого управления проектами, такие как пользовательские отчёты, автоматизация и интеграция с другими корпоративными системами.

---

**Последнее обновление:** 2025-12-20  
**Тестировано с:** Aspose.Tasks for Java 24.12 (последняя на момент написания)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}