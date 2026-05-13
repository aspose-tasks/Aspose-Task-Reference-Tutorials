---
date: 2026-01-10
description: Узнайте, как изменить контур и сгенерировать временные данные для назначений
  ресурсов с помощью Aspose.Tasks for Java, повышая эффективность управления проектами.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как изменить контур в Aspose.Tasks для данных с временными фазами
url: /ru/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как изменить контур в Aspose.Tasks для данных с фазированием времени

## Введение
В этом руководстве вы узнаете **как изменить контур** для назначения ресурса и сгенерировать данные с фазированием времени, используя Aspose.Tasks для Java. Данные с фазированием времени показывают распределение работы по графику проекта, позволяя точно настраивать расписания, балансировать нагрузку и принимать решения, основанные на данных.

## Быстрые ответы
- **Что такое контур?** Контур работы определяет, как усилия распределяются в течение длительности задачи (например, Flat, Turtle, Bell).  
- **Зачем менять контур?** Чтобы отразить реалистичные модели работы, такие как предварительное или последующее распределение усилий.  
- **Какая библиотека требуется?** Aspose.Tasks для Java (любая актуальная версия).  
- **Нужна ли лицензия?** Да, для использования в продакшене требуется действующая лицензия Aspose.Tasks.  
- **Можно ли увидеть результаты в консоли?** Пример выводит даты начала и значения для каждого фазированного сегмента.

## Что означает «как изменить контур»?
Изменение контура означает обновление свойства `WORK_CONTOUR` у объекта `ResourceAssignment`. Aspose.Tasks поддерживает несколько предопределённых контуров (Flat, Turtle, Bell и др.), которые влияют на распределение работы во времени.

## Почему стоит использовать Aspose.Tasks для генерации данных с фазированием времени?
- **Точная отчетность:** Экспорт точного распределения работы для инструментов отчетности.  
- **Планирование сценариев:** Тестирование разных контуров без изменения исходного расписания.  
- **Автоматизация:** Интеграция в CI‑конвейеры для автоматической проверки состояния проекта.

## Предварительные требования
Прежде чем начать, убедитесь, что у вас есть следующие требования:
1. Java Development Kit (JDK): Убедитесь, что JDK установлен в вашей системе. Вы можете скачать и установить JDK по ссылке [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Библиотека Aspose.Tasks для Java: Необходимо иметь библиотеку Aspose.Tasks для Java. Вы можете скачать её с [website](https://releases.aspose.com/tasks/java/).

## Импорт пакетов
Сначала импортируем необходимые пакеты для работы с Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Шаг 1: Чтение исходного файла MPP
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Шаг 2: Получение задачи и назначения ресурса
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Как изменить контур – Flat (по умолчанию)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Как изменить контур – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Распространённые проблемы и советы
- **Контур не обновляется?** Убедитесь, что вызываете `firstRA.set(Asn.WORK_CONTOUR, …)` *до* получения фазированных данных.
- **Неожиданные значения?** Проверьте, что даты начала и окончания задачи правильно заданы в исходном файле MPP.
- **Совет по производительности:** Переиспользуйте один экземпляр `Project` при переборе нескольких контуров, чтобы избежать лишних операций ввода‑вывода файлов.

## Часто задаваемые вопросы
### Можно ли использовать Aspose.Tasks с другими библиотеками Java?
Да, Aspose.Tasks можно интегрировать с другими библиотеками Java для расширения возможностей управления проектами.

### Подходит ли Aspose.Tasks для крупномасштабных корпоративных проектов?
Безусловно, Aspose.Tasks разработан для работы с проектами любого размера, включая крупномасштабные корпоративные инициативы.

### Предоставляет ли Aspose.Tasks поддержку различных форматов файлов проектов?
Да, Aspose.Tasks поддерживает множество форматов, таких как MPP, XML и MPX.

### Можно ли настроить контуры работы в соответствии с требованиями проекта?
Да, вы можете определить пользовательские контуры работы, соответствующие конкретным потребностям планирования.

### Есть ли сообщество, где можно получить помощь по Aspose.Tasks?
Да, вы можете посетить [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) для получения поддержки и обсуждения.

---

**Последнее обновление:** 2026-01-10  
**Тестировано с:** Aspose.Tasks для Java (последний релиз)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}