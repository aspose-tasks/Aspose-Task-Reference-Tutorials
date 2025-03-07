---
title: Manejar las propiedades de retardo de nivelación en Aspose.Tasks
linktitle: Manejar propiedades de retardo de nivelación para asignaciones de recursos en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a manejar las propiedades de retardo de nivelación para asignaciones de recursos en Aspose.Tasks para Java con este completo tutorial.
weight: 17
url: /es/java/resource-assignments/leveling-delay-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manejar las propiedades de retardo de nivelación en Aspose.Tasks

## Introducción
En este tutorial, recorreremos el proceso de manejo de propiedades de retardo de nivelación para asignaciones de recursos en Aspose.Tasks para Java. Aspose.Tasks es una poderosa biblioteca de Java que le permite trabajar con archivos de Microsoft Project sin necesidad de instalar Microsoft Project en su sistema.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1.  Kit de desarrollo de Java (JDK): asegúrese de tener Java JDK instalado en su sistema. Puedes descargarlo e instalarlo desde[sitio web](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Biblioteca Aspose.Tasks para Java: descargue la biblioteca Aspose.Tasks para Java desde[pagina de descarga](https://releases.aspose.com/tasks/java/).

## Importar paquetes
Primero, importe los paquetes necesarios a su proyecto Java para utilizar las funcionalidades de Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Paso 1: crear un objeto de proyecto
 Crear una instancia de`Project` objeto:
```java
Project prj = new Project();
```
## Paso 2: crear una tarea
Agregue una tarea al proyecto:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Paso 3: establecer la fecha de inicio y la duración de la tarea
Establezca la fecha de inicio y la duración de la tarea:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Paso 4: agregue un recurso
Agregue un recurso al proyecto:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Paso 5: crear una asignación de recursos
Cree una asignación de recursos para la tarea y el recurso:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Paso 6: Establecer el retraso de nivelación
Establezca el retraso de nivelación para la tarea:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Paso 7: Mostrar resultados
Imprima el retraso de nivelación y otra información relevante:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Conclusión
En este tutorial, aprendimos cómo manejar las propiedades de retardo de nivelación para asignaciones de recursos en Aspose.Tasks para Java. Si sigue estos pasos, podrá gestionar eficientemente las asignaciones de recursos en sus proyectos Java.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks con otras bibliotecas de Java?

R: Sí, Aspose.Tasks se puede integrar con otras bibliotecas de Java para mejorar las capacidades de gestión de proyectos.

### P: ¿Aspose.Tasks es compatible con diferentes versiones de archivos de Microsoft Project?

R: Sí, Aspose.Tasks admite varias versiones de archivos de Microsoft Project, lo que garantiza la compatibilidad entre diferentes entornos.

### P: ¿Dónde puedo encontrar soporte adicional para Aspose.Tasks?

 R: Puede encontrar soporte y recursos en el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P: ¿Puedo probar Aspose.Tasks antes de comprarlo?

 R: Sí, puede obtener una prueba gratuita de Aspose.Tasks desde[página de lanzamientos](https://releases.aspose.com/).

### P: ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks?

 R: Puede solicitar una licencia temporal al[página de licencia temporal](https://purchase.aspose.com/temporary-license/) para fines de evaluación.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
