---
title: Чтение проекта MS от Primavera с помощью Aspose.Tasks для Java
linktitle: Прочтите проект Primavera в Aspose.Tasks
second_title: API Aspose.Tasks Java
description: Узнайте, как легко читать файлы MS Project из Primavera XML с помощью Aspose.Tasks для Java. Повысьте эффективность управления проектами.
type: docs
weight: 20
url: /ru/java/project-management/read-primavera/
---
## Введение
В управлении проектами совместимость между различными программными платформами имеет решающее значение для бесперебойного рабочего процесса. Aspose.Tasks для Java обеспечивает надежную функциональность для чтения файлов Microsoft Project из Primavera XML. Это руководство проведет вас через процесс чтения файлов MS Project из Primavera с помощью Aspose.Tasks for Java, что позволит вам эффективно исследовать свойства задач, специфичные для Primavera.
## Предварительные условия
Прежде чем продолжить, убедитесь, что у вас установлены и настроены следующие необходимые компоненты:
1. Java Development Kit (JDK): убедитесь, что в вашей системе установлен JDK.
2.  Aspose.Tasks для Java: Загрузите и установите Aspose.Tasks для Java с сайта[здесь](https://releases.aspose.com/tasks/java/).

## Импортировать пакеты
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Шаг 1. Настройте каталог данных.
```java
String dataDir = "Your Data Directory";
```
 Обязательно замените`"Your Data Directory"` с фактическим путем к вашему каталогу данных.
## Шаг 2. Считайте проект из Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Обязательно замените`"PrimaveraProject.xml"` с фактическим именем вашего XML-файла Primavera.
## Шаг 3. Перебор задач и получение свойств, специфичных для Primavera
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Этот код выполняет итерацию каждой задачи в проекте, печатая соответствующие свойства, специфичные для Primavera.

## Заключение
В этом руководстве вы узнали, как читать файлы MS Project из Primavera XML с помощью Aspose.Tasks для Java. Эта функциональность обеспечивает плавную интеграцию и анализ данных проекта на разных платформах, повышая общую эффективность управления проектами.
## Часто задаваемые вопросы
### Вопрос: Могу ли я изменить свойства задач, специфичные для Primavera, с помощью Aspose.Tasks for Java?
О: Да, Aspose.Tasks for Java предоставляет API для изменения свойств задач, специфичных для Primavera, по мере необходимости.
### Вопрос: Поддерживает ли Aspose.Tasks for Java чтение файлов других форматов проектов?
О: Да, Aspose.Tasks for Java поддерживает чтение различных форматов файлов проектов, включая MPP, XML и Primavera XML.
### Вопрос: Подходит ли Aspose.Tasks для Java для приложений управления проектами корпоративного уровня?
Ответ: Конечно, Aspose.Tasks for Java предлагает надежные функции и масштабируемость, что делает его подходящим для приложений управления проектами корпоративного уровня.
### Вопрос: Могу ли я извлечь информацию о ресурсах из проектов Primavera с помощью Aspose.Tasks для Java?
О: Да, Aspose.Tasks for Java позволяет извлекать информацию о ресурсах вместе с деталями задач из проектов Primavera.
### Вопрос: Где я могу найти дополнительную поддержку или документацию для Aspose.Tasks для Java?
 О: Вы можете найти подробную документацию и доступ к форумам для поддержки на[Документация Aspose.Tasks для Java](https://reference.aspose.com/tasks/java/) страница.