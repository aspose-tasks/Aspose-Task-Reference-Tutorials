---
title: Generar datos en fases temporales en Aspose.Tasks
linktitle: Genere datos en fases temporales para asignaciones de recursos en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a generar datos en fases temporales para asignaciones de recursos utilizando Aspose.Tasks para Java. Mejore la eficiencia de la gestión de proyectos con esta guía completa.
weight: 24
url: /es/java/resource-assignments/timephased-data-generation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar datos en fases temporales en Aspose.Tasks

## Introducción
En este tutorial, recorreremos el proceso de generación de datos en fases temporales para asignaciones de recursos utilizando Aspose.Tasks para Java. Los datos en fases temporales brindan información valiosa sobre cómo se asignan los recursos a lo largo del tiempo dentro de un proyecto, lo que ayuda a los gerentes de proyectos a tomar decisiones informadas.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1.  Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema. Puede descargar e instalar JDK desde[aquí](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Biblioteca Aspose.Tasks para Java: debe tener la biblioteca Aspose.Tasks para Java. Puedes descargarlo desde el[sitio web](https://releases.aspose.com/tasks/java/).

## Importar paquetes
Primero, importemos los paquetes necesarios para trabajar con Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Paso 1: leer el archivo MPP de origen
```java
// La ruta al directorio de documentos.
String dataDir = "Your Data Directory";
// Leer el archivo MPP fuente
Project project = new Project(dataDir + "project.mpp");
```
## Paso 2: Obtener la asignación de tareas y recursos
```java
// Consigue la primera tarea del Proyecto.
Task task = project.getRootTask().getChildren().getById(1);
// Obtener la primera asignación de recursos del proyecto.
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Paso 3: generar datos en fases temporales con contorno plano
```java
// El contorno plano es el contorno predeterminado
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Paso 4: cambie el contorno a tortuga
```java
// Cambiar contorno a Tortuga
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Paso 5: cambie el contorno a BackLoaded
```java
// Cambiar contorno a BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Paso 6: cambie el contorno a FrontLoaded
```java
// Cambiar contorno a FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Paso 7: cambie el contorno a campana
```java
// Cambiar contorno a Campana
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Paso 8: cambie el contorno a EarlyPeak
```java
// Cambiar contorno a EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Paso 9: cambie Contour a LatePeak
```java
// Cambiar contorno a LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Paso 10: cambie el contorno a DoublePeak
```java
// Cambiar contorno a DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Conclusión
En este tutorial, cubrimos cómo generar datos en fases temporales para asignaciones de recursos usando Aspose.Tasks para Java. Comprender diferentes contornos de trabajo puede ayudar a los gerentes de proyectos a gestionar eficazmente la asignación y programación de recursos en sus proyectos.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Tasks con otras bibliotecas de Java?
Sí, Aspose.Tasks se puede integrar con otras bibliotecas de Java para mejorar las capacidades de gestión de proyectos.
### ¿Aspose.Tasks es adecuado para proyectos empresariales a gran escala?
Por supuesto, Aspose.Tasks está diseñado para manejar proyectos de todos los tamaños, incluidos proyectos empresariales a gran escala.
### ¿Aspose.Tasks brinda soporte para diferentes formatos de archivos de proyecto?
Sí, Aspose.Tasks admite varios formatos de archivos de proyecto, incluidos MPP, XML y MPX.
### ¿Puedo personalizar los contornos de trabajo según los requisitos de mi proyecto?
Sí, Aspose.Tasks permite a los usuarios definir contornos de trabajo personalizados para satisfacer las necesidades específicas de su proyecto.
### ¿Existe un foro comunitario donde pueda obtener ayuda con Aspose.Tasks?
 Sí, puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoyo y discusiones.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
