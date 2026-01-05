---
date: 2026-01-05
description: Узнайте, как установить дату начала проекта и сохранить XML MS Project
  с помощью Aspose.Tasks для Java. Пошаговое руководство для Java‑разработчиков.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Установить дату начала проекта с Aspose.Tasks для Java
url: /ru/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Установка даты начала проекта с Aspose.Tasks для Java

## Введение
В этом руководстве вы узнаете, **как установить дату начала проекта** в файле Microsoft Project и затем **сохранить MS Project XML** с помощью библиотеки Aspose.Tasks для Java. Независимо от того, автоматизируете ли вы конвейер отчетности или создаёте собственный инструмент управления проектами, освоение этой задачи сэкономит ваше время и избавит от ручных ошибок.

## Быстрые ответы
- **Какой основной метод для установки даты начала?** Используйте `project.set(Prj.START_DATE, …)`.
- **В каком формате следует экспортировать файл?** Сохраните его как XML с помощью `SaveFileFormat.Xml`.
- **Нужна ли лицензия для этой операции?** Доступна пробная версия, но полная лицензия удаляет водяные знаки.
- **Можно ли изменить дату начала после создания задач?** Да, обновите свойство проекта перед добавлением задач.
- **Совместимо ли это со всеми версиями MS Project?** Aspose.Tasks поддерживает XML, MPP и другие форматы.

## Что такое «Установка даты начала проекта»?
Установка даты начала проекта определяет базовый календарь, от которого начинаются все расчёты планирования задач. Это первый шаг в программном построении надёжного графика проекта.

## Почему стоит использовать Aspose.Tasks для Java?
Aspose.Tasks предоставляет чистый Java‑API, который работает на любой платформе без необходимости установки Microsoft Project. Он позволяет быстро создавать, изменять и экспортировать данные проекта, что делает его идеальным для серверной автоматизации.

## Предварительные требования
1. **Java Development Kit (JDK)** – любая современная версия JDK.  
2. **Aspose.Tasks for Java** – загрузить можно [здесь](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse или ваш предпочтительный Java‑IDE.

## Импорт пакетов
Сначала импортируйте необходимые классы:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Шаг 1: Настройка каталога данных
Определите, где будут храниться сгенерированные файлы.

```java
String dataDir = "Your Data Directory";
```

### Шаг 2: Создание экземпляра проекта
Создайте новый пустой проект.

```java
Project project = new Project();
```

### Шаг 3: Установка свойств информации о проекте
Здесь мы **устанавливаем дату начала проекта** и связанные свойства расписания.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Шаг 4: Сохранение MS Project XML
Экспортируйте настроенный проект в XML‑файл.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Распространённые проблемы и решения
- **Неправильный формат даты:** Убедитесь, что используете `java.util.Calendar` и вызываете `getTime()` перед присвоением.  
- **Файл не сохраняется:** Проверьте, что `dataDir` указывает на существующую папку с правом записи.  
- **Предупреждения о лицензии:** Пробная версия добавляет водяные знаки; примените действующую лицензию, чтобы их убрать.

## Часто задаваемые вопросы

### В: Можно ли использовать Aspose.Tasks для Java для чтения файлов MS Project?  
**О:** Да, Aspose.Tasks для Java предоставляет мощные возможности как для чтения, так и для записи файлов MS Project.

### В: Совместим ли Aspose.Tasks для Java с разными версиями MS Project?  
**О:** Абсолютно, Aspose.Tasks для Java поддерживает различные форматы MS Project, обеспечивая широкую совместимость.

### В: Есть ли ограничения у пробной версии Aspose.Tasks для Java?  
**О:** Пробная версия позволяет изучать библиотеку, но добавляет водяные знаки в выходные файлы.

### В: Как получить поддержку по Aspose.Tasks для Java?  
**О:** Вы можете обратиться за помощью на форуме сообщества Aspose.Tasks [здесь](https://forum.aspose.com/c/tasks/15).

### В: Можно ли приобрести временную лицензию для Aspose.Tasks для Java?  
**О:** Да, временные лицензии доступны для краткосрочного использования. Получить её можно [здесь](https://purchase.aspose.com/temporary-license/).

### В: Сохраняет ли экспорт в XML пользовательские поля?  
**О:** Да, при сохранении с помощью `SaveFileFormat.Xml` сохраняются все пользовательские атрибуты и расширенные поля.

### В: Можно ли изменить дату начала после добавления задач?  
**О:** Вы можете обновить дату начала в любой момент до сохранения; просто снова вызовите `project.set(Prj.START_DATE, …)`.

---

**Последнее обновление:** 2026-01-05  
**Тестировано с:** Aspose.Tasks for Java 24.12  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}