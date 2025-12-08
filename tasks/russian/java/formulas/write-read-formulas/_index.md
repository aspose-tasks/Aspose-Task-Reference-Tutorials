---
date: 2025-12-07
description: Узнайте, как сохранять файл проекта, писать и читать формулы MS Project,
  а также добавлять формулы пользовательских полей с помощью Aspose.Tasks для Java.
language: ru
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Сохранить файл проекта и записать формулы MS Project с помощью Aspose.Tasks
url: /java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сохранить файл проекта и записать формулы MS Project с Aspose.Tasks

## Введение
В области управления проектами эффективная работа с данными имеет первостепенное значение. Aspose.Tasks for Java — это надёжное решение, которое облегчает манипуляцию и извлечение данных из файлов Microsoft Project. Одна из мощных возможностей, которую оно предоставляет, — запись и чтение формул MS Project. **Вы также узнаете, как *сохранить файл проекта* после применения этих формул**, гарантируя, что ваши изменения будут сохранены для дальнейшего анализа. Этот учебник проведёт вас через процесс использования этой функциональности для улучшения задач управления проектами.

## Быстрые ответы
- **Что делает «save project file»?** Он записывает все изменения в памяти обратно в файл .mpp на диске.  
- **Можно ли добавить формулы пользовательских полей?** Да — вы можете создать пользовательское поле и задать формулу, например «удвоить стоимость задачи».  
- **Нужна ли лицензия для запуска кода?** Бесплатная пробная версия подходит для оценки; коммерческая лицензия требуется для продакшна.  
- **Какая IDE лучше всего подходит?** Любая Java‑IDE (IntelliJ IDEA, Eclipse, VS Code) скомпилирует пример.  
- **Совместим ли API с последней версией MS Project?** Aspose.Tasks поддерживает все современные форматы .mpp.

## Что означает «save project file» в Aspose.Tasks?
Сохранение файла проекта означает фиксирование текущего состояния объекта `Project` — включая задачи, ресурсы и любые пользовательские формулы — в физический файл Microsoft Project (`.mpp`). Эта операция необходима после изменения данных, например после добавления пользовательского поля или изменения стоимости задачи.

## Почему стоит добавить пользовательское поле и создать формулу пользовательского поля?
Добавление пользовательского поля даёт гибкий контейнер для дополнительной информации, которая не покрывается стандартными полями. Привязав формулу — например, **удвоить стоимость задачи** — вы автоматизируете расчёты, уменьшаете количество ручных ошибок и поддерживаете согласованность данных расписания.

## Предварительные требования
Перед тем как приступить к учебнику, убедитесь, что у вас есть следующее:

1. **Java Development Kit (JDK)** — установлен Java 8 или выше.  
2. **Aspose.Tasks for Java** — скачайте и установите с [здесь](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** — выберите предпочитаемую IDE для разработки на Java (IntelliJ IDEA, Eclipse, VS Code и т.д.).  

## Импорт пакетов
Чтобы начать, импортируйте необходимые пакеты в ваш Java‑проект:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Шаг 1: Настройка каталога данных
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Определите папку, где находятся ваши файлы MS Project. Здесь вы будете загружать исходный файл и позже **save project file**.

## Шаг 2: Загрузка файла проекта
```java
Project project = new Project(dataDir + "project.mpp");
```
Загрузите существующий файл Microsoft Project в объект `Project`, чтобы иметь возможность читать или изменять его содержимое.

## Шаг 3: Добавление пользовательского поля и создание формулы пользовательского поля
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
На этом этапе мы **add custom field** «Double Costs» и **create custom field formula**, которая умножает `[Cost]` задачи на 2, фактически **double task cost**. Метод `setFormula` внедряет расчёт непосредственно в файл проекта.

## Шаг 4: Добавление задачи и установка стоимости
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Создайте новую задачу, затем задайте базовую стоимость `100`. При сохранении проекта пользовательское поле автоматически отобразит `200` благодаря ранее определённой формуле.

## Шаг 5: Сохранить файл проекта
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Наконец, **save project file** со всеми изменениями. Метод `save` записывает обновлённый проект, включая новое пользовательское поле и вычисленные значения, в `saved.mpp`.

## Распространённые проблемы и решения
| Issue | Reason | Fix |
|-------|--------|-----|
| **Formula not applied** | Custom field not added to the project’s `ExtendedAttributes` collection. | Ensure `project.getExtendedAttributes().add(attr);` is executed before saving. |
| **File not found** | Incorrect `dataDir` path. | Verify the directory string ends with a path separator (`/` or `\\`). |
| **Cost appears as 0** | Task cost not set before saving. | Call `task.set(Tsk.COST, ...)` before `project.save`. |

## Часто задаваемые вопросы
**Q: Совместим ли Aspose.Tasks со всеми версиями MS Project?**  
A: Да, Aspose.Tasks поддерживает широкий диапазон версий MS Project, от старых форматов .mpp до последних релизов.

**Q: Можно ли интегрировать Aspose.Tasks в существующий Java‑проект?**  
A: Абсолютно. API спроектирован для бесшовной интеграции; достаточно добавить JAR‑файл Aspose.Tasks в classpath проекта.

**Q: Есть ли ограничения на типы формул, которые я могу создавать?**  
A: Библиотека поддерживает большинство нативных синтаксисов формул MS Project, включая арифметику, логические операции и встроенные функции. Сложные пользовательские функции могут потребовать обходных решений.

**Q: Поддерживает ли Aspose.Tasks мультиплатформенную развёртку?**  
A: Да, библиотека работает на любой платформе, поддерживающей Java, включая Windows, Linux и macOS.

**Q: Как получить техническую поддержку по Aspose.Tasks?**  
A: Посетите [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для помощи сообщества или откройте тикет поддержки, если у вас коммерческая лицензия.

## Заключение
В этом учебнике мы рассмотрели, как **save project file**, **add custom field** и **create a custom field formula**, которая **double task cost** с помощью Aspose.Tasks for Java. Следуя этим шагам, вы сможете автоматизировать расчёты, обогатить данные проекта и гарантировать, что все изменения сохраняются для будущих отчётов и анализа.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}