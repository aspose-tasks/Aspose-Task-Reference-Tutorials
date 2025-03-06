---
title: Dividir la fecha de finalización de la tarea en Aspose.Tasks
linktitle: Dividir la fecha de finalización de la tarea en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a dividir las fechas de finalización de las tareas sin esfuerzo utilizando Aspose.Tasks para Java. Mejore la gestión de proyectos con cronogramas precisos.
type: docs
weight: 28
url: /es/java/task-properties/split-task-finish-date/
---
## Introducción
En la gestión de proyectos, comprender los cronogramas de las tareas es crucial para completar exitosamente el proyecto. Aspose.Tasks para Java proporciona potentes funciones para manipular las tareas del proyecto de manera eficiente. En este tutorial, profundizaremos en cómo dividir las fechas de finalización de las tareas utilizando Aspose.Tasks, lo que le ayudará a gestionar los cronogramas del proyecto de forma eficaz.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
- Conocimientos básicos de programación Java.
-  Aspose.Tasks para la biblioteca Java instalada. Puedes descargarlo[aquí](https://releases.aspose.com/tasks/java/).
- Un entorno de desarrollo Java configurado.
## Importar paquetes
Comience por incluir los paquetes necesarios en su proyecto Java:
```java
import com.aspose.tasks.*;
```
## Paso 1: busque una tarea dividida
Localice la tarea que desea dividir dentro del proyecto:
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Leer proyecto
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Paso 2: busque el calendario del proyecto
Recupere el calendario del proyecto para realizar cálculos de fechas precisos:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Paso 3: Calcule la fecha de finalización de la tarea con diferentes duraciones
Ahora, calcule la fecha de finalización de la tarea para varias duraciones:
## Paso 3.1: Duración de 8 Horas
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Repita el código anterior durante diferentes duraciones, ajustando las horas en consecuencia.
## Conclusión
Dominar el arte de manipular las fechas de finalización de las tareas es fundamental para una gestión eficaz de los proyectos. Aspose.Tasks para Java simplifica este proceso, permitiéndole optimizar los cronogramas de su proyecto sin esfuerzo.
## Preguntas frecuentes
### P1: ¿Cómo puedo descargar Aspose.Tasks para Java?
 A1: puedes descargarlo[aquí](https://releases.aspose.com/tasks/java/).
### P2: ¿Dónde puedo encontrar documentación para Aspose.Tasks?
 A2: consulte la documentación[aquí](https://reference.aspose.com/tasks/java/).
### P3: ¿Cómo obtengo una licencia temporal para Aspose.Tasks?
 A3: Obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### P4: ¿Dónde puedo buscar soporte para Aspose.Tasks?
 A4: Visita el foro de soporte[aquí](https://forum.aspose.com/c/tasks/15).
### P5: ¿Puedo comprar Aspose.Tasks?
 A5: Sí, puedes comprarlo[aquí](https://purchase.aspose.com/buy).