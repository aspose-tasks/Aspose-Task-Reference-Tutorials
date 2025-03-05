---
title: Escriba datos de recursos actualizados en Aspose.Tasks
linktitle: Escriba datos de recursos actualizados en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda cómo actualizar sin esfuerzo datos de recursos en archivos de MS Project usando Aspose.Tasks para Java.
type: docs
weight: 21
url: /es/java/resource-management/write-updated-resource-data/
---
## Introducción
En este tutorial, lo guiaremos a través de la actualización de datos de recursos de Microsoft Project usando Aspose.Tasks para Java. Aspose.Tasks es una potente API de Java que le permite manipular archivos de Microsoft Project sin necesidad de instalar Microsoft Project en su sistema.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Kit de desarrollo de Java (JDK) instalado en su sistema.
2.  Aspose.Tasks para la biblioteca Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/java/).
3. Conocimientos básicos de programación Java.

## Importar paquetes

Primero, necesita importar los paquetes necesarios para trabajar con Aspose.Tasks en su código Java. Agregue las siguientes declaraciones de importación a su archivo Java:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Paso 1: configure su directorio de datos

Defina el directorio donde se encuentran sus archivos de datos:

```java
String dataDir = "Your Data Directory";
```

## Paso 2: especificar archivos de entrada y salida

Defina las rutas para el archivo de MS Project de entrada y el archivo actualizado resultante:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Archivo de prueba con un rsc para actualizar
String resultFile = dataDir + "OutputMPP.mpp"; // Archivo para escribir proyecto de prueba.
```

## Paso 3: cargar el proyecto

 Cargue el archivo de MS Project en un`Project` objeto:

```java
Project project = new Project(file);
```

## Paso 4: agregar un recurso y establecer atributos

Agregue un nuevo recurso al proyecto y establezca sus atributos, como tarifa estándar, tarifa de horas extra y grupo:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Paso 5: guarde el proyecto

Guarde el proyecto actualizado con los datos de recursos modificados:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusión

En este tutorial, hemos demostrado cómo actualizar los datos de recursos de MS Project usando Aspose.Tasks para Java. Si sigue estos pasos, podrá manipular eficientemente la información de recursos en sus archivos de MS Project mediante programación.

## Preguntas frecuentes

### P1: ¿Puedo actualizar varios recursos en el mismo proyecto usando Aspose.Tasks para Java?

R1: Sí, puede actualizar varios recursos recorriéndolos en iteración y configurando sus atributos en consecuencia.

### P2: ¿Aspose.Tasks admite otros formatos de archivo además de MS Project?

R2: Sí, Aspose.Tasks admite varios formatos de archivo, incluidos XML, MPP y más.

### P3: ¿Aspose.Tasks es compatible con diferentes versiones de Java?

R3: Aspose.Tasks es compatible con las versiones 6 y superiores de Java.

### P4: ¿Puedo realizar otras operaciones en archivos de MS Project con Aspose.Tasks?

R4: Sí, puedes realizar una amplia gama de operaciones como leer, escribir y manipular tareas, recursos y calendarios.

### P5: ¿Dónde puedo encontrar ayuda o soporte adicional para Aspose.Tasks?

 A5: Puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para cualquier ayuda o consulta.
