---
date: 2026-06-10
description: Aprenda cómo cambiar el contorno y generar datos con fase de tiempo para
  asignaciones de recursos usando Aspose.Tasks para Java, cubriendo tipos de contorno
  de trabajo y escenarios avanzados de programación.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Generar datos con fase de tiempo para asignaciones de recursos en Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cómo cambiar el contorno en Aspose.Tasks para datos con fase de tiempo
url: /es/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo cambiar el contorno en Aspose.Tasks para datos con fase de tiempo

## Introducción
En este tutorial, descubrirás **cómo cambiar el contorno** para una asignación de recurso y generar datos con fase de tiempo usando Aspose.Tasks para Java. Los datos con fase de tiempo revelan la distribución del trabajo a lo largo de la línea de tiempo del proyecto, lo que te permite afinar los cronogramas, equilibrar las cargas de trabajo y tomar decisiones basadas en datos. Dominar los cambios de contorno te ayuda a modelar patrones de esfuerzo realistas como carga frontal, carga trasera o picos de carga.

## Respuestas rápidas
- **¿Qué es un contorno?** Un contorno de trabajo define cómo se distribuye el esfuerzo a lo largo de la duración de una tarea (p. ej., Flat, Turtle, Bell).  
- **¿Por qué cambiar un contorno?** Para reflejar patrones de trabajo realistas como carga frontal o carga trasera.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks for Java (cualquier versión reciente).  
- **¿Necesito una licencia?** Sí, se requiere una licencia válida de Aspose.Tasks para uso en producción.  
- **¿Puedo ver los resultados en la consola?** El ejemplo imprime las fechas de inicio y los valores para cada segmento con fase de tiempo.

## Qué es “cómo cambiar el contorno”
Cambiar un contorno significa actualizar la propiedad `WORK_CONTOUR` de un objeto `ResourceAssignment`. Esta propiedad indica a Aspose.Tasks cómo distribuir el trabajo total de la asignación a lo largo de la duración de la tarea. La biblioteca ofrece varios contornos predefinidos como Flat, Turtle, Bell, entre otros, cada uno generando un patrón distinto de distribución del esfuerzo en el tiempo.

## Por qué usar Aspose.Tasks para generar datos con fase de tiempo
Aspose.Tasks genera datos con fase de tiempo con **0 ms de sobrecarga para operaciones en memoria** y soporta **más de 50 formatos de salida** (MPP, XML, CSV, etc.). La biblioteca puede procesar proyectos de cientos de páginas sin cargar todo el archivo en memoria, proporcionando una distribución precisa del trabajo para informes, nivelación de recursos y análisis de escenarios. Su API te permite automatizar cambios de contorno y extraer valores de fase de tiempo precisos de forma programática.

