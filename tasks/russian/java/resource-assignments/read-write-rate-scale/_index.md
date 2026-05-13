---
date: 2026-01-10
description: Узнайте, как читать шкалу ставок и управлять назначениями ресурсов в
  Aspose.Tasks для Java. Определите материальный ресурс, как установить шкалу и назначить
  ресурсы задаче.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как читать шкалу ставок и записывать шкалу ставок для назначений ресурсов в
  Aspose.Tasks
url: /ru/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как читать и записывать шкалу ставок для назначений ресурсов в Aspose.Tasks

В этом руководстве вы узнаете **как читать ставку** и настроите параметры шкалы ставок для назначений ресурсов, используя Aspose.Tasks для Java. Независимо от того, создаёте ли вы планировщик, инструмент отчётности или просто хотите автоматизировать обновления проекта, освоение управления шкалой ставок даёт точный контроль над материальными и трудовыми ресурсами.

## Быстрые ответы
- **Какой основной класс для работы со ставками?** `ResourceAssignment` с свойством `Asn.RATE_SCALE`.  
- **Какой enum определяет варианты шкалы?** `RateScaleType` (Day, Week, Month и т.д.).  
- **Нужна ли лицензия для запуска примера?** Бесплатная оценочная лицензия работает для тестирования; коммерческая лицензия требуется для продакшн.  
- **Можно ли изменить шкалу после сохранения?** Да – перезагрузите проект и измените `Asn.RATE_SCALE`, как показано.  
- **Поддерживаемые IDE?** Любая Java IDE (IntelliJ IDEA, Eclipse, NetBeans) может компилировать код.

## Что такое шкала ставок?
Шкала ставок определяет единицу времени (день, неделя, месяц и т.д.), к которой применяется ставка стоимости ресурса. Регулирование шкалы позволяет точно моделировать потребление материалов или трудовые затраты.

## Зачем читать и записывать шкалу ставок?
Чтение текущей шкалы помогает проанализировать существующие графики, а запись новой шкалы позволяет согласовать ресурсы с политиками биллинга или потребления проекта. Это особенно полезно при **определении стоимости материального ресурса** или когда необходимо **установить шкалу** для нестандартных трудовых календарей.

## Предварительные требования
Перед началом убедитесь, что у вас есть следующее:
1. **Среда разработки Java** – установлен JDK 8 или выше.  
2. **Библиотека Aspose.Tasks for Java** – скачайте и установите библиотеку по ссылке [here](https://releases.aspose.com/tasks/java/).

## Импорт пакетов
Сначала импортируйте необходимые классы Aspose.Tasks.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Шаг 1: Настройте ваш Java‑проект
Создайте проект Maven или Gradle и добавьте JAR‑файл Aspose.Tasks в classpath. Этот шаг гарантирует, что компилятор найдёт импортированные классы.

## Шаг 2: Загрузите файл проекта
Загрузите существующий файл Microsoft Project, с которым хотите работать.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Шаг 3: Добавьте задачу
Создайте новую задачу, которая позже получит назначения ресурсов.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Шаг 4: Определите ресурсы
Здесь мы **определяем материальный ресурс** и обычный трудовой ресурс. Обратите внимание на использование `ResourceType.Material` для ресурса типа материал.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Шаг 5: Назначьте ресурсы задаче
Теперь мы **назначаем ресурсы задаче** и указываем **как установить шкалу**, используя `RateScaleType.Week`. Это демонстрирует как чтение, так и запись шкалы ставок.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Шаг 6: Сохраните проект
Сохраните изменения в новый файл, чтобы позже можно было проверить сохранённую шкалу ставок.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Шаг 7: Получите назначения ресурсов
Перезагрузите сохранённый проект и **прочитайте ставку** шкалы, чтобы подтвердить, что она была записана корректно.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Распространённые ошибки и советы
- **Несоответствие UID** – При получении назначений по UID убедитесь, что значения UID совпадают с назначенными при создании.  
- **Неправильный тип ресурса** – Использование `ResourceType.Material` для рабочего ресурса приведёт к неожиданным результатам расчётов ставок.  
- **Формат сохранения** – Всегда сохраняйте с помощью `SaveFileFormat.Mpp` (или другого поддерживаемого формата), чтобы сохранить пользовательские поля, такие как шкала ставок.

## Заключение
Управление и проверка шкалы ставок для назначений ресурсов в Aspose.Tasks для Java становится простой задачей, как только вы знакомы с соответствующими классами и свойствами. Следуя этому руководству, вы сможете **читать информацию о ставке**, **определять материальные ресурсы**, **устанавливать шкалу** и **назначать ресурсы задаче** с уверенностью.

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Tasks для Java с любой Java IDE?**  
A: Да, Aspose.Tasks для Java совместим со всеми основными Java IDE, включая IntelliJ IDEA, Eclipse и NetBeans.

**Q: Поддерживает ли Aspose.Tasks другие форматы файлов, кроме MPP?**  
A: Да, Aspose.Tasks поддерживает различные форматы файлов, включая MPP, XML и HTML.

**Q: Подходит ли Aspose.Tasks для управления проектами корпоративного уровня?**  
A: Абсолютно, Aspose.Tasks предлагает обширный набор функций для управления проектами любой масштабности, что делает его подходящим для корпоративного уровня управления проектами.

**Q: Можно ли дополнительно настраивать назначения ресурсов, помимо шкалы ставок?**  
A: Да, Aspose.Tasks предоставляет широкие возможности для настройки назначений ресурсов, включая корректировку стоимости, работы и длительности.

**Q: Есть ли сообщество или форум поддержки Aspose.Tasks?**  
A: Да, вы можете получить поддержку и пообщаться с другими пользователями на форуме Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}