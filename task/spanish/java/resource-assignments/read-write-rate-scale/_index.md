---
title: Escala de tasa de lectura y escritura para asignaciones de recursos en Aspose.Tasks
linktitle: Escala de tasa de lectura y escritura para asignaciones de recursos en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda cómo administrar la escala de tasas de asignaciones de recursos de manera efectiva en Aspose.Tasks para Java con este completo tutorial.
type: docs
weight: 20
url: /es/java/resource-assignments/read-write-rate-scale/
---
## Introducción
En este tutorial, profundizaremos en la gestión de la escala de tasa de asignaciones de recursos utilizando Aspose.Tasks para Java, una biblioteca sólida para trabajar con archivos de Microsoft Project mediante programación. Si sigue estos pasos, podrá manipular eficazmente la configuración de escala de tarifas para las asignaciones de recursos en sus aplicaciones Java.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Entorno de desarrollo de Java: asegúrese de tener el kit de desarrollo de Java (JDK) instalado en su sistema.
2.  Biblioteca Aspose.Tasks para Java: descargue e instale la biblioteca Aspose.Tasks para Java desde[aquí](https://releases.aspose.com/tasks/java/).

## Importar paquetes
Primero, debe importar los paquetes necesarios para trabajar con las funcionalidades de Aspose.Tasks. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## Paso 1: configura tu proyecto
Comience configurando su proyecto Java e incluya la biblioteca Aspose.Tasks en sus dependencias.
## Paso 2: cargue el archivo del proyecto
Cargue el archivo de proyecto con el que desea trabajar en su aplicación Java.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Paso 3: agregar una tarea
Añade una nueva tarea a tu proyecto.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Paso 4: definir recursos
Definir recursos materiales y no materiales y especificar sus tipos.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Paso 5: asignar recursos a la tarea
Asigne los recursos previamente definidos a la tarea junto con sus tipos de escala de tarifas.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Paso 6: guarde el proyecto
Guarde el proyecto con las asignaciones de recursos modificadas.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Paso 7: recuperar asignaciones de recursos
Vuelva a cargar el proyecto guardado y recupere las asignaciones de recursos para verificar la configuración de la escala de tarifas.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Conclusión
Administrar la escala de tasa de asignaciones de recursos en Aspose.Tasks para Java es crucial para una gestión eficaz de proyectos. Si sigue esta guía paso a paso, podrá manipular sin problemas la configuración de la escala de tarifas para las asignaciones de recursos en sus aplicaciones Java.
## Preguntas frecuentes
### P1: ¿Puedo usar Aspose.Tasks para Java con cualquier IDE de Java?
R: Sí, Aspose.Tasks para Java es compatible con todos los principales IDE de Java, incluidos IntelliJ IDEA, Eclipse y NetBeans.
### P2: ¿Aspose.Tasks admite otros formatos de archivo además de MPP?
R: Sí, Aspose.Tasks admite varios formatos de archivo, incluidos MPP, XML y HTML.
### P3: ¿Aspose.Tasks es adecuado para la gestión de proyectos a nivel empresarial?
R: Por supuesto, Aspose.Tasks ofrece funciones integrales para gestionar proyectos de cualquier escala, lo que lo hace adecuado para la gestión de proyectos a nivel empresarial.
### P4: ¿Puedo personalizar las asignaciones de recursos más allá de la escala de tarifas?
R: Sí, Aspose.Tasks proporciona amplias capacidades para personalizar las asignaciones de recursos, incluidos ajustes de costo, trabajo y duración.
### P5: ¿Existe un foro comunitario para soporte de Aspose.Tasks?
 R: Sí, puedes encontrar soporte e interactuar con otros usuarios en el foro Aspose.Tasks.[aquí](https://forum.aspose.com/c/tasks/15).