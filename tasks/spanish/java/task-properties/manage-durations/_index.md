---
title: Administrar la duración de las tareas en Aspose.Tasks
linktitle: Administrar la duración de las tareas en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Explore Aspose.Tasks para Java y aprenda a administrar la duración de las tareas sin esfuerzo. Siga nuestra guía paso a paso para una planificación y ejecución efectiva de proyectos.
weight: 20
url: /es/java/task-properties/manage-durations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Administrar la duración de las tareas en Aspose.Tasks

## Introducción
Aspose.Tasks para Java proporciona una solución sólida para gestionar las tareas y la duración de los proyectos de manera eficiente. En este tutorial, exploraremos cómo administrar la duración de las tareas usando Aspose.Tasks, guiándolo en cada paso. Ya sea que sea un desarrollador experimentado o un principiante, esta guía lo ayudará a comprender los conceptos básicos para trabajar con la duración de las tareas en sus proyectos.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
-  Kit de desarrollo de Java (JDK): asegúrese de tener Java instalado en su máquina. Puedes descargarlo[aquí](https://www.oracle.com/java/technologies/javase-downloads.html).
- Biblioteca Aspose.Tasks: descargue e incluya la biblioteca Aspose.Tasks en su proyecto. Puedes encontrar la biblioteca.[aquí](https://releases.aspose.com/tasks/java/).
## Importar paquetes
En su proyecto Java, importe los paquetes necesarios para trabajar con Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Paso 1: configura tu proyecto
```java
// Crear un nuevo proyecto
Project project = new Project();
```
## Paso 2: agregar una nueva tarea
```java
// Agregar una nueva tarea al proyecto
Task task = project.getRootTask().getChildren().add("Task");
```
## Paso 3: Obtener y convertir la duración de la tarea
```java
// Obtener la duración de la tarea en días (unidad de tiempo predeterminada)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convertir duración a unidad de tiempo de horas
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Paso 4: actualice la duración de la tarea a 1 semana
```java
// Aumentar la duración de la tarea a 1 semana.
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Paso 5: Disminuir la duración de la tarea
```java
// Disminuir la duración de la tarea
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Si sigue estos pasos, habrá administrado con éxito la duración de las tareas en su proyecto Aspose.Tasks para Java.
## Conclusión
En este tutorial, cubrimos los conceptos básicos de la gestión de la duración de las tareas utilizando Aspose.Tasks para Java. Ahora puede incorporar con confianza estas técnicas en sus proyectos para una gestión eficaz de la duración de las tareas.
## Preguntas frecuentes
### ¿Aspose.Tasks es compatible con todas las versiones de Java?
Aspose.Tasks es compatible con Java 6 y versiones posteriores.
### ¿Puedo utilizar Aspose.Tasks para proyectos comerciales?
 Sí, puedes utilizar Aspose.Tasks tanto para proyectos personales como comerciales. Visita[aquí](https://purchase.aspose.com/buy) para obtener detalles sobre la licencia.
### ¿Dónde puedo encontrar apoyo y recursos adicionales?
 Visita el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoyo y debates de la comunidad.
### ¿Cómo puedo obtener una licencia temporal para realizar pruebas?
 Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/) para pruebas y evaluación.
### ¿Hay una prueba gratuita disponible para Aspose.Tasks?
 Sí, puedes acceder a la prueba gratuita.[aquí](https://releases.aspose.com/) para explorar Aspose.Tasks antes de realizar una compra.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
