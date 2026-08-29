---
date: 2026-08-29
description: Aprenda cómo establecer la baseline duration y rastrear el project progress
  usando Aspose.Tasks for Java. Esta guía paso a paso le ayuda a gestionar los task
  baselines de manera eficiente.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Cómo establecer Baseline Duration en Aspose.Tasks for Java
og_description: Aprenda cómo establecer la baseline duration y rastrear el project
  progress usando Aspose.Tasks for Java. Siga esta guía detallada para gestionar los
  task baselines de manera eficiente.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Cómo establecer la baseline duration para rastrear el project progress
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Cómo establecer la baseline duration para rastrear el project progress
url: /es/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer la duración de la línea base para rastrear el progreso del proyecto

## Introducción
El seguimiento del progreso del proyecto comienza con una línea base sólida. En este tutorial descubrirá **cómo establecer la duración de la línea base** para tareas en archivos de Microsoft Project usando la biblioteca Aspose.Tasks para Java, y comprenderá por qué establecer una línea base temprano le ayuda a monitorizar la desviación del cronograma, la variación de costos y la sobreasignación de recursos a lo largo de la vida del proyecto.

## Respuestas rápidas
- **¿Qué significa “set baseline”?** Registra el inicio, fin y duración originales de una tarea para que pueda comparar cambios futuros.  
- **¿Qué clase de Aspose.Tasks crea un proyecto?** La clase `Project` – también aprenderá cómo **crear una instancia de proyecto** correctamente.  
- **¿Necesito una licencia para ejecutar el código?** Una licencia de evaluación gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Puedo recuperar líneas base interinas?** Sí, Aspose.Tasks le permite consultar líneas base interinas y sus costos fijos.  
- **¿Qué versión de Java se requiere?** Se recomienda Java 8 o posterior.  
- **¿Cómo me ayuda esto a rastrear el progreso del proyecto?** Una vez establecida la línea base, puede comparar instantáneamente las fechas reales con el plan original usando las funciones de informes incorporadas.

## Qué es una línea base de tarea y por qué establecerla
Una línea base de tarea captura el cronograma planificado (fecha de inicio, fecha de fin y duración) en un momento específico. Al establecer una línea base crea un punto de referencia que facilita detectar desviaciones del cronograma, sobrecostos y sobreasignación de recursos a medida que el proyecto evoluciona.

## Por qué usar Aspose.Tasks para la gestión de líneas base
Aspose.Tasks ofrece **compatibilidad total con .mpp** – puede leer y escribir archivos nativos de Microsoft Project sin necesidad de tener Microsoft Office instalado. La API le brinda acceso programático a **más de 50 formatos de entrada y salida**, soporta **líneas base interinas 1‑10**, y puede manejar **proyectos de cientos de páginas** sin cargar todo el archivo en memoria, lo cual es esencial para el procesamiento por lotes de alto rendimiento.

## Requisitos previos
1. **Entorno de desarrollo Java** – JDK 8+ instalado y configurado.  
2. **Aspose.Tasks for Java** – descargue la biblioteca desde la [página de descarga de Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **IDE o herramienta de compilación** – Maven, Gradle, o cualquier IDE que prefiera.

## Importar paquetes
Las siguientes importaciones traen las clases centrales de Aspose.Tasks necesarias para trabajar con proyectos, tareas, líneas base y datos con fase de tiempo.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Paso 1: crear una instancia de proyecto
La clase `Project` representa un archivo de Microsoft Project en memoria y es el punto de entrada para todas las operaciones.

```java
Project project = new Project();
```

## Paso 2: crear una línea base de tarea
Un `TaskBaseline` almacena el inicio, fin y duración planificados para una tarea específica.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Paso 3: mostrar información de la línea base de la tarea
El método `getBaselines()` devuelve la colección de líneas base asociadas a una tarea.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Paso 4: verificar la línea base interina y el costo fijo
`BaselineType` enumera las líneas base primarias e interinas (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Paso 5: imprimir datos con fase de tiempo
`TimephasedData` representa una pieza de información de cronograma para un intervalo de tiempo específico.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Al seguir estos pasos, puede **establecer la duración de la línea base** para cualquier tarea y recuperar información detallada de la línea base usando Aspose.Tasks para Java, brindándole una forma fiable de **rastrear el progreso del proyecto** a lo largo del ciclo de vida del proyecto.

## Problemas comunes y soluciones
- **La línea base no aparece en MS Project:** Asegúrese de haber llamado a `project.setBaseline(BaselineType.Baseline)` **después** de agregar la tarea.  
- **NullPointerException en `getBaselines()`:** Verifique que la tarea se haya agregado al proyecto antes de establecer la línea base.  
- **Desajuste de unidad de tiempo:** Use `TimeUnitType` para formatear la duración correctamente, especialmente al trabajar con calendarios personalizados.

## Preguntas frecuentes

### ¿Qué es una línea base de tarea en MS Project?
Una línea base de tarea en MS Project es una captura del cronograma planificado inicial para una tarea, incluyendo su fecha de inicio, fecha de fin y duración.

### ¿Por qué es importante gestionar las líneas base de tareas?
Gestionar las líneas base de tareas ayuda a comparar el cronograma planificado con el progreso real del proyecto, facilitando un mejor seguimiento y la toma de decisiones.

### ¿Puedo modificar una línea base de tarea una vez establecida?
Sí, puede modificar las líneas base de tareas en MS Project para reflejar cambios en el plan del proyecto. Sin embargo, es esencial documentar cualquier desviación de la línea base original.

### ¿Aspose.Tasks admite otras funcionalidades de gestión de proyectos?
Sí, Aspose.Tasks ofrece una amplia gama de funciones para la gestión de proyectos, incluyendo programación de tareas, asignación de recursos y generación de diagramas de Gantt.

### ¿Dónde puedo encontrar soporte para Aspose.Tasks?
Puede encontrar soporte para Aspose.Tasks en el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15), donde puede hacer preguntas e interactuar con otros usuarios.

## Preguntas frecuentes adicionales
**Q: ¿Necesito llamar a `setBaseline` para cada tarea individualmente?**  
A: No. Llamar a `project.setBaseline(BaselineType.Baseline)` registra la línea base para todas las tareas del proyecto de una sola vez.

**Q: ¿Cómo puedo establecer una línea base interina para una tarea específica?**  
A: Use `project.setBaseline(BaselineType.Baseline1)` (o Baseline2‑Baseline10) después de actualizar el cronograma de la tarea.

**Q: ¿Es posible exportar los datos de la línea base a CSV?**  
A: Sí. Itere sobre `task.getBaselines()` y escriba los campos deseados en un archivo CSV usando la I/O estándar de Java.

**Q: ¿Puedo leer un archivo .mpp existente que ya contiene líneas base?**  
A: Absolutamente. Cargue el archivo con `new Project("myproject.mpp")` y luego acceda a las líneas base de cada tarea como se muestra arriba.

**Q: ¿Aspose.Tasks maneja archivos multi‑proyecto?**  
A: Aspose.Tasks funciona con archivos .mpp de un solo proyecto. Para escenarios multi‑proyecto, combine los proyectos programáticamente.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Tutoriales relacionados

- [Crear lista de tareas Java – Línea base de MS Project usando Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Crear proyecto MPP Java – Cambiar progreso de la tarea con Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Línea base de gestión de proyectos – Programación de tareas con Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}