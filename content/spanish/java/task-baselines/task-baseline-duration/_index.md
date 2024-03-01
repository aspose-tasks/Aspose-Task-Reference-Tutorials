---
title: Gestión de la duración de la línea base de tareas en Aspose.Tasks
linktitle: Gestión de la duración de la línea base de tareas en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a administrar de manera eficiente las líneas base de tareas en MS Project usando Aspose.Tasks para Java. Este tutorial lo guía paso a paso a través del proceso.
type: docs
weight: 12
url: /es/java/task-baselines/task-baseline-duration/
---
## Introducción
La gestión de líneas base de tareas en MS Project es crucial para la planificación y el seguimiento de proyectos. En este tutorial, exploraremos cómo administrar eficazmente la duración de la línea base de las tareas usando Aspose.Tasks para Java.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Entorno de desarrollo de Java: asegúrese de tener el kit de desarrollo de Java (JDK) instalado en su sistema.
2.  Biblioteca Aspose.Tasks: descargue e instale la biblioteca Aspose.Tasks para Java desde[aquí](https://releases.aspose.com/tasks/java/).

## Importar paquetes
Primero, importe los paquetes necesarios para su proyecto Java:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## Paso 1: crear una instancia de proyecto
Inicialice una nueva instancia de proyecto utilizando el siguiente código:
```java
Project project = new Project();
```
## Paso 2: crear una línea base de tareas
Cree una nueva tarea y establezca su línea base usando el siguiente código:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## Paso 3: Mostrar información de referencia de la tarea
Recupere y muestre información de referencia de la tarea, como la duración, la fecha de inicio, la fecha de finalización y más:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## Paso 4: verificar la línea base provisional y el costo fijo
Verifique si la línea base es una línea base provisional y recupere los costos fijos asociados con ella:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## Paso 5: Imprimir datos en fases temporales
Imprima datos de fases temporales asociados con la línea base de la tarea:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
Si sigue estos pasos, puede administrar eficazmente la duración de la línea base de las tareas en MS Project utilizando Aspose.Tasks para Java.

## Conclusión
Gestionar las líneas base de tareas es esencial para la gestión de proyectos, ya que le permite realizar un seguimiento de las desviaciones del cronograma planificado. Con Aspose.Tasks para Java, este proceso se simplifica y es eficiente, lo que permite un mejor control y entrega del proyecto.
## Preguntas frecuentes
### ¿Qué es una línea base de tareas en MS Project?
Una línea base de tarea en MS Project es una instantánea del cronograma planificado inicial para una tarea, incluida su fecha de inicio, fecha de finalización y duración.
### ¿Por qué es importante gestionar las líneas base de tareas?
La gestión de líneas de base de tareas ayuda a comparar el cronograma planificado con el progreso real del proyecto, lo que facilita un mejor seguimiento y toma de decisiones.
### ¿Puedo modificar la línea base de una tarea una vez establecida?
Sí, puede modificar las líneas base de tareas en MS Project para reflejar los cambios en el plan del proyecto. Sin embargo, es esencial documentar cualquier desviación de la línea de base original.
### ¿Aspose.Tasks admite otras funcionalidades de gestión de proyectos?
Sí, Aspose.Tasks ofrece una amplia gama de funciones para la gestión de proyectos, incluida la programación de tareas, la asignación de recursos y la generación de diagramas de Gantt.
### ¿Dónde puedo encontrar soporte para Aspose.Tasks?
 Puede encontrar soporte para Aspose.Tasks en el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15), donde podrás hacer preguntas e interactuar con otros usuarios.