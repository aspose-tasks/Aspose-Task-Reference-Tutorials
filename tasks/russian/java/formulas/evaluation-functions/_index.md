---
date: 2025-12-09
description: Узнайте, как создать объект проекта Java и поддерживать функции оценки
  в формулах Aspose.Tasks с использованием Java. Откройте, как создать расширенный
  атрибут для задач.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Создание объекта проекта Java – поддержка функций оценки в Aspose.Tasks
url: /ru/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Поддержка функций оценки в формулах Aspose.Tasks

## Введение
Aspose.Tasks for Java позволяет вам **create project object java** создавать экземпляры и выполнять функции Microsoft Project непосредственно в вашем Java‑коде. Встраивая эти формулы, вы можете выполнять сложные расчёты, генерировать пользовательские отчёты и автоматизировать анализ проекта, не покидая среду разработки. Этот учебник проведёт вас через весь процесс — от настройки объекта проекта до добавления расширенного атрибута, который может хранить пользовательские данные.

## Быстрые ответы
- **Что означает “create project object java”?** Он создаёт в памяти экземпляр `Project`, которым вы можете программно управлять.  
- **Какая библиотека требуется?** Aspose.Tasks for Java (скачайте с официального сайта).  
- **Нужна ли лицензия?** Для использования в продакшене требуется временная или полная лицензия; доступна бесплатная пробная версия.  
- **Могу ли я использовать пользовательские поля?** Да — вы можете определять и прикреплять расширенные атрибуты к задачам.  
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

## Шаг 1: Создание объекта проекта Java
Создайте новый объект `Project`. Он будет служить контейнером для всех задач, ресурсов и пользовательских данных, которые вы определите.

```java
Project project = new Project();
```

Строка выше **creates project object java**, который изначально пуст и готов к настройке.

## Шаг 2: Как создать расширенный атрибут
Определите расширенный атрибут, который будет хранить пользовательские числовые данные (например, значение синуса) для каждой задачи.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Здесь мы **create extended attribute** типа `Number` с именем “Sine” и связываем его с задачами.

## Шаг 3: Добавление расширенного атрибута в проект
Зарегистрируйте определение атрибута в проекте, чтобы каждая задача могла ссылаться на него.

```java
project.getExtendedAttributes().add(attr);
```

## Шаг 4: Создание новой задачи
Добавьте простую задачу с именем “Task” под корневой задачей проекта.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Шаг 5: Привязка расширенного атрибута к задаче
Свяжите ранее определённый расширенный атрибут с только что созданной задачей.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Теперь задача содержит пользовательское поле “Sine”, которое вы можете использовать в формулах или вычислениях.

## Зачем использовать функции оценки?
Встраивание функций MS Project в формулы Aspose.Tasks позволяет вам:

- Выполнять мгновенные расчёты (например, `Sin([Start])`) без внешних инструментов.  
- Хранить всю логику проекта в единой, поддерживаемой кодовой базе.  
- Генерировать динамические отчёты, отражающие изменения данных в реальном времени.

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|---------|
| **Formula returns `NaN`** | Убедитесь, что тип пользовательского поля соответствует ожидаемому числовому типу. |
| **Extended attribute not visible** | Убедитесь, что определение атрибута добавлено в проект **before** создания задач. |
| **License exception** | Установите временную или полную лицензию; режим пробной версии может ограничивать некоторые функции. |

## Часто задаваемые вопросы

**Q: Может ли Aspose.Tasks for Java обрабатывать сложные формулы MS Project?**  
A: Да, Aspose.Tasks for Java поддерживает оценку широкого спектра функций MS Project, позволяя выполнять сложные расчёты в Java‑приложениях.

**Q: Совместим ли Aspose.Tasks for Java с разными версиями файлов Microsoft Project?**  
A: Да, Aspose.Tasks for Java поддерживает различные версии файлов Microsoft Project, включая форматы MPP, MPT и XML.

**Q: Могу ли я попробовать Aspose.Tasks for Java перед покупкой?**  
A: Да, вы можете скачать бесплатную пробную версию Aspose.Tasks for Java с сайта [here](https://purchase.aspose.com/buy).

**Q: Как получить поддержку по Aspose.Tasks for Java?**  
A: Вы можете получить поддержку на форуме сообщества Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Q: Доступна ли временная лицензия для Aspose.Tasks for Java?**  
A: Да, вы можете получить временную лицензию для тестирования с сайта Aspose [here](https://purchase.aspose.com/temporary-license/).

---

**Последнее обновление:** 2025-12-09  
**Тестировано с:** Aspose.Tasks for Java 24.10  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}