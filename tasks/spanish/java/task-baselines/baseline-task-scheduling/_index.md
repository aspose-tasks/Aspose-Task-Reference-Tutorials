---
date: 2026-08-29
description: Aprenda cómo leer datos de baseline y programar tareas usando Aspose.Tasks
  para Java, para que pueda comparar el progreso planificado con el real de manera
  eficiente.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Programación de tareas de baseline en Aspose.Tasks
og_description: Aprenda cómo leer datos de baseline y programar tareas usando Aspose.Tasks
  para Java, lo que permite comparar con precisión el progreso planificado con el
  real.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Cómo leer baseline y programar tareas con Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Cómo leer baseline y programar tareas con Aspose.Tasks
url: /es/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer la línea base y programar tareas con Aspose.Tasks

En esta guía descubrirás **cómo leer la línea base** de información y programar tareas de forma programática usando Aspose.Tasks para Java. Al final del tutorial, podrás capturar el plan original del proyecto, compararlo con el progreso real y generar informes de variación, todo sin necesidad de tener Microsoft Project instalado.

## Introducción a la línea base de gestión de proyectos
Gestionar una **línea base de gestión de proyectos** es una piedra angular de la gestión de proyectos eficaz. Te permite capturar el plan original y luego comparar **el progreso planificado vs el real** para detectar variaciones temprano. En este tutorial, repasaremos cómo programar líneas base de tareas usando Aspose.Tasks para Java, dándote las herramientas para **gestionar líneas base de proyectos** con confianza y mantener tus proyectos en buen camino.

## Respuestas rápidas
- **¿Qué representa una línea base de gestión de proyectos?**  
  Registra el cronograma, costo y alcance aprobados al inicio del proyecto, proporcionando una referencia para el análisis de variaciones.  
- **¿Qué biblioteca maneja la programación de líneas base en Java?**  
  Aspose.Tasks para Java ofrece una API pura de Java que soporta más de 45 formatos de entrada y salida y proyectos de hasta 100 000 tareas.  
- **¿Necesito una licencia para ejecutar el código?**  
  Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para uso en producción.  
- **¿Cuáles son los requisitos principales?**  
  Java Development Kit (JDK) 11+ y la biblioteca Aspose.Tasks para Java.  
- **¿Puedo ver las fechas de la línea base después de establecerlas?**  
  Sí—utiliza el objeto `TaskBaseline` para leer los valores de inicio, fin y duración.

## ¿Qué es una línea base de gestión de proyectos?
Una línea base de gestión de proyectos registra el cronograma, presupuesto y alcance aprobados al inicio de la ejecución. Sirve como punto de referencia para medir el rendimiento e identificar desviaciones a lo largo del ciclo de vida del proyecto. Incluye las fechas de inicio y fin planificadas, el costo total y los detalles del alcance, proporcionando una instantánea completa para comparaciones futuras.

## ¿Por qué usar Aspose.Tasks para la programación de líneas base?
Aspose.Tasks proporciona una API pura de Java que funciona sin necesidad de instalar Microsoft Project. Soporta **más de 45 formatos de entrada y salida**, puede procesar proyectos con **hasta 100 000 tareas** en modo de uso eficiente de memoria, y ofrece métodos incorporados para leer y escribir datos de líneas base, lo que hace que la generación de informes automatizada e integración sea sencilla.

## Prerequisitos
- **Java Development Kit (JDK)** – instala JDK 11 o posterior. Puedes descargarlo desde el [sitio web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java library** – descarga la última versión desde la [página de descarga](https://releases.aspose.com/tasks/java/) y agrega el JAR al classpath de tu proyecto.

## Importar paquetes
Las clases `Project`, `Task` y `TaskBaseline` se encuentran en el espacio de nombres `com.aspose.tasks`. Impórtalas al inicio de tu archivo fuente:

La clase `Project` es el objeto de nivel superior de Aspose.Tasks que representa un archivo de proyecto único en memoria. Proporciona acceso a tareas, recursos y colecciones de líneas base.

## ¿Cómo leer la línea base?
Carga el proyecto, luego consulta la colección `TaskBaseline` para cada tarea. El objeto `TaskBaseline` devuelve el inicio, fin y duración de la línea base que se capturaron cuando llamaste a `setBaseline`. Este enfoque directo te permite leer los valores de la línea base sin analizar archivos XML o binarios.

## Paso 1: crear una nueva instancia de proyecto
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## Paso 2: definir una tarea y establecer la línea base
```java
Project project = new Project();
```

## Paso 3: acceder a la información de la línea base
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Paso 4: mostrar la duración de la línea base
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Paso 5: mostrar la fecha de inicio de la línea base
```java
System.out.println(baseline.getDuration().toString());
```

## Paso 6: mostrar la fecha de fin de la línea base
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Problemas comunes y soluciones
- **Línea base no establecida:** Asegúrate de llamar a `project.setBaseline(BaselineType.Baseline)` **después** de agregar tareas; de lo contrario la colección de líneas base estará vacía.  
- **Valores nulos:** Si `task.getBaselines()` devuelve una lista vacía, verifica que la tarea se haya añadido a la jerarquía del proyecto antes de establecer la línea base.  
- **Formato de fecha:** Los métodos `getStart()` y `getFinish()` devuelven objetos `java.util.Date`. Usa `SimpleDateFormat` si necesitas un formato de visualización personalizado.

## Preguntas frecuentes

**Q: ¿Cómo creo una nueva instancia de proyecto en Aspose.Tasks?**  
A: Instancia la clase `Project` (`Project project = new Project();`). Esto crea un nuevo archivo de proyecto listo para tareas y líneas base.

**Q: ¿Cuál es la diferencia entre `BaselineType.Baseline` y otros tipos de línea base?**  
A: `BaselineType.Baseline` se refiere a la línea base primaria (Línea base 1). Aspose.Tasks también soporta Línea base 2‑10 para instantáneas adicionales.

**Q: ¿Puedo exportar los datos de la línea base a Excel o CSV?**  
A: Sí, puedes iterar sobre los objetos `TaskBaseline` y escribir los valores en un archivo CSV usando la I/O estándar de Java.

**Q: ¿Establecer una línea base afecta las fechas de las tareas existentes?**  
A: Establecer una línea base captura las fechas actuales pero no modifica el cronograma activo de la tarea. Puedes seguir ajustando las fechas de inicio/fin después de establecer la línea base.

**Q: ¿Es posible comparar múltiples líneas base programáticamente?**  
A: Absolutamente. Recupera cada línea base mediante `task.getBaselines().get(index)` y compara sus propiedades `Start`, `Finish` y `Duration`.

---

**Última actualización:** 2026-08-29  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Tutoriales relacionados

- [Crear lista de tareas Java – Línea base de MS Project usando Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Cómo establecer la duración de la línea base en Aspose.Tasks para Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Crear proyecto MPP Java – Cambiar el progreso de la tarea con Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}