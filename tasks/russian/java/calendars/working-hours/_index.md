---
date: 2026-02-05
description: Узнайте, как определять рабочие дни и рассчитывать продолжительность
  задачи, извлекая рабочие часы из календарей MS Project с помощью Aspose.Tasks для
  Java.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Определение рабочих дней и рабочих часов с Aspose.Tasks
url: /ru/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Определение рабочих дней и рабочих часов с Aspose.Tasks

## Введение
Управление календарями проекта является ключевой частью успешного планирования. В этом руководстве вы **определите рабочие дни** для любой задачи и **извлечёте рабочие часы** из календаря MS Project с помощью Aspose.Tasks for Java. К концу руководства вы сможете **рассчитать продолжительность задачи**, настроить рабочие часы и надёжно **загрузить файл MPP**, чтобы получить необходимые данные. Вы также увидите, как **читать файлы MS Project** без установки Microsoft Project, что делает автоматизацию возможной на любой платформе.

## Быстрые ответы
- **Что означает «определить рабочие дни»?** Это означает определение, какие даты в календаре считаются рабочими для данной задачи.  
- **Какую библиотеку следует использовать?** Aspose.Tasks for Java предоставляет полнофункциональный API для работы с файлами MS Project.  
- **Сколько времени занимает реализация?** Обычно 10–15 минут для базового извлечения.  
- **Нужна ли лицензия?** Доступна бесплатная пробная версия; для использования в продакшене требуется коммерческая лицензия.  
- **Можно ли настроить рабочие часы?** Да — вы можете изменять календари, добавлять праздники и задавать пользовательские диапазоны рабочего времени.  

## Что такое «определить рабочие дни»?
Когда задача планируется, календарь проекта определяет, какие дни являются рабочими, а какие — нерабочими (выходные, праздники). Определение рабочих дней означает запрос к этому календарю, чтобы точно знать, когда может происходить работа, что необходимо для точных расчётов **calculate task duration**.

## Почему использовать Aspose.Tasks для получения рабочих часов?
- **Microsoft Project не требуется** — вы можете читать файлы MS Project напрямую из кода Java.  
- **Полная поддержка календарей** — включает календарь по умолчанию, ресурсный и календарь задач.  
- **Высокая производительность** — быстро обрабатывайте крупные проекты.  
- **Обширная документация** — примеры и справочник API доступны.  

## Предварительные требования
1. **Java Development Kit (JDK)** – версия 8 или выше.  
2. **Aspose.Tasks for Java** – скачайте последнюю JAR‑файл [здесь](https://releases.aspose.com/tasks/java/).  
3. Базовые знания программирования на Java.  

## Импорт пакетов
Сначала импортируйте основное пространство имён Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Как загрузить файл MPP с помощью Aspose.Tasks?
Загрузка файла проекта — первый шаг к любому анализу календаря. API позволяет **загрузить файл MPP** одной строкой кода, без необходимости использовать пользовательский интерфейс MS Project.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Получение информации о задаче и календаре
Выберите задачу, которую хотите проанализировать, и получите её связанный календарь. Здесь мы **извлекаем рабочие часы** для задачи:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Определение дат начала и окончания
Установите временное окно, для которого вы хотите **определить рабочие дни**. Использование дат начала и окончания задачи гарантирует, что вы оцениваете только соответствующий период.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Итерация по датам
Пройдите в цикле каждую дату длительности задачи. Этот цикл поможет нам позже **настроить рабочие часы**, если потребуется:

```java
java.util.Calendar tempDate = calStartDate;
```

## Расчёт продолжительности
Во время итерации мы проверяем, является ли каждый день рабочим, суммируем рабочие часы и в конце вычисляем продолжительность задачи в минутах, часах и днях. Этот шаг демонстрирует, как программно **calculate working days** и **calculate task duration**.

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## Как настроить рабочие часы и праздники
Aspose.Tasks позволяет изменять диапазоны рабочего времени календаря и добавлять исключения, такие как праздники. Вы можете вызвать `taskCalendar.addWorkingTime()` или `taskCalendar.addException()`, чтобы адаптировать расписание к политике вашей организации. Это полезно, когда стандартный график 9‑5 не соответствует реальности.

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|---------|
| **Task returns `null` for calendar** | Убедитесь, что у задачи действительно назначен календарь; иначе она наследует календарь проекта по умолчанию. |
| **Incorrect duration because of holidays** | Проверьте, что праздники определены в календаре задачи или в базовом календаре проекта. |
| **Time zone mismatch** | Используйте `java.util.TimeZone`, чтобы при необходимости согласовать часовой пояс календаря с вашей системой. |

## Часто задаваемые вопросы
### Q: Может ли Aspose.Tasks for Java работать со сложными структурами проекта?
A: Да, Aspose.Tasks for Java предоставляет всестороннюю поддержку работы со сложными структурами проекта, включая задачи, ресурсы и календари.

### Q: Совместим ли Aspose.Tasks for Java с разными версиями MS Project?
A: Абсолютно, Aspose.Tasks for Java поддерживает различные версии MS Project, обеспечивая совместимость в разных средах.

### Q: Могу ли я настроить рабочие часы и праздники в календарях проекта?
A: Да, вы можете легко настроить рабочие часы и праздники в соответствии с требованиями проекта, используя API Aspose.Tasks for Java.

### Q: Предоставляет ли Aspose.Tasks for Java поддержку и документацию?
A: Да, Aspose.Tasks for Java предоставляет обширную документацию и специализированные форумы поддержки, помогающие разработчикам эффективно использовать его возможности.

### Q: Доступна ли пробная версия Aspose.Tasks for Java?
A: Да, вы можете получить бесплатную пробную версию Aspose.Tasks for Java [здесь](https://releases.aspose.com/).

## Заключение
В этом руководстве мы продемонстрировали, как **определить рабочие дни**, **извлечь рабочие часы** и **рассчитать продолжительность задачи** из календаря MS Project с помощью Aspose.Tasks for Java. Следуя приведённым шагам, вы сможете автоматизировать анализ расписания, настраивать календари и поддерживать планы проекта точными и актуальными. Теперь у вас есть инструменты для **чтения данных MS Project**, **загрузки файла MPP** и выполнения точных расчётов продолжительности без необходимости использовать Microsoft Project.

---

**Последнее обновление:** 2026-02-05  
**Тестировано с:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}