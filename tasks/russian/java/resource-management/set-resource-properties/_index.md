---
date: 2026-01-18
description: Узнайте, как установить стандартную ставку и другие свойства ресурсов
  в MS Project с помощью Aspose.Tasks для Java, включая добавление ресурса в MS Project
  и эффективное управление ресурсами.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как установить стандартную ставку для ресурсов в Aspose.Tasks
url: /ru/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Установить стандартную ставку для ресурсов в Aspose.Tasks

## Введение
Если вы разрабатываете Java‑приложения, которым необходимо работать с файлами Microsoft Project, **установка стандартной ставки** для ресурса — одна из самых распространённых задач. В этом руководстве вы узнаете, как **установить стандартную ставку** и другие свойства ресурса с помощью Aspose.Tasks for Java. К концу руководства вы сможете создать объект проекта, добавить ресурс в файл MS Project и уверенно управлять ресурсами MS Project.

## Быстрые ответы
- **Какой основной класс используется для работы с файлом проекта?** `Project`
- **Какой метод добавляет новый ресурс?** `project.getResources().add()`
- **Как установить стандартную ставку?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Нужна ли лицензия для продакшна?** Да, требуется действующая лицензия Aspose.Tasks.
- **Какая версия Java поддерживается?** Java 8+ (рекомендуется последняя версия JDK).

## Что такое «установка стандартной ставки»?
Операция *установки стандартной ставки* назначает ресурсу стоимость по умолчанию за час. Руководители проектов используют это значение для расчёта затрат на труд, формирования отчётов о стоимости и прогнозирования бюджета.

## Почему устанавливать ставки с помощью Aspose.Tasks?
- **Не требуется установка Microsoft Project** – работа с файлами напрямую из Java.
- **Полная точность** – все поля ресурса, включая сверхурочные и ставки стоимости, сохраняются.
- **Кроссплатформенность** – работает на Windows, Linux и macOS.
- **Удобно для автоматизации** – идеально подходит для пакетной обработки или интеграции в CI‑конвейеры.

## Предварительные требования
Прежде чем начать, убедитесь, что у вас есть следующее:

### Настройка среды разработки Java
1. Установите JDK: Убедитесь, что на вашей системе установлен Java Development Kit (JDK). Вы можете скачать его с [сайта Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Настройка IDE: Выберите интегрированную среду разработки (IDE), такую как IntelliJ IDEA, Eclipse или NetBeans, и установите её на свой компьютер.

### Установка Aspose.Tasks for Java
1. Скачайте Aspose.Tasks for Java: Перейдите на [страницу загрузки](https://releases.aspose.com/tasks/java/) и получите последнюю версию Aspose.Tasks for Java.
2. Интегрируйте с проектом: Добавьте библиотеку Aspose.Tasks for Java в ваш Java‑проект, указав её в зависимостях.

## Импорт пакетов
Чтобы начать, вам необходимо импортировать необходимые пакеты из Aspose.Tasks for Java в ваш проект. Этот шаг гарантирует доступ к требуемой функциональности.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Шаг 1: Создать объект проекта
Создание **объекта проекта** — первый шаг любой работы с MS Project. Он представляет весь файл проекта в памяти.

```java
Project project = new Project();
```

## Шаг 2: Добавить ресурс (add resource ms project)
Теперь мы **добавим ресурс MS Project** с помощью коллекции Resources. Имя ресурса может быть любым, подходящим для вашего расписания.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Шаг 3: Установить свойства ресурса (how to set rates)
Здесь мы **устанавливаем стандартную ставку** и также демонстрируем, как задать ставку за сверхурочную работу. Эти ставки хранятся как значения `BigDecimal` для сохранения точности.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| `NullPointerException` при вызове `set` | Ресурс был добавлен некорректно. | Убедитесь, что `project.getResources().add()` возвращает ненулевой `Resource`. |
| Ставки отображаются как 0 в сохранённом файле | Используется `int` вместо `BigDecimal`. | Всегда используйте `BigDecimal.valueOf()` для денежных значений. |
| Лицензия не найдена | Файл лицензии не загружен до создания `Project`. | Загрузите лицензию (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) в начале программы. |

## Заключение
Следуя этим шагам, вы научились **создавать объект проекта**, **добавлять ресурс MS Project** и **устанавливать стандартную ставку** вместе с другими свойствами ресурса. Это позволяет автоматизировать расчёты затрат, генерировать пользовательские отчёты и полностью управлять ресурсами MS Project из Java.

## Часто задаваемые вопросы
### Может ли Aspose.Tasks for Java работать со сложными файлами MS Project?
Да, Aspose.Tasks for Java способен обрабатывать широкий спектр форматов файлов MS Project, включая сложные файлы с обширными иерархиями задач.

### Доступна ли бесплатная пробная версия Aspose.Tasks for Java?
Да, вы можете получить бесплатную пробную версию Aspose.Tasks for Java [здесь](https://releases.aspose.com/).

### Где я могу найти поддержку Aspose.Tasks for Java?
Вы можете получить помощь и участвовать в обсуждениях, связанных с Aspose.Tasks for Java, на [форуме поддержки](https://forum.aspose.com/c/tasks/15).

### Как получить временную лицензию для Aspose.Tasks for Java?
Вы можете получить временную лицензию на странице [temporary license page](https://purchase.aspose.com/temporary-license/) для целей оценки.

### Где можно приобрести лицензированную версию Aspose.Tasks for Java?
Вы можете приобрести лицензированную версию Aspose.Tasks for Java на [странице покупки](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Последнее обновление:** 2026-01-18  
**Тестировано с:** Aspose.Tasks for Java 24.12 (последняя версия на момент написания)  
**Автор:** Aspose