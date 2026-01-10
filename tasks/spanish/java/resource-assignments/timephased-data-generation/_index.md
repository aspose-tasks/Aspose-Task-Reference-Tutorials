---
date: 2026-01-10
description: Aprenda a cambiar el contorno y generar datos con fase de tiempo para
  asignaciones de recursos usando Aspose.Tasks para Java, mejorando la eficiencia
  de la gestión de proyectos.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo cambiar el contorno en Aspose.Tasks para datos con fase de tiempo
url: /es/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo cambiar el contorno en Aspose.Tasks para datos con fases temporales

## Introducción
En este tutorial, descubrirás **cómo cambiar el contorno** para una asignación de recursos y generar datos con fases temporales usando Aspose.Tasks para Java. Los datos con fases temporales revelan la distribución del trabajo a lo largo de la línea de tiempo del proyecto, lo que te permite afinar los cronogramas, equilibrar la carga de trabajo y tomar decisiones basadas en datos.

## Respuestas rápidas
- **¿Qué es un contorno?** Un contorno de trabajo define cómo se distribuye el esfuerzo a lo largo de la duración de una tarea (p. ej., Plano, Tortuga, Campana).  
- **¿Por qué cambiar un contorno?** Para reflejar patrones de trabajo realistas, como cargar el esfuerzo al inicio o al final.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks para Java (cualquier versión reciente).  
- **¿Necesito una licencia?** Sí, se requiere una licencia válida de Aspose.Tasks para uso en producción.  
- **¿Puedo ver los resultados en la consola?** El ejemplo imprime las fechas de inicio y los valores para cada segmento con fases temporales.

## ¿Qué es “cómo cambiar el contorno”?
Cambiar un contorno significa actualizar la propiedad `WORK_CONTOUR` de una `ResourceAssignment`. Aspose.Tasks admite varios contornos predefinidos (Plano, Tortuga, Campana, etc.) que influyen en cómo se asigna el trabajo a lo largo del tiempo.

## ¿Por qué usar Aspose.Tasks para generar datos con fases temporales?
- **Informes precisos:** Exporta la distribución exacta del trabajo para herramientas de generación de informes.  
- **Planificación de escenarios:** Prueba diferentes contornos sin alterar el cronograma original.  
- **Automatización:** Integra en pipelines de CI para validar automáticamente la salud del proyecto.

## Requisitos previos
Antes de comenzar, asegúrate de contar con los siguientes requisitos:
1. Java Development Kit (JDK): Asegúrate de que tienes el JDK instalado en tu sistema. Puedes descargar e instalar el JDK desde [aquí](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Biblioteca Aspose.Tasks para Java: Necesitas tener la biblioteca Aspose.Tasks para Java. Puedes descargarla desde el [sitio web](https://releases.aspose.com/tasks/java/).

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

## Paso 1: Leer el archivo MPP de origen
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Paso 2: Obtener la tarea y la asignación de recursos
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Cómo cambiar el contorno – Plano (Predeterminado)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Tortuga
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Cargado al final
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Cargado al inicio
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Campana
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Pico temprano
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Pico tardío
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Doble pico
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Problemas comunes y consejos
- **¿El contorno no se actualiza?** Asegúrate de llamar a `firstRA.set(Asn.WORK_CONTOUR, …)` *antes* de obtener los datos con fases temporales.
- **¿Valores inesperados?** Verifica que las fechas de inicio y fin de la tarea estén correctamente establecidas en el MPP de origen.
- **Consejo de rendimiento:** Reutiliza la misma instancia de `Project` al iterar a través de varios contornos para evitar operaciones de I/O de archivo innecesarias.

## Preguntas frecuentes
### ¿Puedo usar Aspose.Tasks con otras bibliotecas Java?
Sí, Aspose.Tasks puede integrarse con otras bibliotecas Java para mejorar las capacidades de gestión de proyectos.

### ¿Es Aspose.Tasks adecuado para proyectos empresariales a gran escala?
Absolutamente, Aspose.Tasks está diseñado para manejar proyectos de cualquier tamaño, incluidas iniciativas empresariales a gran escala.

### ¿Aspose.Tasks ofrece soporte para diferentes formatos de archivo de proyecto?
Sí, Aspose.Tasks admite una variedad de formatos, como MPP, XML y MPX.

### ¿Puedo personalizar los contornos de trabajo según los requisitos de mi proyecto?
Sí, puedes definir contornos de trabajo personalizados para adaptarse a necesidades de programación específicas.

### ¿Existe un foro comunitario donde pueda obtener ayuda con Aspose.Tasks?
Sí, puedes visitar el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener soporte y participar en discusiones.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}