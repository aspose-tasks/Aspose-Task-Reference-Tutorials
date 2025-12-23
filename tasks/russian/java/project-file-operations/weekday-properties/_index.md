---
date: 2025-12-23
description: Узнайте, как использовать Aspose.Tasks для Java, чтобы обновлять график
  проекта, устанавливать первый день недели, изменять количество дней в месяце и эффективно
  настраивать календарь проекта.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Управление свойствами дней недели
url: /ru/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Управление свойствами будних дней

## Введение
Aspose.Tasks for Java (aspose tasks java) — это надёжный API, позволяющий разработчикам Java работать с файлами Microsoft Project без необходимости установки Microsoft Project. В этом руководстве вы узнаете, как **load an MPP file**, **set week start day**, **change days per month**, а также **customize the project calendar** — все необходимые шаги для обновления графика проекта. К концу вы сможете программно изменять свойства будних дней и сохранять изменения в нужном формате.

## Быстрые ответы
- **Какой основной класс для работы с проектами?** `Project` из библиотеки Aspose.Tasks.  
- **Как изменить день начала недели?** Используйте `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **Могу ли я загрузить существующий файл .mpp?** Да — создайте экземпляр `Project`, указав путь к файлу.  
- **Какой метод сохраняет проект в формате XML?** `project.save(path, SaveFileFormat.Xml)`.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для оценки; лицензия требуется для продакшн.

## Требования
Перед началом убедитесь, что у вас есть следующее:

- **Java Development Kit (JDK)** – установлена последняя версия.  
- **Aspose.Tasks for Java library** – скачайте её [здесь](https://releases.aspose.com/tasks/java/).  
- **IDE** (например, IntelliJ IDEA, Eclipse или NetBeans).  

## Импорт пакетов
Чтобы начать, импортируйте необходимые классы Aspose.Tasks:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Теперь пройдем каждый шаг управления свойствами будних дней.

## Шаг 1: Загрузка файла MPP
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Здесь мы **загружаем существующий файл .mpp** (`load mpp file`), чтобы мы могли просмотреть и изменить настройки его календаря.*

## Шаг 2: Отображение текущих свойств будних дней
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Этот код выводит текущие **день начала недели**, **дни в месяц**, **минуты в день** и **минуты в неделю** — основные элементы, которые часто нужны для **настройки календаря проекта**.

## Шаг 3: Установка новых свойств будних дней
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
На этом шаге мы **устанавливаем день начала недели** на понедельник, **изменяем количество дней в месяц** на 24 и корректируем количество минут в день и в неделю. Такие настройки типичны, когда необходимо **обновить график проекта**, чтобы он соответствовал нестандартному рабочему календарю.

## Шаг 4: Сохранение обновленного проекта
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Изменённый проект сохраняется в виде XML‑файла, что упрощает его обмен или импорт в другие инструменты.

## Шаг 5: Подтверждение операции
```java
System.out.println("Process completed Successfully");
```
Простое сообщение в консоли сообщает, что процесс завершён без ошибок.

## Распространённые проблемы и советы
- **Неправильный путь к файлу** – Убедитесь, что `dataDir` заканчивается слешем, или используйте `Paths.get(...)` для кроссплатформенных путей.  
- **Лицензия не установлена** – В продакшн‑среде вызовите `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` перед созданием `Project`.  
- **Неожиданный день начала недели** – Убедитесь, что используете правильное значение перечисления `DayType` (например, `DayType.Sunday`).  

## Часто задаваемые вопросы

**Q: Может ли Aspose.Tasks for Java работать со сложными структурами проектов?**  
A: Да, Aspose.Tasks for Java предоставляет всестороннюю поддержку для работы со сложными структурами проектов без труда.

**Q: Совместим ли Aspose.Tasks for Java с различными версиями файлов Microsoft Project?**  
A: Абсолютно, Aspose.Tasks for Java поддерживает различные версии файлов Microsoft Project, обеспечивая совместимость на разных платформах.

**Q: Могу ли я интегрировать Aspose.Tasks for Java в свои существующие Java‑приложения?**  
A: Да, Aspose.Tasks for Java предлагает бесшовные возможности интеграции, позволяя улучшать ваши Java‑приложения мощными функциями управления проектами.

**Q: Предоставляет ли Aspose.Tasks for Java документацию и поддержку?**  
A: Да, вы можете получить доступ к обширной документации и поддержке сообщества для Aspose.Tasks for Java на их [website](https://releases.aspose.com/).

**Q: Доступна ли бесплатная пробная версия Aspose.Tasks for Java?**  
A: Да, вы можете скачать бесплатную пробную версию Aspose.Tasks for Java с их [website](https://reference.aspose.com/tasks/java/) для изучения возможностей перед покупкой.

---

**Последнее обновление:** 2025-12-23  
**Тестировано с:** Aspose.Tasks for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}