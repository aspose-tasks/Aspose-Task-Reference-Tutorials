---
date: 2026-01-23
description: Aprenda a establecer la duración de la línea base y crear una instancia
  de proyecto usando Aspose.Tasks para Java. Esta guía paso a paso le ayuda a gestionar
  las líneas base de las tareas de manera eficiente.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Cómo establecer la duración de la línea base en Aspose.Tasks para Java
url: /es/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer la duración de la baseline en Aspose.Tasks para Java

## Introducción
Establecer una baseline es un paso fundamental para rastrear el progreso del proyecto frente al plan original. En este tutorial aprenderás **cómo establecer la baseline** de duración para tareas en Microsoft Project usando la biblioteca Aspose.Tasks para Java, y verás por qué establecer una baseline temprano puede ahorrarte tiempo y dolores de cabeza más adelante.

## Respuestas rápidas
- **¿Qué significa “set baseline”?** Registra la fecha de inicio, fin y duración original de una tarea para que puedas comparar cambios futuros.  
- **¿Qué clase de Aspose.Tasks crea un proyecto?** La clase `Project` – también aprenderás cómo **crear una instancia de proyecto** correctamente.  
- **¿Necesito una licencia para ejecutar el código?** Una licencia de evaluación gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Puedo recuperar baselines interinos?** Sí, Aspose.Tasks te permite consultar baselines interinos y sus costos fijos.  
- **¿Qué versión de Java se requiere?** Se recomienda Java 8 o posterior.

## ¿Qué es una baseline de tarea y por qué establecerla?
Una baseline de tarea captura el cronograma planificado (fecha de inicio, fecha de fin y duración) en un momento específico. Al establecer una baseline creas un punto de referencia que facilita detectar desviaciones de cronograma, sobrecostos y sobreasignación de recursos a medida que el proyecto avanza.

## ¿Por qué usar Aspose.Tasks para la gestión de baselines?
- **Compatibilidad total con .mpp** – leer y escribir archivos nativos de Microsoft Project sin necesidad de Office.  
- **API rica** – acceder a datos de baseline, baselines interinos e información con fase de tiempo de forma programática.  
- **Multiplataforma** – funciona en Windows, Linux y macOS con cualquier JDK estándar.

## Requisitos previos
1. **Entorno de desarrollo Java** – JDK 8+ instalado y configurado.  
2. **Aspose.Tasks para Java** – descarga la biblioteca desde [aquí](https://releases.aspose.com/tasks/java/).  
3. **IDE o herramienta de compilación** – Maven, Gradle o cualquier IDE que prefieras.

## Importar paquetes
Primero, importa las clases necesarias en tu proyecto Java:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Paso 1: Crear una instancia de proyecto
Crear una instancia de proyecto es la base para cualquier manipulación posterior. Este paso muestra cómo **crear una instancia de proyecto** usando Aspose.Tasks:

```java
Project project = new Project();
```

## Paso 2: Crear una baseline de tarea
Agrega una nueva tarea a la raíz del proyecto y establece su baseline. Esto registra el cronograma original de la tarea:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Paso 3: Mostrar información de la baseline de tarea
Recupera la baseline que acabas de crear e imprime sus propiedades clave. Esto te ayuda a verificar que la baseline se haya establecido correctamente:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Paso 4: Verificar baseline interino y costo fijo
Si trabajas con baselines interinos, puedes consultar si la baseline actual es interina y cualquier costo fijo asociado:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Paso 5: Imprimir datos con fase de tiempo
Los datos con fase de tiempo muestran cómo se distribuye la baseline a lo largo del tiempo. Recorre la colección para inspeccionar cada entrada:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Al seguir estos pasos, puedes **cómo establecer la baseline** de duración para cualquier tarea y recuperar información detallada de la baseline usando Aspose.Tasks para Java.

## Problemas comunes y soluciones
- **Baseline no aparece en MS Project:** Asegúrate de haber llamado `project.setBaseline(BaselineType.Baseline)` **después** de agregar la tarea.  
- **NullPointerException en `getBaselines()`:** Verifica que la tarea se haya agregado al proyecto antes de establecer la baseline.  
- **Desajuste de unidad de tiempo:** Usa `TimeUnitType` para formatear la duración correctamente, especialmente al trabajar con calendarios personalizados.

## Preguntas frecuentes
### ¿Qué es una baseline de tarea en MS Project?
Una baseline de tarea en MS Project es una captura del cronograma planificado inicial para una tarea, incluyendo su fecha de inicio, fecha de fin y duración.

### ¿Por qué es importante gestionar baselines de tarea?
Gestionar baselines de tarea ayuda a comparar el cronograma planificado con el progreso real del proyecto, facilitando un mejor seguimiento y la toma de decisiones.

### ¿Puedo modificar una baseline de tarea una vez establecida?
Sí, puedes modificar baselines de tarea en MS Project para reflejar cambios en el plan del proyecto. Sin embargo, es esencial documentar cualquier desviación de la baseline original.

### ¿Aspose.Tasks admite otras funcionalidades de gestión de proyectos?
Sí, Aspose.Tasks ofrece una amplia gama de funciones para la gestión de proyectos, incluyendo programación de tareas, asignación de recursos y generación de diagramas de Gantt.

### ¿Dónde puedo encontrar soporte para Aspose.Tasks?
Puedes encontrar soporte para Aspose.Tasks en el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15), donde puedes hacer preguntas e interactuar con otros usuarios.

## Preguntas frecuentes adicionales
**P: ¿Necesito llamar a `setBaseline` para cada tarea individualmente?**  
R: No. Llamar a `project.setBaseline(BaselineType.Baseline)` registra la baseline para todas las tareas del proyecto de una sola vez.

**P: ¿Cómo puedo establecer una baseline interina para una tarea específica?**  
R: Usa `project.setBaseline(BaselineType.Baseline1)` (o Baseline2‑Baseline10) después de actualizar el cronograma de la tarea.

**P: ¿Es posible exportar los datos de la baseline a CSV?**  
R: Sí. Itera sobre `task.getBaselines()` y escribe los campos deseados en un archivo CSV usando I/O estándar de Java.

**P: ¿Puedo leer un archivo .mpp existente que ya contiene baselines?**  
R: Absolutamente. Carga el archivo con `new Project("myproject.mpp")` y luego accede a las baselines de cada tarea como se muestra arriba.

**P: ¿Aspose.Tasks maneja archivos multiproyecto?**  
R: Aspose.Tasks trabaja con archivos .mpp de un solo proyecto. Para escenarios multiproyecto, combina los proyectos programáticamente.

---

**Última actualización:** 2026-01-23  
**Probado con:** Aspose.Tasks para Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}