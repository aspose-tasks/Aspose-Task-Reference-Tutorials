---
date: 2026-08-29
description: Aprenda cómo establecer link types y gestionar task dependencies con
  Aspose.Tasks for Java en un tutorial step‑by‑step.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Cómo establecer link types en Aspose.Tasks for Java
og_description: Aprenda cómo establecer link types y gestionar task dependencies con
  Aspose.Tasks for Java. Guía step‑by‑step para desarrolladores.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Cómo establecer link types en Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Cómo establecer link types en Aspose.Tasks for Java
url: /es/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer tipos de enlace en Aspose.Tasks para Java

## Introducción
Si te preguntas **cómo establecer un enlace** entre tareas mientras *gestionas dependencias de tareas* en un proyecto, has llegado al lugar correcto. En este tutorial recorreremos la creación de un nuevo proyecto, la adición de tareas y la definición del tipo de enlace (Start‑to‑Start, Finish‑to‑Start, etc.) usando Aspose.Tasks para Java. Al final te sentirás seguro personalizando las relaciones de tareas para que coincidan con las necesidades de programación del mundo real y verás cómo la API maneja planes a gran escala con hasta 10,000 tareas.

## Respuestas rápidas
- **¿Qué clase representa una dependencia?** `TaskLink` es el objeto central que modela un enlace entre dos tareas.  
- **¿Qué enum define el tipo de relación?** `TaskLinkType` (p. ej., `StartToStart`, `FinishToStart`).  
- **¿Puedo leer los tipos de enlace existentes?** Sí – itera `Project.getTaskLinks()` y llama a `getLinkType()`.  
- **¿Necesito una licencia para este código?** Una licencia temporal funciona para pruebas; se requiere una licencia completa para producción.  
- **¿Es compatible con Java 8+?** Absolutamente – Aspose.Tasks soporta Java 8 hasta Java 21, cubriendo 13 versiones principales.

## Qué es un enlace de tarea
Un **enlace de tarea** modela una dependencia entre dos tareas en el cronograma de un proyecto.  
Puedes crear, modificar o eliminar un `TaskLink` para reflejar relaciones predecesor‑sucesor, permitiendo que el planificador calcule automáticamente las fechas de inicio y fin.

## Por qué usar los tipos de enlace de Aspose.Tasks
Aspose.Tasks soporta **30+ formatos de entrada y salida** y puede procesar proyectos que contienen **hasta 10,000 tareas** sin cargar todo el archivo en memoria. Esta capacidad cuantificada garantiza un rendimiento rápido incluso para planes a escala empresarial, y la biblioteca conserva todas las características de Microsoft Project como campos personalizados y asignaciones de recursos.

## Requisitos previos
- **Entorno de desarrollo Java** – JDK 8 o superior instalado y configurado.  
- **Biblioteca Aspose.Tasks** – Descarga el último JAR desde el [download link](https://releases.aspose.com/tasks/java/).  
- **Directorio de documentos** – Crea una carpeta en tu máquina donde guardarás los archivos de proyecto de ejemplo.

## Importar paquetes
Comenzamos importando las clases esenciales de Aspose.Tasks. Esto prepara el IDE para reconocer las llamadas a la API que usaremos más adelante.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## ¿Cómo establecer tipos de enlace en Aspose.Tasks para Java?
Carga una nueva instancia de `Project`, agrega dos tareas y luego crea un `TaskLink` con el `TaskLinkType` deseado. Este patrón de dos pasos te permite definir cualquiera de los cuatro tipos estándar de dependencia en una sola llamada. `Project` representa todo el archivo del proyecto y su cronograma. `Task` es un elemento de trabajo individual dentro del proyecto. `TaskLink` conecta una tarea predecesora con una tarea sucesora. `TaskLinkType` es una enumeración que especifica la relación (Start‑to‑Start, Finish‑to‑Start, etc.).

### Paso 1: establecer un tipo de enlace
`TaskLink` representa una dependencia entre dos tareas, mientras que `TaskLinkType` enumera los posibles tipos de relación como `StartToStart`. En este paso creamos un proyecto nuevo, agregamos dos tareas y las vinculamos usando la relación **Start‑to‑Start**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Consejo profesional:** Puedes reemplazar `StartToStart` con `FinishToStart`, `StartToFinish` o `FinishToFinish` según la dependencia que necesites **gestionar dependencias de tareas**.

### Paso 2: obtener un tipo de enlace
`Project.getTaskLinks()` devuelve una colección de todos los objetos `TaskLink` en el cronograma. Al iterar esta colección puedes leer el `TaskLinkType` de cada enlace y verificar que la relación correcta se haya guardado.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

La consola mostrará valores como `StartToStart`, `FinishToStart`, etc., confirmando el tipo de enlace que estableciste previamente.

## Problemas comunes y soluciones
- **NullPointerException al agregar enlaces** – Asegúrate de que tanto las tareas predecesoras como las sucesoras se hayan agregado al proyecto antes de crear un `TaskLink`.  
- **Tipo de enlace incorrecto después de guardar** – Siempre llama a `project.save("output.mpp")` (u otro formato compatible) después de establecer el tipo de enlace para persistir los cambios.  
- **Licencia no encontrada** – Coloca tu archivo de licencia Aspose.Tasks en el classpath del proyecto y cárgalo con `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## Preguntas frecuentes

**Q: ¿Es Aspose.Tasks compatible con diferentes entornos Java?**  
A: Sí, Aspose.Tasks se integra con Java SE estándar, Java EE y kits de desarrollo Android sin dependencias adicionales.

**Q: ¿Puedo personalizar los tipos de enlace según los requisitos de mi proyecto?**  
A: Absolutamente. El enum `TaskLinkType` ofrece cuatro tipos estándar, y puedes combinarlos con valores de retraso para modelar horarios complejos.

**Q: ¿Dónde puedo encontrar documentación detallada de Aspose.Tasks para Java?**  
A: Consulta la [documentación de Aspose.Tasks para Java](https://reference.aspose.com/tasks/java/) para obtener guía detallada, referencia de API y ejemplos de código.

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks?**  
A: Visita la [página de licencia temporal](https://purchase.aspose.com/temporary-license/) para adquirir una licencia temporal para propósitos de prueba.

**Q: ¿Dónde puedo obtener soporte para consultas relacionadas con Aspose.Tasks?**  
A: Únete a la comunidad de Aspose.Tasks en el [foro de soporte](https://forum.aspose.com/c/tasks/15) para obtener ayuda y discusiones.

**Q: ¿Puedo cambiar un tipo de enlace después de que el proyecto se haya guardado?**  
A: Sí. Carga el proyecto, recupera el `TaskLink`, llama a `setLinkType()` con el nuevo valor del enum y guarda el proyecto nuevamente.

**Q: ¿Aspose.Tasks soporta la lectura de archivos Microsoft Project (MPP)?**  
A: Sí. Usa `new Project("file.mpp")` para cargar archivos MPP y trabajar con sus enlaces de tarea como en el ejemplo XML anterior.

---

**Última actualización:** 2026-08-29  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear enlace de tarea entre proyectos en Aspose.Tasks](/tasks/java/task-links/create-cross-project-task-link/)
- [Establecer fecha de inicio del proyecto y gestionar tareas padre e hijo en Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Cargar archivo MPP Java - Gestionar propiedades del proyecto con Aspose.Tasks](/tasks/java/project-management/default-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}