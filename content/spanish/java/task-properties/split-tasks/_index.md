---
title: Dividir tareas en Aspose.Tasks
linktitle: Dividir tareas en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: ¡Domina la gestión de tareas en Java con Aspose.Tasks! Aprenda a dividir tareas de manera eficiente para optimizar los cronogramas del proyecto. ¡Descargar ahora!
type: docs
weight: 29
url: /es/java/task-properties/split-tasks/
---
## Introducción
¿Tiene dificultades con la gestión de tareas en su proyecto Java? Aspose.Tasks para Java proporciona una poderosa solución para dividir tareas de manera eficiente, mejorando las capacidades de gestión de proyectos. En este tutorial, lo guiaremos a través del proceso de dividir tareas usando Aspose.Tasks para Java, ayudándolo a optimizar los cronogramas de su proyecto y la asignación de recursos.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Kit de desarrollo de Java (JDK) instalado en su máquina.
-  Biblioteca Aspose.Tasks para Java descargada y agregada a su proyecto. Puedes descargarlo desde el[Aspose.Tasks para la documentación de Java](https://reference.aspose.com/tasks/java/).
## Importar paquetes
Comience importando los paquetes necesarios a su proyecto Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```
## Paso 1: crear un nuevo proyecto
Comience creando un nuevo proyecto usando la biblioteca Aspose.Tasks:
```java
// Crear un nuevo proyecto
Project splitTaskProject = new Project();
```
## Paso 2: configurar el calendario del proyecto
Establezca la configuración del calendario del proyecto para establecer el cronograma:
```java
// Obtenga un calendario estándar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Establecer la configuración del calendario del proyecto
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (sigue con el ejemplo)
```
## Paso 3: agregar una tarea raíz
Agregue una tarea raíz a su proyecto:
```java
// Tarea raíz
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Paso 4: agregue una nueva tarea para dividir
Agregue una nueva tarea a su proyecto que desee dividir:
```java
// Agregar una nueva tarea
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Paso 5: crear una asignación de recursos
Cree una nueva asignación de recursos para la tarea:
```java
// Crear una nueva asignación de recursos
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Paso 6: generar datos en fases temporales
Generar datos de fase temporal de asignación de recursos:
```java
// Generar datos de fase temporal de asignación de recursos
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Paso 7: dividir la tarea
Divida la tarea en varias partes:
```java
// Dividir la tarea en 3 partes.
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (sigue con el ejemplo)
```
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo dividir tareas usando Aspose.Tasks para Java. Esta potente biblioteca simplifica la gestión de tareas en proyectos Java y proporciona soluciones eficientes para optimizar los cronogramas de los proyectos y la asignación de recursos.
## Preguntas frecuentes
### ¿Puedo dividir tareas con diferentes duraciones?
Sí, puede ajustar la duración de las tareas según los requisitos de su proyecto.
### ¿Aspose.Tasks para Java es compatible con todas las versiones de Java?
Aspose.Tasks para Java está diseñado para funcionar perfectamente con varias versiones de Java, lo que garantiza la compatibilidad.
### ¿Puedo utilizar Aspose.Tasks para Java de forma gratuita?
Aspose.Tasks para Java ofrece una prueba gratuita que le permite explorar sus funciones antes de realizar una compra.
### ¿Cómo puedo obtener soporte para Aspose.Tasks para Java?
 Visita el[Foro de soporte de Aspose.Tasks para Java](https://forum.aspose.com/c/tasks/15) para obtener asistencia y conectarse con la comunidad.
### ¿Necesito una licencia temporal para Aspose.Tasks para Java?
 Puede obtener una licencia temporal de[este enlace](https://purchase.aspose.com/temporary-license/) para fines de prueba y evaluación.