---
title: Supervise las horas extras, los costos restantes y el trabajo en Aspose.Tasks
linktitle: Supervise las horas extras, los costos restantes y el trabajo en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a monitorear las horas extra, los costos restantes y trabajar en proyectos Java usando Aspose.Tasks. Pasos sencillos para una gestión eficaz de proyectos.
type: docs
weight: 18
url: /es/java/resource-assignments/overtime-remaining-costs-work/
---
## Introducción
En este tutorial, aprenderemos cómo usar Aspose.Tasks para Java para monitorear las horas extra, los costos restantes y el trabajo en un proyecto. Esto puede ser invaluable para los gerentes de proyectos y líderes de equipos para garantizar que los proyectos se mantengan encaminados y dentro del presupuesto.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Kit de desarrollo de Java (JDK): Aspose.Tasks para Java requiere Java SE 6 o posterior.
2.  Aspose.Tasks para la biblioteca Java: descargue e instale la biblioteca desde[aquí](https://releases.aspose.com/tasks/java/).
3. Entorno de desarrollo integrado (IDE): cualquier IDE de Java como Eclipse, IntelliJ IDEA o NetBeans.

## Importar paquetes
Comience importando los paquetes necesarios en su archivo Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Paso 1: configurar el directorio de datos
Defina el directorio donde se encuentra el archivo de su proyecto:
```java
String dataDir = "Your Data Directory";
```
 Reemplazar`"Your Data Directory"` con la ruta al archivo de su proyecto.
## Paso 2: cargar el proyecto
 Crear una instancia de`Project` objeto y cargar el archivo del proyecto:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Reemplazar`"ResourceAssignmentOvertimes.mpp"` con el nombre del archivo de su proyecto.
## Paso 3: iterar a través de las asignaciones de recursos
Recorra cada asignación de recursos en el proyecto:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Paso 4: Imprima los costos de horas extras y el trabajo
Recupere e imprima costos de horas extras y trabajo para cada asignación de recursos:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Paso 5: Imprima los costos y el trabajo restantes
Recupere e imprima los costos y el trabajo restantes para cada asignación de recursos:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Paso 6: Imprima el trabajo y los costos de horas extras restantes
Recupere e imprima los costos de horas extra restantes y el trabajo para cada asignación de recursos:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Conclusión
Monitorear las horas extras, los costos restantes y el trabajo en un proyecto es crucial para una gestión exitosa del proyecto. Con Aspose.Tasks para Java, puede acceder y realizar un seguimiento fácilmente de esta información, garantizando que sus proyectos se mantengan dentro del cronograma y el presupuesto.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Tasks para Java con otras bibliotecas de Java?
Sí, Aspose.Tasks para Java es compatible con otras bibliotecas y marcos de Java.
### ¿Aspose.Tasks admite diferentes formatos de archivos de proyectos?
Sí, Aspose.Tasks admite varios formatos de archivos de proyecto, incluidos MPP, XML y más.
### ¿Hay una versión de prueba disponible?
 Sí, puedes descargar una prueba gratuita desde[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar soporte si tengo problemas?
 Puedes visitar el foro de Aspose.Tasks[aquí](https://forum.aspose.com/c/tasks/15) para soporte.
### ¿Cómo puedo comprar una licencia para Aspose.Tasks?
 Puedes comprar una licencia de[aquí](https://purchase.aspose.com/buy).