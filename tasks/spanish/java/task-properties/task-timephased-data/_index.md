---
title: Datos de fases temporales de tareas en Aspose.Tasks
linktitle: Datos de fases temporales de tareas en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Explore Aspose.Tasks para Java y domine la gestión de datos en fases temporales de tareas. Descargue la biblioteca, disfrute de una prueba gratuita y optimice el seguimiento de su proyecto.
weight: 34
url: /es/java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Datos de fases temporales de tareas en Aspose.Tasks

## Introducción
En el ámbito de la gestión de proyectos, el seguimiento preciso de los datos de las fases temporales de las tareas es crucial para una ejecución eficiente del proyecto. Aspose.Tasks para Java surge como una poderosa herramienta para agilizar este proceso, ofreciendo características sólidas y flexibilidad. Este tutorial lo guiará a través del uso de Aspose.Tasks para Java para administrar los datos de las tareas en fases temporales de manera efectiva.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Entorno de desarrollo de Java: asegúrese de tener Java instalado en su sistema.
-  Biblioteca Aspose.Tasks para Java: descargue e incluya la biblioteca Aspose.Tasks en su proyecto. Puedes encontrar la biblioteca.[aquí](https://releases.aspose.com/tasks/java/).
- Directorio de documentos: configure un directorio para los documentos de su proyecto.
## Importar paquetes
En su proyecto Java, importe los paquetes necesarios para Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## Paso 1: establecer la fecha de inicio del proyecto
```java
Project project = new Project(dataDir + "project.xml");
// Código adicional para importaciones de paquetes.
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Explicación: Inicialice un objeto de calendario, establezca la fecha de inicio y aplíquelo al proyecto.
## Paso 2: definir tarea y recurso
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Explicación: Cree una tarea y un recurso, estableciendo tarifas para horas estándar y extra.
## Paso 3: establecer la duración de la tarea
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Explicación: Defina la duración de la tarea (por ejemplo, 6 días).
## Paso 4: asignar recurso a la tarea
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Explicación: Asigne el recurso a la tarea.
## Paso 5: configurar la asignación de recursos
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Explicación: Establezca parámetros como detener, reanudar y contorno de trabajo para la asignación de recursos.
## Paso 6: establecer la línea de base
```java
project.setBaseline(BaselineType.Baseline);
```
Explicación: Establecer una línea base para el proyecto.
## Paso 7: Actualizar la finalización de la tarea
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Explicación: Indique el porcentaje de finalización de la tarea.
## Paso 8: recuperar datos en fases temporales
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Explicación: Recuperar datos de fases temporales para el trabajo restante de la asignación.
## Paso 9: Mostrar datos en fases temporales
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Código adicional para mostrar otros valores
```
Explicación: Genera y muestra los datos de fases temporales.
## Conclusión
La gestión eficaz de los datos de las fases temporales de las tareas es indispensable para el éxito del proyecto. Aspose.Tasks para Java simplifica este proceso y proporciona un conjunto completo de funcionalidades. Si sigue este tutorial, podrá integrar Aspose.Tasks sin problemas en su proyecto Java, asegurando un control preciso sobre los cronogramas del proyecto y la asignación de recursos.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks para Java en cualquier proyecto Java?
R: Sí, Aspose.Tasks para Java es compatible con cualquier proyecto basado en Java.
### P: ¿Dónde puedo encontrar soporte adicional para Aspose.Tasks para Java?
 R: Visita el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoyo y discusiones.
### P: ¿Hay una prueba gratuita disponible para Aspose.Tasks para Java?
 R: Sí, puedes explorar una prueba gratuita[aquí](https://releases.aspose.com/).
### P: ¿Cómo puedo obtener una licencia temporal de Aspose.Tasks para Java?
 R: Puedes adquirir una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### P: ¿Dónde puedo comprar Aspose.Tasks para Java?
 R: Puedes comprar Aspose.Tasks para Java[aquí](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
