---
date: 2026-08-29
description: Aprenda cómo agregar una tarea a un proyecto en Java, crear una lista
  de tareas y establecer una línea base sin Microsoft Project utilizando Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Crear una línea base de tarea en Aspose.Tasks
og_description: Aprenda cómo agregar una tarea a un proyecto en Java y establecer
  una línea base usando Aspose.Tasks. Esta guía muestra código paso a paso sin necesidad
  de Microsoft Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Cómo agregar una tarea a un proyecto en Java y establecer una línea base
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Cómo agregar una tarea a un proyecto en Java y establecer una línea base
url: /es/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar una tarea a un proyecto en Java y establecer una línea base

## Introducción
En este tutorial **agregarás una tarea al proyecto** programáticamente, generarás una línea base de tarea de Microsoft Project y guardarás el archivo, todo sin abrir nunca Microsoft Project. Aspose.Tasks for Java te brinda una API pura de Java que funciona en cualquier plataforma, lo que la hace perfecta para canalizaciones de compilación automatizadas, servicios de informes o cualquier solución del lado del servidor que necesite manipular archivos .mpp.

## Respuestas rápidas
- **¿Qué hace Aspose.Tasks?** Proporciona una API Java para crear, leer y editar archivos de Microsoft Project sin requerir Microsoft Project.  
- **¿Necesito tener Microsoft Project instalado?** No, la biblioteca funciona completamente de forma independiente.  
- **¿Qué versión de Java se requiere?** JDK 8 o superior.  
- **¿Puedo establecer una línea base para una sola tarea?** Sí – llama a `setBaseline` sobre una lista que contenga solo las tareas que deseas.  
- **¿Se necesita una licencia para producción?** Sí, una licencia comercial elimina los límites de evaluación y desbloquea todas las funciones.

## ¿Qué es una línea base de tarea?
Una línea base de tarea captura la fecha de inicio planificada originalmente, la fecha de finalización y el esfuerzo de trabajo para una tarea en el momento en que el cronograma se guarda por primera vez. Esta instantánea actúa como punto de referencia, permitiendo a los gerentes de proyecto comparar el progreso y los costos reales con el plan inicial, y calcular variaciones para el análisis de desempeño.

## ¿Por qué usar Aspose.Tasks para agregar una tarea a un proyecto en Java?
Puedes crear, modificar y establecer líneas base de tareas sin ninguna instalación de escritorio, lo que permite flujos de trabajo totalmente automatizados. Aspose.Tasks soporta **más de 50 formatos de entrada y salida** y puede manejar proyectos con **cientos de tareas** manteniendo el uso de memoria por debajo de 200 MB, lo que la hace ideal para servicios en la nube y canalizaciones CI/CD.

