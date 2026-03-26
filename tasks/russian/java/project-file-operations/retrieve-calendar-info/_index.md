---
date: 2025-12-20
description: Узнайте, как использовать Aspose.Tasks для извлечения сведений о календаре
  проекта из файлов Microsoft Project с помощью Java. Пошаговое руководство с примерами
  кода.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как использовать Aspose.Tasks для получения информации о календаре MS Project
url: /ru/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать Aspose.Tasks для получения информации о календаре MS Project

## Введение
В этом руководстве **вы узнаете, как использовать Aspose.Tasks** для получения простой информации о календаре из файлов Microsoft Project. Доступ к данным календаря, таким как рабочие дни, часы и исключения, необходим, когда необходимо **получить информацию о календарном проекте** для региональных, региональных или пользовательской логики планирования. Давайте пройдем процесс шаг за шагом.

## Быстрые ответы
- **Какая библиотека используется в этом руководстве?** Aspose.Tasks для Java.
- **Какое завершение ключевого слова эффект?** *как использовать aspose.tasks*.
- **Что можно потерять?** Календари проекта, включая рабочие дни и часы.
- **Нужна ли лицензия?** Доступна бесплатная пробная версия; для продакшн‑использования требуется лицензия.
- **Какая версия Java соответствует?** Java8 или выше.

## Зачем извлекать информацию из календаря проекта?
Календари проекта определяют задачи даты, ресурсы и расчеты общей временной шкалы. Извлекая эти данные, вы можете:
- Создавать пользовательские отчеты, отражающие реальные рабочие графики.
- Синхронизировать время Microsoft Project с постоянными переменами (ERP, BI и т.д.).
- Выполняете анализ «что-если», программно изменяя настройки календаря.

## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть:

- Базовые знания по программирования на Java.
- Установленный Java Development Kit (JDK).
- Библиотека Aspose.Tasks для Java. Скачать ее можно [здесь](https://releases.aspose.com/tasks/java/).

## Импорт пакетов
Сначала импортируйте необходимые классы Aspose.Tasks в ваш Java‑проект.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Шаг 1: Настройка каталога данных
Определите папку, содержащую ваш файл *.mpp*.

```java
String dataDir = "Your Data Directory";
```

Замените `"Your Data Directory"` на абсолютный путь к папке, где находится **project.mpp**.

## Шаг 2: Определение единиц времени
Создайте константы, помогающие преобразовать внутреннее представление времени в человекочитаемые часы.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Эти значения выражаются в микросекундах — так Aspose.Tasks хранит время внутри.

## Шаг 3: Создание экземпляра проекта
Загрузите файл Microsoft Project в объект `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Конструктор `Project` разбирает файл *.mpp* и делает все данные проекта, включая календари, доступными через API.

## Шаг 4: Получение информации о календарях
Получите коллекцию календарей, определённых в проекте.

```java
CalendarCollection alCals = project.getCalendars();
```

Проект может содержать несколько календарей (стандартный, ресурсный и пользовательские). Эта коллекция даёт доступ к каждому из них.

## Шаг 5: Перебор календарей
Пройдитесь по каждому календарю, отобразив его UID, имя и рабочие дни с соответствующими часами.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

Внутренний цикл проверяет каждый объект `WeekDay`. Если день помечен как рабочий, выводится тип дня (Monday, Tuesday, …) вместе с рассчитанными рабочими часами.

## Шаг 6: Отображение сообщения о завершении
Сигнализируйте о завершении процесса извлечения.

```java
System.out.println("Process completed Successfully");
```

## Заключение
Следуя этим шагам, **теперь вы знаете, как использовать Aspose.Tasks для извлечения информации о календаре проекта** из файла MS Project с помощью Java. Вы можете интегрировать эту логику в более крупные приложения, автоматизировать отчётность или синхронизировать расписание с другими корпоративными цепями.

## Часто задаваемые вопросы

**В: Можно ли использовать Aspose.Tasks с другими языками программирования?**
О: Да, Aspose.Tasks поддерживает несколько платформ и языков, включая .NET, C++, Python и Java.

**В: Доступна ли бесплатная пробная версия Aspose.Tasks?**
О: Да, бесплатную пробную версию можно скачать [здесь](https://releases.aspose.com/).

**Вопрос: Как получить поддержку для Aspose.Tasks?**
A: Поддержку можно получить на форуме сообщества Aspose.Tasks [здесь](https://forum.aspose.com/c/tasks/15).

**В: Можно ли получить временную лицензию для Aspose.Tasks?**
О: Да, временные лицензии доступны для покупки [здесь](https://purchase.aspose.com/temporary-license/).

**В: Где найти подробную документацию по Aspose.Tasks?**
О: Документацию можно [посмотретьздесь](https://reference.aspose.com/tasks/java/).

---

**Последнее обновление:** 20 декабря 2025 г.
**Протестировано с помощью:** Aspose.Tasks для Java 24.12 (последняя версия на момент написания статьи).
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}