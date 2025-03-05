---
title: Detener y reanudar asignaciones de recursos en Aspose.Tasks
linktitle: Detener y reanudar asignaciones de recursos en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda cómo gestionar las asignaciones de recursos de forma eficaz en Aspose.Tasks para Java con este tutorial paso a paso.
type: docs
weight: 23
url: /es/java/resource-assignments/stop-resume-assignment/
---
## Introducción
En este tutorial, aprenderemos cómo detener y reanudar asignaciones de recursos usando Aspose.Tasks para Java. Aspose.Tasks es una potente API de Java que permite a los desarrolladores trabajar con archivos de Microsoft Project sin necesidad de que Microsoft Project esté instalado en sus sistemas. Dividiremos el proceso en pasos manejables para que sea fácil de seguir.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Kit de desarrollo de Java (JDK) instalado en su sistema.
-  Descarga la biblioteca Aspose.Tasks para Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/java/).
- Conocimientos básicos de programación Java.
## Importar paquetes
Primero, importemos los paquetes necesarios a nuestro proyecto Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Paso 1: cargue el archivo del proyecto
```java
// La ruta al directorio de documentos.
String dataDir = "Your Data Directory";
// Cargar el archivo del proyecto
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 En este paso, cargamos el archivo del proyecto en un`Project` objeto utilizando la ruta del archivo.
## Paso 2: iterar a través de las asignaciones de recursos
```java
// Definir fecha mínima
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterar a través de asignaciones de recursos
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Aquí, definimos una fecha mínima y comenzamos a iterar a través de cada asignación de recursos en el proyecto.
## Paso 3: Verifique las fechas de finalización y reanudación
```java
    // Verificar fecha de parada
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Verificar fecha de currículum
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
En este paso, verificamos si las fechas de finalización y reanudación de cada asignación de recursos son anteriores a la fecha mínima. Si lo son, imprimimos "NA", en caso contrario, imprimimos las fechas respectivas.
## Conclusión
En este tutorial, aprendimos cómo detener y reanudar asignaciones de recursos en Aspose.Tasks para Java. Si sigue los pasos proporcionados, podrá implementar fácilmente esta funcionalidad en sus proyectos Java.

## Preguntas frecuentes
### ¿Puedo usar Aspose.Tasks sin Microsoft Project instalado?
Sí, Aspose.Tasks le permite trabajar con archivos de Microsoft Project sin necesidad de tener Microsoft Project instalado en su sistema.
### ¿Dónde puedo encontrar más documentación?
 Puedes encontrar documentación detallada.[aquí](https://reference.aspose.com/tasks/java/).
### ¿Hay una prueba gratuita disponible?
 Sí, puedes obtener una prueba gratuita.[aquí](https://releases.aspose.com/).
### ¿Cómo puedo obtener soporte si tengo algún problema?
Puedes obtener apoyo de la comunidad.[aquí](https://forum.aspose.com/c/tasks/15).
### ¿Puedo comprar una licencia temporal?
 Sí, puedes comprar una licencia temporal.[aquí](https://purchase.aspose.com/temporary-license/).