## Requisitos previos
1. **Java Development Kit (JDK)** – instala JDK 8 o una versión más reciente.  
2. **Aspose.Tasks for Java** – descarga la biblioteca desde el [download link](https://releases.aspose.com/tasks/java/).  

## Importar paquetes
Para comenzar a trabajar con Aspose.Tasks en tu proyecto Java, importa los paquetes necesarios:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Paso 1: crear un objeto de proyecto
La clase `Project` es el objeto de nivel superior de Aspose.Tasks que representa un archivo de Microsoft Project en memoria. Instanciarla te brinda un proyecto en blanco que puedes poblar con tareas, recursos y calendarios.

```java
Project project = new Project();
```
Aquí instanciamos un nuevo objeto `Project`: representa el archivo MS Project que contendrá nuestra lista de tareas.

## Paso 2: agregar una tarea al proyecto
La clase `Task` representa un elemento de trabajo individual en el cronograma del proyecto. Cada `Task` puede tener su propia duración, fecha de inicio y asignaciones de recursos.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
Usando `getRootTask()` accedemos a la raíz de la jerarquía del proyecto y **agregamos una tarea a Microsoft Project**. La cadena `"Task"` es el nombre de la tarea; puedes reemplazarla con cualquier descripción que necesites.

## Paso 3: establecer línea base para tareas especificadas
`BaselineType` es una enumeración que define qué ranura de línea base (Baseline, Baseline1 … Baseline10) deseas escribir. Al pasar una lista de tareas puedes establecer línea base solo en los elementos que selecciones.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Para **establecer una línea base sin MS Project**, crea una lista con las tareas que deseas baselinar (aquí `myList`) y pásala a `setBaseline`. Rellena `myList` con las tareas que agregaste si solo necesitas una línea base selectiva.

## Paso 4: establecer línea base para todo el proyecto
`setBaseline` escribe los valores de línea base seleccionados en cada tarea del proyecto.  
Si prefieres baselinar todo el proyecto en una sola llamada, simplemente invoca `setBaseline` con el `BaselineType` deseado.

```java
project.setBaseline(BaselineType.Baseline);
```
Esta llamada escribe los valores de línea base elegidos para **cada tarea** del proyecto, garantizando una instantánea completa del cronograma original.

## Cómo agregar una tarea a Microsoft Project usando Aspose.Tasks
`add()` crea una nueva tarea hija bajo la tarea padre especificada y devuelve el objeto `Task` recién creado.  
Agregas una tarea llamando a `add()` sobre un objeto `Task` padre (usualmente la tarea raíz). El método devuelve una nueva instancia de `Task` que puedes configurar más—duración, fecha de inicio, recursos o campos personalizados—antes de guardar el archivo del proyecto.

## Cómo establecer una línea base sin MS Project
Aspose.Tasks permite crear líneas base completamente mediante código. Elige un `BaselineType` (p. ej., `BaselineType.Baseline`) e invoca `setBaseline`. Puedes repetir esto con `Baseline1`‑`Baseline10` para mantener múltiples líneas base de revisión, todo sin abrir Microsoft Project.

## Problemas comunes y soluciones
- **La línea base no aparece:** Asegúrate de llamar a `project.save("output.mpp")` después de establecer la línea base (paso de guardado omitido aquí por brevedad).  
- **La lista de tareas aparece vacía:** Verifica que estés agregando tareas al padre correcto (`getRootTask()` o una subtarea).  
- **Errores de incompatibilidad de versiones:** Usa el JAR más reciente de Aspose.Tasks para garantizar compatibilidad con los formatos .mpp más nuevos.

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Tasks para Java sin Microsoft Project instalado?**  
A: Sí, Aspose.Tasks funciona de forma independiente y no requiere Microsoft Project en la máquina host.

**Q: ¿Aspose.Tasks para Java es compatible con diferentes versiones de Microsoft Project?**  
A: Absolutamente. La biblioteca soporta archivos de Project desde 2007 hasta las versiones más recientes de 2024.

**Q: ¿Puedo manipular recursos del proyecto usando Aspose.Tasks para Java?**  
A: Sí, puedes agregar, actualizar y eliminar recursos programáticamente, al igual que las tareas.

**Q: ¿Aspose.Tasks para Java admite la configuración de dependencias entre tareas?**  
A: Sí, puedes definir relaciones predecesor‑sucesor usando la clase `TaskLink`.

**Q: ¿Existe soporte técnico disponible para Aspose.Tasks para Java?**  
A: Sí, puedes obtener ayuda a través del [support forum](https://forum.aspose.com/c/tasks/15), donde el personal de Aspose y la comunidad responden a consultas.

## Conclusión
Al seguir estos pasos has aprendido cómo **agregar una tarea al proyecto** en Java, crear una lista de tareas y **establecer una línea base sin MS Project** usando Aspose.Tasks. Este enfoque simplifica la automatización de proyectos, elimina la necesidad de instalaciones de escritorio de Project y te brinda control programático total sobre cada aspecto de tu cronograma.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Tutoriales relacionados

- [Cómo crear un proyecto aspose.tasks – Establecer nuevos atributos de tarea](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Cómo establecer la duración de la línea base en Aspose.Tasks para Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Crear tareas Aspose Java – Propiedades de la tarea](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}