---
title: Recuperar excepciones de calendario con Aspose.Tasks
linktitle: Recuperar excepciones de calendario con Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda cómo recuperar excepciones de calendario de MS Project usando Aspose.Tasks para Java. Tutorial paso a paso para una integración perfecta.
type: docs
weight: 13
url: /es/java/calendar-exceptions/retrieve/
---
## Introducción
En este tutorial, exploraremos cómo recuperar excepciones de calendario de MS Project usando la biblioteca Aspose.Tasks para Java. Aspose.Tasks es una poderosa herramienta que permite a los desarrolladores manipular archivos de Microsoft Project mediante programación. Lo guiaremos a través del proceso paso a paso, dividiendo cada ejemplo en varios pasos para una fácil comprensión.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema.
2.  Aspose.Tasks para Java: descargue e instale Aspose.Tasks para Java desde[aquí](https://releases.aspose.com/tasks/java/).
3. Entorno de desarrollo integrado (IDE): puede utilizar cualquier IDE de su elección, como IntelliJ IDEA o Eclipse.

## Importar paquetes
Primero, necesita importar los paquetes necesarios para trabajar con Aspose.Tasks:
```java
import com.aspose.tasks.*;
```
## Paso 1: configure su directorio de datos
```java
// La ruta al directorio de documentos.
String dataDir = "Your Data Directory";
```
 Asegúrese de reemplazar`"Your Data Directory"` con la ruta a su directorio que contiene el archivo de MS Project.
## Paso 2: cargar el archivo de MS Project
```java
Project project = new Project(dataDir + "project.mpp");
```
 Esta línea inicializa una nueva`Project` objeto cargando el archivo de MS Project especificado por la ruta.
## Paso 3: recuperar las excepciones del calendario
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
Aquí, iteramos a través de cada calendario del proyecto y luego a través de cada excepción de calendario dentro de ese calendario. Imprimimos las fechas de inicio y finalización de cada excepción.

## Conclusión
En este tutorial, hemos aprendido cómo recuperar excepciones de calendario de MS Project usando Aspose.Tasks para Java. Si sigue estos sencillos pasos, podrá integrar perfectamente esta funcionalidad en sus aplicaciones Java.
## Preguntas frecuentes
### ¿Puede Aspose.Tasks manejar diferentes versiones de archivos de MS Project?
Sí, Aspose.Tasks admite varias versiones de archivos de MS Project, incluidos los formatos MPP, MPT y XML.
### ¿Hay una prueba gratuita disponible para Aspose.Tasks?
 Sí, puede descargar una prueba gratuita de Aspose.Tasks desde[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar documentación para Aspose.Tasks para Java?
 Puedes consultar la documentación.[aquí](https://reference.aspose.com/tasks/java/).
### ¿Cómo puedo obtener soporte para Aspose.Tasks?
 Puede obtener soporte en el foro de la comunidad.[aquí](https://forum.aspose.com/c/tasks/15).
### ¿Existe una opción para licencias temporales para Aspose.Tasks?
 Sí, puede obtener licencias temporales de[aquí](https://purchase.aspose.com/temporary-license/).