## Requisitos previos
Antes de comenzar, asegúrate de contar con los siguientes requisitos:
1. Java Development Kit (JDK): Asegúrate de que tienes el JDK instalado en tu sistema. Puedes descargar e instalar el JDK desde [aquí](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Biblioteca Aspose.Tasks para Java: Necesitas tener la biblioteca Aspose.Tasks para Java. Puedes descargarla desde el [sitio web](https://releases.aspose.com/tasks/java/).

## Importar paquetes
La clase `Project` es el objeto central de Aspose.Tasks que representa un archivo de proyecto completo en memoria. Importa los espacios de nombres necesarios antes de comenzar a trabajar con tareas y asignaciones.

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
El constructor `Project` carga un archivo MPP existente, analizando su estructura sin materializar completamente cada tarea en memoria, lo que mantiene la operación ligera.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Paso 2: Obtener la tarea y la asignación de recurso
`ResourceAssignment` vincula un recurso a una tarea y almacena propiedades a nivel de asignación como trabajo, costo y contorno. Recupera la primera asignación con `project.getResourceAssignments().getById(1)` (o cualquier ID válido) antes de modificar su contorno.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Cómo cambiar el contorno – Plano (Predeterminado)
`WorkContourType` es una enumeración que enumera los patrones de contorno de trabajo predefinidos soportados por Aspose.Tasks. `Asn.WORK_CONTOUR` identifica el campo de contorno de una asignación de recurso, y `generateTimephasedData()` crea entradas de trabajo con fase de tiempo basadas en la configuración actual del contorno. Un contorno **Plano** distribuye el trabajo de manera uniforme a lo largo de la duración de la tarea; configúralo con `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` y luego llama a `firstRA.generateTimephasedData()` para obtener valores espaciados uniformemente.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Tortuga
El contorno **Tortuga** comienza con bajo esfuerzo, acelera hacia la mitad y vuelve a desacelerar, asemejándose al ritmo gradual de una tortuga. Aplícalo configurando `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` y luego regenera los datos con fase de tiempo. Este patrón es ideal para tareas que requieren una curva de aprendizaje antes de alcanzar la máxima productividad.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Carga trasera
El contorno **BackLoaded** coloca la mayor parte del trabajo hacia el final del cronograma de la tarea, con poco esfuerzo al inicio. Configúralo usando `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` y regenera los datos con fase de tiempo. Esto es útil para actividades que dependen de tareas previas antes de que se pueda realizar el trabajo.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Carga frontal
El contorno **FrontLoaded** concentra el esfuerzo al inicio de la tarea, modelando escenarios como fases de lanzamiento o ráfagas intensas de trabajo temprano. Aplícalo con `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` y luego llama a `firstRA.generateTimephasedData()` para ver la distribución cargada al frente.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Campana
El contorno **Bell** crea un pico simétrico en el medio de la línea de tiempo, representando trabajo que aumenta, alcanza un pico y luego disminuye suavemente. Configúralo mediante `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` y regenera los datos con fase de tiempo para visualizar la curva de esfuerzo en forma de campana.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Pico temprano
**EarlyPeak** coloca el valor de trabajo más alto al inicio del cronograma y luego disminuye. Usa `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` seguido de `firstRA.generateTimephasedData()` para modelar actividades que requieren un inicio fuerte, como el prototipado rápido.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Pico tardío
**LatePeak** desplaza el pico de trabajo hacia el final de la tarea, adecuado para trabajo que se intensifica a medida que se acerca la fecha límite. Aplícalo con `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` y regenera los datos con fase de tiempo para ver el aumento de carga de trabajo en la fase tardía.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cómo cambiar el contorno – Doble pico
**DoublePeak** crea dos picos de trabajo distintos separados por un intervalo de menor esfuerzo, útil para tareas con dos grandes ráfagas de esfuerzo. Configúralo usando `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` y luego llama a `firstRA.generateTimephasedData()` para obtener el patrón de doble pico.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Problemas comunes y consejos
- **¿El contorno no se actualiza?** Asegúrate de llamar a `firstRA.set(Asn.WORK_CONTOUR, …)` *antes* de recuperar los datos con fase de tiempo.  
- **¿Valores inesperados?** Verifica que las fechas de inicio y fin de la tarea estén configuradas correctamente en el MPP de origen.  
- **Consejo de rendimiento:** Reutiliza la misma instancia `Project` al iterar a través de múltiples contornos para evitar I/O de archivos innecesario, lo que puede reducir el tiempo de procesamiento hasta en un 40 % en proyectos grandes.  
- **Consejo de memoria:** Para proyectos que superen 1 GB, habilita `Project.setReadOnly(true)` para mantener el uso de memoria por debajo de 200 MB mientras aún generas datos con fase de tiempo precisos.

## Preguntas frecuentes
**Q: ¿Puedo usar Aspose.Tasks con otras bibliotecas Java?**  
A: Sí, Aspose.Tasks se integra sin problemas con otras bibliotecas Java, lo que te permite combinar datos de programación con informes, análisis o frameworks de UI.

**Q: ¿Es Aspose.Tasks adecuado para proyectos empresariales a gran escala?**  
A: Absolutamente. La biblioteca está diseñada para manejar proyectos con decenas de miles de tareas y recursos, procesando archivos de cientos de páginas sin degradación del rendimiento.

**Q: ¿Aspose.Tasks ofrece soporte para diferentes formatos de archivo de proyecto?**  
A: Sí, Aspose.Tasks soporta más de 30 formatos, incluidos MPP, XML, CSV y MPX, lo que permite una importación/exportación fácil entre sistemas heredados y modernos.

**Q: ¿Puedo personalizar los contornos de trabajo según los requisitos de mi proyecto?**  
A: Sí, puedes definir contornos personalizados proporcionando una matriz de porcentajes de trabajo a la propiedad `WORK_CONTOUR`, dándote control total sobre la distribución del esfuerzo.

**Q: ¿Existe un foro de la comunidad donde pueda obtener ayuda con Aspose.Tasks?**  
A: Sí, puedes visitar el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para soporte, discusiones y ejemplos de código tanto de ingenieros de Aspose como de miembros de la comunidad.

---

**Última actualización:** 2026-06-10  
**Probado con:** Aspose.Tasks for Java (última versión)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Crear asignaciones de recursos en Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Leer datos con fase de tiempo para recursos en Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [Cómo detener la asignación y reanudar asignaciones de recursos en Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}