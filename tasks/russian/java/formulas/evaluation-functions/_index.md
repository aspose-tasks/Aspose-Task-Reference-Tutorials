---
date: 2026-02-13
description: Узнайте, как генерировать отчёт проекта, создавая объект проекта в Java,
  добавляя расширенные атрибуты и используя функции оценки с Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Создать отчёт проекта – создать объект проекта Java
url: /ru/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Поддержка функций оценки в формулах Aspose.Tasks

## Введение
Aspose.Tasks for Java позволяет вам **создавать отчёт проекта** путем создания **объекта проекта** в Java и оценки функций Microsoft Project непосредственно в вашем коде. Встраивая эти формулы, вы можете выполнять сложные расчёты, создавать пользовательские отчёты и автоматизировать анализ проекта, не покидая свою среду разработки. В этом руководстве мы пройдём процесс создания объекта проекта, добавления расширенного атрибута и использования функций оценки для **добавления данных пользовательского поля задачи**.

## Быстрые ответы
- **Что означает «create project object java»?** Он создаёт в памяти экземпляр `Project`, которым вы можете программно управлять.  
- **Какая библиотека требуется?** Aspose.Tasks for Java (скачайте с официального сайта).  
- **Нужна ли лицензия?** Для использования в продакшене требуется временная или полная лицензия Aspose.Tasks; доступна бесплатная пробная версия.  
- **Можно ли использовать пользовательские поля?** Да — вы можете **add extended attribute** к задачам и использовать их как пользовательские поля.  
- **Совместимо ли это со всеми форматами файлов Project?** Aspose.Tasks поддерживает форматы MPP, MPT и XML.

## Требования
Прежде чем начать, убедитесь, что у вас есть:

1. **Среда разработки Java** — JDK 8+ и IDE, например IntelliJ IDEA или Eclipse.  
2. **Библиотека Aspose.Tasks for Java** — скачайте и подключите библиотеку со страницы [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).

## Импорт пакетов
Добавьте пространство имён Aspose.Tasks в ваш Java‑класс, чтобы работать с проектами, задачами и расширенными атрибутами:

```java
import com.aspose.tasks.*;
```

## Создание отчёта проекта — Создание объекта проекта Java
Создайте новый объект `Project`. Он будет служить контейнером для всех задач, ресурсов и пользовательских данных, которые вы определите.

```java
Project project = new Project();
```

Строка выше **creates project object java** создаёт объект проекта Java, который изначально пуст и готов к настройке.

## Как добавить расширенный атрибут
Определите расширенный атрибут, который будет хранить пользовательские числовые данные (например, значение синуса) для каждой задачи.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Здесь мы **add extended attribute** типа `Number` с именем «Sine» и связываем его с задачами.

## Добавление расширенного атрибута в проект
Зарегистрируйте определение атрибута в проекте, чтобы каждая задача могла его использовать.

```java
project.getExtendedAttributes().add(attr);
```

## Создание новой задачи
Добавьте простую задачу с именем «Task» под корневой задачей проекта.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Связывание расширенного атрибута с задачей
Свяжите ранее определённый расширенный атрибут с только что созданной задачей.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Теперь задача содержит пользовательское поле «Sine», которое вы можете использовать в формулах или вычислениях. Это также способ **add custom field task** данных программно.

## Зачем использовать функции оценки?
Встраивание функций MS Project в формулы Aspose.Tasks позволяет вам:

- Выполнять расчёты «на лету» (например, `Sin([Start])`) без внешних инструментов.  
- Хранить всю логику проекта в единой, поддерживаемой кодовой базе.  
- Создавать динамические отчёты, отражающие изменения данных в реальном времени, помогая вам **generate project report** автоматически.

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|---------|
| **Formula returns `NaN`** | Убедитесь, что тип пользовательского поля соответствует ожидаемому числовому типу. |
| **Extended attribute not visible** | Убедитесь, что определение атрибута добавлено в проект **before** создания задач. |
| **License exception** | Установите временную или полную **Aspose.Tasks license**; режим пробной версии может ограничивать некоторые функции. |
| **Missing temporary license** | Получите **temporary Aspose license** с сайта Aspose. |

## Часто задаваемые вопросы

**Q: Может ли Aspose.Tasks for Java обрабатывать сложные формулы MS Project?**  
A: Да, Aspose.Tasks for Java поддерживает оценку широкого спектра функций MS Project, позволяя выполнять сложные расчёты в Java‑приложениях.

**Q: Совместим ли Aspose.Tasks for Java с разными версиями файлов Microsoft Project?**  
A: Да, Aspose.Tasks for Java поддерживает различные версии файлов Microsoft Project, включая форматы MPP, MPT и XML.

**Q: Можно ли попробовать Aspose.Tasks for Java перед покупкой?**  
A: Да, вы можете скачать бесплатную пробную версию Aspose.Tasks for Java с сайта [here](https://purchase.aspose.com/buy).

**Q: Как получить поддержку по Aspose.Tasks for Java?**  
A: Вы можете получить поддержку на форуме сообщества Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Q: Доступна ли временная лицензия для Aspose.Tasks for Java?**  
A: Да, вы можете получить временную лицензию для тестирования с сайта Aspose [here](https://purchase.aspose.com/temporary-license/).

## Заключение
Следуя этим шагам, вы узнали, как **create project object**, **add extended attribute**, и использовать функции оценки для автоматического **generate project report**. Теперь вы можете расширить эту основу, создавая более продвинутую аналитику проектов, пользовательские панели мониторинга или инструменты автоматического планирования — всё это работает на базе Aspose.Tasks for Java.

---

**Последнее обновление:** 2026-02-13  
**Тестировано с:** Aspose.Tasks for Java 24.10  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}