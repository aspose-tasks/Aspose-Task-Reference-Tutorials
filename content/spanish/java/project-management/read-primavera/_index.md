---
title: Lea MS Project desde Primavera con Aspose.Tasks para Java
linktitle: Leer proyecto de Primavera en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a leer archivos de MS Project desde Primavera XML sin problemas utilizando Aspose.Tasks para Java. Mejore la eficiencia de la gestión de sus proyectos.
type: docs
weight: 20
url: /es/java/project-management/read-primavera/
---
## Introducción
En la gestión de proyectos, la interoperabilidad entre diferentes plataformas de software es crucial para un flujo de trabajo fluido. Aspose.Tasks para Java proporciona una funcionalidad sólida para leer archivos de Microsoft Project desde Primavera XML. Este tutorial lo guiará a través del proceso de lectura de archivos de MS Project desde Primavera usando Aspose.Tasks para Java, permitiéndole examinar las propiedades específicas de Primavera de las tareas de manera eficiente.
## Requisitos previos
Antes de continuar, asegúrese de tener instalados y configurados los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema.
2.  Aspose.Tasks para Java: descargue e instale Aspose.Tasks para Java desde[aquí](https://releases.aspose.com/tasks/java/).

## Importar paquetes
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Paso 1: configurar el directorio de datos
```java
String dataDir = "Your Data Directory";
```
 Asegúrese de reemplazar`"Your Data Directory"` con la ruta real a su directorio de datos.
## Paso 2: leer el proyecto desde Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Asegúrese de reemplazar`"PrimaveraProject.xml"` con el nombre real de su archivo Primavera XML.
## Paso 3: iterar a través de tareas y recuperar propiedades específicas de Primavera
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
Este código recorre en iteración cada tarea del proyecto, imprimiendo propiedades relevantes específicas de Primavera.

## Conclusión
En este tutorial, aprendió a leer archivos de MS Project desde Primavera XML usando Aspose.Tasks para Java. Esta funcionalidad permite una integración y un análisis perfectos de los datos del proyecto en diferentes plataformas, lo que mejora la eficiencia general de la gestión de proyectos.
## Preguntas frecuentes
### P: ¿Puedo modificar las propiedades específicas de Primavera de las tareas usando Aspose.Tasks para Java?
R: Sí, Aspose.Tasks para Java proporciona API para modificar las propiedades de las tareas específicas de Primavera según sea necesario.
### P: ¿Aspose.Tasks para Java admite la lectura de otros formatos de archivos de proyecto?
R: Sí, Aspose.Tasks para Java admite la lectura de varios formatos de archivos de proyecto, incluidos MPP, XML y Primavera XML.
### P: ¿Aspose.Tasks para Java es adecuado para aplicaciones de gestión de proyectos de nivel empresarial?
R: Por supuesto, Aspose.Tasks para Java ofrece características sólidas y escalabilidad, lo que lo hace adecuado para aplicaciones de gestión de proyectos de nivel empresarial.
### P: ¿Puedo extraer información de recursos de proyectos Primavera usando Aspose.Tasks para Java?
R: Sí, Aspose.Tasks para Java le permite extraer información de recursos junto con detalles de tareas de proyectos Primavera.
### P: ¿Dónde puedo encontrar soporte o documentación adicional para Aspose.Tasks para Java?
 R: Puede encontrar documentación completa y acceso a foros de soporte en el[Aspose.Tasks para la documentación de Java](https://reference.aspose.com/tasks/java/) página.