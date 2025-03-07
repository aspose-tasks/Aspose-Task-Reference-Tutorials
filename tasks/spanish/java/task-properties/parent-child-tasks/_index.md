---
title: Administrar tareas principales y secundarias en Aspose.Tasks
linktitle: Administrar tareas principales y secundarias en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Mejore la eficiencia de la gestión de proyectos con Aspose.Tasks para Java. Aprenda a gestionar las tareas de padres e hijos paso a paso. ¡Empieza ahora!
weight: 24
url: /es/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Administrar tareas principales y secundarias en Aspose.Tasks

## Introducción
En el ámbito de la gestión de proyectos, la organización eficaz de las tareas es crucial. Aspose.Tasks para Java proporciona una solución sólida para administrar las tareas principales y secundarias de manera eficiente. En este tutorial, lo guiaremos a través del proceso de uso de Aspose.Tasks para Java para optimizar las tareas de su proyecto.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Conocimientos básicos de programación Java.
-  Aspose.Tasks para la biblioteca Java instalada. Puedes descargarlo[aquí](https://releases.aspose.com/tasks/java/).
- Un entorno de desarrollo integrado (IDE) de Java configurado en su sistema.
## Importar paquetes
Para comenzar, importe los paquetes necesarios a su proyecto Java. Estos paquetes facilitan una integración perfecta con las funcionalidades de Aspose.Tasks para Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## Paso 1: establecer la fecha de inicio del proyecto
Comience estableciendo la fecha de inicio del proyecto y otros parámetros relevantes.
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Se puede agregar código adicional para importaciones de paquetes aquí
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Paso 2: Agregar tarea principal (tarea 1)
Cree una tarea principal denominada "Tarea 1" y configure sus propiedades.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Paso 3: Agregar tarea principal (tarea 2) con tareas secundarias
Ahora, agregue otra tarea principal llamada "Tarea 2" e incluya tareas secundarias (Tarea 3 y Tarea 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Agregar tareas secundarias a la Tarea 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Se puede agregar configuración adicional para la Tarea 3 y la Tarea 4 aquí
```
## Paso 4: configurar tareas secundarias
Especifique fechas de inicio, duraciones y restricciones para la Tarea 3 y la Tarea 4.
```java
// Configurar la tarea 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configurar la tarea 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Paso 5: actualizar el porcentaje de finalización de tareas
Ajuste el porcentaje de finalización para la Tarea 3 y la Tarea 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Paso 6: guarde el proyecto
Finalmente, guarde el proyecto con los cambios aplicados.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Esta guía paso a paso demuestra cómo gestionar las tareas principales y secundarias de forma eficaz utilizando Aspose.Tasks para Java. Experimente con diferentes configuraciones para adaptarse a los requisitos de su proyecto.
## Conclusión
En conclusión, Aspose.Tasks para Java permite a los desarrolladores manejar de manera eficiente las tareas del proyecto, garantizando una organización y un seguimiento perfectos. Implemente los pasos descritos para mejorar sus capacidades de gestión de proyectos.
## Preguntas frecuentes
### ¿Aspose.Tasks para Java es compatible con diferentes formatos de archivos de proyectos?
Sí, Aspose.Tasks para Java admite varios formatos de archivos de proyecto, incluidos MPP y XML.
### ¿Puedo personalizar las propiedades de las tareas más allá de lo que se cubre en este tutorial?
¡Absolutamente! Aspose.Tasks para Java proporciona amplias opciones de personalización para las propiedades de las tareas.
### ¿Existe un foro comunitario para Aspose.Tasks donde pueda buscar ayuda?
 Sí, puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para el apoyo de la comunidad.
### ¿Cómo puedo obtener una licencia temporal de Aspose.Tasks para Java?
 Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo encontrar documentación completa para Aspose.Tasks para Java?
 La documentación está disponible.[aquí](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
