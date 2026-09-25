---
date: 2026-09-25
description: Aprenda cómo crear un cronograma de proyecto en Java usando Aspose.Tasks.
  Esta guía le muestra cómo agregar tareas resumen, gestionar la jerarquía del proyecto
  y establecer el directorio de documentos de manera eficiente.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Crear tareas en Aspose.Tasks
og_description: Aprenda cómo crear un cronograma de proyecto en Java usando Aspose.Tasks.
  Siga instrucciones paso a paso para agregar tareas resumen, gestionar la jerarquía
  y establecer el directorio de documentos.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Cómo crear un cronograma de proyecto con Aspose.Tasks para Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Cómo crear un cronograma de proyecto con Aspose.Tasks para Java
url: /es/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un cronograma de proyecto con Aspose.Tasks para Java

## Introducción
En este tutorial aprenderá cómo **crear un cronograma de proyecto** en una aplicación Java usando Aspose.Tasks. Ya sea que esté construyendo una lista de tareas simple o un planificador empresarial complejo, los pasos a continuación le guiarán para agregar tareas resumen, gestionar la jerarquía del proyecto y establecer el directorio del documento, todo con fragmentos de código claros y ejecutables. Al final, tendrá un cronograma completamente estructurado listo para su manipulación o exportación.

## Respuestas rápidas
- **¿Qué gestiona Aspose.Tasks?** Maneja jerarquías de tareas, recursos, calendarios y formatos de archivos de proyecto (MS‑Project, Primavera, etc.).  
- **¿Necesito una licencia para el desarrollo?** Una licencia temporal gratuita funciona para evaluación; se requiere una licencia completa para producción.  
- **¿Qué versión de Java es compatible?** Java 8 y versiones posteriores son totalmente compatibles.  
- **¿Puedo agregar campos personalizados a las tareas?** Sí, puede extender las tareas con campos definidos por el usuario mediante la API.  
- **¿Hay soporte incorporado para diagramas de Gantt?** Aspose.Tasks puede exportar a PDF/HTML que incluyen visualizaciones de Gantt.

## ¿Qué es un cronograma de proyecto en Aspose.Tasks?
Un cronograma de proyecto es el conjunto completo de tareas, dependencias y cronologías que definen cómo se realizará el trabajo. Aspose.Tasks almacena esta información en un objeto `Project` que puede leer, modificar y guardar en varios formatos. Incluye fechas de inicio y fin, restricciones y asignaciones de recursos, lo que permite una planificación y generación de informes integral.

## ¿Por qué usar Aspose.Tasks para la gestión de proyectos Java?
Aspose.Tasks admite **más de 30 formatos de entrada y salida** y puede procesar proyectos con **hasta 10 000 tareas** sin cargar todo el archivo en memoria, ofreciendo alto rendimiento para escenarios de gestión de proyectos Java a gran escala.

## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de contar con los siguientes requisitos:
- **Java Development Kit (JDK)** – JDK 8 o posterior instalado en su máquina.  
- **Biblioteca Aspose.Tasks para Java** – Descargue e instale la biblioteca desde [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
- **Entorno de Desarrollo Integrado (IDE)** – Use Eclipse, IntelliJ IDEA o cualquier IDE compatible con Java que prefiera.

## Importar paquetes
`Project`, `Task` y clases relacionadas se encuentran en el espacio de nombres `com.aspose.tasks`. Impórtelas al inicio de su archivo Java:

La clase `Project` representa un cronograma de proyecto completo y proporciona métodos para manipular tareas y recursos.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

La clase `Project` es el punto de entrada para todas las operaciones sobre un archivo de proyecto.

## ¿Cómo crear un cronograma de proyecto con Aspose.Tasks?

Cargue una nueva instancia de `Project`, establezca el directorio del documento y comience a agregar tareas. Este párrafo de respuesta directa explica el flujo principal: crea un `Project`, configura su `RootFolder` (el directorio del documento), luego agrega una tarea resumen seguida de subtareas. Todos los cambios se mantienen en memoria hasta que llama a `save` para guardar el cronograma en un archivo.

### Paso 1: establecer el directorio del documento
Defina dónde se escribirá el archivo de proyecto resultante. Establecer el directorio al principio garantiza que todas las operaciones de guardado posteriores utilicen una ruta coherente.

La propiedad `RootFolder` especifica la carpeta base donde se leen o escriben los archivos de proyecto.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Paso 2: crear un nuevo proyecto
Instancie un nuevo objeto `Project` que contendrá su cronograma. Opcionalmente, puede pasar una ruta de archivo preexistente para cargar un cronograma existente y modificarlo.

El constructor `Project` crea un cronograma vacío listo para la adición de tareas.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Paso 3: agregar una tarea resumen
Una tarea resumen agrupa subtareas relacionadas y aparece como un nodo colapsable en los diagramas de Gantt. Use la clase `Task` y establezca `IsSummary` a `true`.

El método `addTask` crea una nueva tarea bajo un padre especificado y devuelve su ID.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Paso 4: agregar una subtarea
Las subtareas heredan las fechas de inicio/fin de su tarea resumen padre a menos que las sobrescriba. Agregar una subtarea es tan simple como llamar a `addTask` nuevamente y especificar el ID del padre.

Llamar a `addTask` con un ID de padre agrega una subtarea bajo esa tarea resumen.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Continúe agregando tantas tareas y subtareas como necesite para su proyecto. Cada paso contribuye a construir una jerarquía de proyecto estructurada que puede exportarse a MS‑Project, PDF u otros formatos compatibles.

## Problemas comunes y soluciones
- **Problema:** “Directorio del documento no encontrado.”  
  **Solución:** Verifique que la ruta que asigna a `RootFolder` exista en el sistema de archivos y que su proceso Java tenga permisos de escritura.
- **Problema:** Las subtareas no aparecen bajo la tarea resumen.  
  **Solución:** Asegúrese de pasar el ID de tarea padre correcto al llamar a `addTask`. La API requiere el ID del padre como segundo argumento.
- **Problema:** Los proyectos grandes causan OutOfMemoryError.  
  **Solución:** Aspose.Tasks procesa las tareas en modo de transmisión; aumente el tamaño del heap de JVM (`-Xmx2g`) o divida el cronograma en varios archivos.

## Preguntas frecuentes
**Q:** ¿Es Aspose.Tasks adecuado para proyectos de pequeña escala?  
**A:** Absolutamente. La biblioteca escala desde una lista de una sola tarea hasta cronogramas a nivel empresarial con miles de tareas.

**Q:** ¿Dónde puedo encontrar documentación detallada de Aspose.Tasks para Java?  
**A:** Consulte la documentación [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**Q:** ¿Cómo obtengo una licencia temporal para Aspose.Tasks?  
**A:** Visite la [temporary license request page](https://purchase.aspose.com/temporary-license/) para obtener una licencia de tiempo limitado que funciona para desarrollo y pruebas.

**Q:** ¿Puedo personalizar los atributos de las tareas usando Aspose.Tasks?  
**A:** Sí, puede extender las tareas con campos personalizados, asignar recursos y modificar calendarios programáticamente.

**Q:** ¿Existe una comunidad de soporte para usuarios de Aspose.Tasks?  
**A:** ¡Absolutamente! Únase a la comunidad de Aspose.Tasks en [the support forum](https://forum.aspose.com/c/tasks/15).

**Última actualización:** 2026-09-25  
**Probado con:** Aspose.Tasks 24.12 para Java  
**Autor:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Tutoriales relacionados

- [Establecer la fecha de inicio del proyecto en MS Project usando Aspose.Tasks para Java](/tasks/java/project-properties/write-project-info/)
- [Crear dependencias de tareas de gestión de proyectos en Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Cómo agregar recursos al proyecto y crear asignaciones de recursos en Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}