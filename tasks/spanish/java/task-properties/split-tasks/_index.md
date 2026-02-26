---
date: 2026-02-26
description: 'Aprenda cómo dividir tareas con Aspose.Tasks para Java: la guía definitiva
  sobre cómo dividir tareas, establecer el calendario del proyecto y crear asignaciones
  de recursos.'
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo dividir tareas en Aspose.Tasks
url: /es/java/task-properties/split-tasks/
weight: 29
---

?"

Link text translate.

Then the bottom metadata lines: "Last Updated:" "Tested With:" "Author:" translate.

Now produce final content.

Make sure to keep code block placeholders exactly as they are.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo dividir tareas en Aspose.Tasks

## Introducción
Si estás buscando **cómo dividir tareas** en un proyecto basado en Java, has llegado al lugar correcto. Aspose.Tasks for Java te brinda una forma limpia y programática de dividir una tarea de larga duración en partes más pequeñas y manejables, lo que ayuda con el nivelado de recursos, informes precisos y cronogramas de proyecto más ajustados. En este tutorial recorreremos todo el proceso, desde la configuración del calendario del proyecto hasta la creación de una asignación de recurso y, finalmente, la división de la tarea en varios segmentos.

## Respuestas rápidas
- **¿Qué es la división de tareas?** Dividir una única tarea en varios intervalos más pequeños mientras se conserva su duración total.  
- **¿Por qué dividir tareas en Java?** Permite una asignación de recursos precisa y un mejor seguimiento del progreso.  
- **¿Qué biblioteca ayuda?** Aspose.Tasks for Java proporciona métodos integrados para dividir y crear fases temporales.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia para producción.  
- **¿Qué versión de Java es compatible?** La biblioteca funciona con Java 8 y versiones posteriores.

## Requisitos previos
Antes de sumergirte en el tutorial, asegúrate de contar con los siguientes requisitos:
- Java Development Kit (JDK) instalado en tu máquina.  
- Biblioteca Aspose.Tasks for Java descargada y añadida a tu proyecto. Puedes descargarla de la [documentación de Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/).

## Importar paquetes
Comienza importando los paquetes necesarios en tu proyecto Java:

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

## Paso 1: Crear un nuevo proyecto
Crea un nuevo proyecto usando la biblioteca Aspose.Tasks:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Paso 2: Configurar el calendario del proyecto
Establecer el **calendario del proyecto** define los días laborables, festivos y la línea de tiempo general de tu planificación. Este paso es esencial para cálculos de fases temporales precisos.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Paso 3: Añadir una tarea raíz
Todo proyecto necesita un contenedor raíz. Añadir una tarea raíz te brinda un lugar donde adjuntar todas las tareas posteriores.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Paso 4: Añadir una nueva tarea para dividir
Crea la tarea que deseas dividir. Aquí establecemos una duración de tres días como ejemplo.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Paso 5: Crear una asignación de recurso
Una **asignación de recurso** vincula un recurso (o un marcador de posición) a la tarea. Esto es necesario antes de generar datos de fases temporales.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Paso 6: Generar datos de fases temporales
Los datos de fases temporales representan cómo se distribuye el trabajo a lo largo de la duración de la tarea. Generarlos prepara la tarea para ser dividida.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Paso 7: Dividir la tarea
Ahora **dividimos la tarea en partes**. En este ejemplo dividimos la tarea de tres días en tres segmentos de un día cada uno.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## ¿Por qué dividir tareas?
Dividir tareas te brinda un control más granular sobre:
- **Nivelado de recursos:** Asigna diferentes recursos a cada segmento.  
- **Seguimiento del progreso:** Actualiza el estado por segmento.  
- **Informes:** Genera diagramas de Gantt y reportes más detallados.

## Problemas comunes y soluciones
- **Datos de calendario faltantes:** Asegúrate de llamar a `timephasedDataFromTaskDuration` antes de dividir.  
- **Segmentos de duración cero:** Verifica que cada intervalo dividido tenga una duración distinta de cero; de lo contrario, la biblioteca lo ignorará.  
- **Excepciones de licencia:** Ejecutar sin una licencia válida puede añadir una marca de agua a los archivos exportados.

## Preguntas frecuentes
### ¿Puedo dividir tareas con diferentes duraciones?
Sí, puedes ajustar la duración de cada parte para que coincida con los requisitos de tu proyecto.

### ¿Es Aspose.Tasks for Java compatible con todas las versiones de Java?
Aspose.Tasks for Java está diseñado para funcionar sin problemas con Java 8 y versiones posteriores, garantizando una amplia compatibilidad.

### ¿Puedo usar Aspose.Tasks for Java de forma gratuita?
Aspose.Tasks for Java ofrece una prueba gratuita, que te permite explorar sus funciones antes de realizar una compra.

### ¿Cómo puedo obtener soporte para Aspose.Tasks for Java?
Visita el [foro de soporte de Aspose.Tasks for Java](https://forum.aspose.com/c/tasks/15) para obtener asistencia y conectar con la comunidad.

### ¿Necesito una licencia temporal para Aspose.Tasks for Java?
Puedes obtener una licencia temporal desde [este enlace](https://purchase.aspose.com/temporary-license/) para propósitos de prueba y evaluación.

---

**Última actualización:** 2026-02-26  
**Probado con:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}