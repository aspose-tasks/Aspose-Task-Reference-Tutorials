---
date: 2026-09-09
description: Aprenda cómo identificar tareas entre proyectos usando Aspose.Tasks para
  Java. Explore una integración fluida, una gestión eficiente y ejemplos del mundo
  real.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Identificar tareas entre proyectos en Aspose.Tasks
og_description: Identificar tareas entre proyectos en Aspose.Tasks para Java. Aprenda
  cómo establecer el directorio de documentos, recuperar IDs de tareas y gestionar
  proyectos vinculados de manera eficiente.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Identificar tareas entre proyectos en Aspose.Tasks – Guía Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Identificar tareas entre proyectos en Aspose.Tasks
url: /es/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Identificar tareas entre proyectos en Aspose.Tasks

## Introducción
En este tutorial aprenderá **cómo identificar tareas entre proyectos** con Aspose.Tasks para Java. Ya sea que mantenga una cartera de cronogramas interdependientes o necesite auditar dependencias externas, los pasos a continuación le muestran cómo localizar tareas que hacen referencia a otros archivos de proyecto, obtener sus identificadores y trabajar con ellas programáticamente.

## Respuestas rápidas
- **¿Qué significa “identificar tareas entre proyectos”?** Significa localizar tareas que hacen referencia o dependen de tareas en otro archivo de proyecto.  
- **¿Qué método imprime el ID de la tarea?** Use `externalTask.get(Tsk.ID)` para imprimir el ID de la tarea.  
- **¿Cómo establezco el directorio del documento?** Asigne la ruta de la carpeta a una variable `String` (p. ej., `dataDir`).  
- **¿Qué propiedad recupera una tarea por UID?** Llame a `getChildren().getByUid(yourUid)`.  
- **¿Necesito una licencia para uso en producción?** Sí, se requiere una licencia válida de Aspose.Tasks para implementaciones comerciales.

## ¿Qué es “identificar tareas entre proyectos”?
Identificar tareas entre proyectos le permite rastrear relaciones entre tareas distribuidas en varios archivos de Microsoft Project. Al localizar tareas que hacen referencia o dependen de cronogramas externos, puede comprender cómo los elementos de trabajo interactúan a través de los límites de los proyectos, evitar esfuerzos duplicados y mantener cronogramas precisos. Esta capacidad es esencial para carteras a gran escala donde las tareas se comparten o dependen de cronogramas externos.

## ¿Por qué usar Aspose.Tasks para Java?
Aspose.Tasks para Java admite **más de 50 formatos de entrada y salida** (incluidos MPP, MPX, XML y CSV) y puede procesar proyectos con **hasta 10 000 tareas** sin cargar todo el archivo en memoria. La biblioteca funciona en cualquier plataforma compatible con JVM, no requiere instalación de Microsoft Project y ofrece acceso completo a la API a IDs, UIDs, IDs externos y metadatos de enlace.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

- Un entorno de desarrollo Java funcional (JDK 8 o superior).  
- Aspose.Tasks para Java instalado. Puede descargarlo **[aquí](https://releases.aspose.com/tasks/java/)**.  
- Un archivo de licencia válido de Aspose.Tasks si planea ejecutar el código en producción.

## Importar paquetes
La clase `Project` representa un archivo de Microsoft Project, `Task` representa una tarea individual y `Tsk` proporciona constantes de campos de tarea.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Paso 1: establecer el directorio del documento
La cadena `dataDir` contiene la ruta a la carpeta que contiene sus archivos `.mpp`.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Paso 2: cargar proyecto externo
`Project externalProject` carga el archivo de proyecto externo especificado para su inspección.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Paso 3: obtener tarea externa por UID
`externalProject.getChildren().getByUid(uid)` recupera una tarea de la colección de tareas del proyecto externo usando su identificador único.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Paso 4: imprimir ID de la tarea (caso de uso principal)
`externalTask.get(Tsk.ID)` devuelve el ID interno asignado por Aspose.Tasks para la tarea dada.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Paso 5: imprimir ID original (externa) de la tarea
`externalTask.get(Tsk.ExternalID)` obtiene el ID original de la tarea tal como se define en el archivo de proyecto fuente.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Repita los pasos anteriores para cualquier tarea adicional que necesite rastrear entre proyectos.

## Problemas comunes y consejos
- **Errores de ruta** – Asegúrese de que `dataDir` termine con el separador de archivos apropiado (`/` o `\\`).  
- **UID no encontrado** – Verifique que el UID exista en el proyecto externo; use `externalProject.getRootTask().getChildren().size()` para listar los UIDs disponibles.  
- **Excepciones de licencia** – Una licencia faltante o inválida lanzará una excepción de licencia en tiempo de ejecución.  
- **Proyectos grandes** – Para proyectos con más de 5 000 tareas, considere usar `ProjectReader` con la bandera `LoadOptions` para transmitir datos y reducir el consumo de memoria.

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Tasks con otros lenguajes de programación?**  
A: Sí, Aspose.Tasks admite varios lenguajes, incluidos Java, .NET y más.

**Q: ¿Dónde puedo encontrar documentación detallada de Aspose.Tasks para Java?**  
A: Consulte la documentación **[aquí](https://reference.aspose.com/tasks/java/)**.

**Q: ¿Hay una prueba gratuita disponible para Aspose.Tasks para Java?**  
A: Sí, puede obtener una prueba gratuita **[aquí](https://releases.aspose.com/)**.

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks?**  
A: Obtenga una licencia temporal **[aquí](https://purchase.aspose.com/temporary-license/)**.

**Q: ¿Necesita ayuda o tiene preguntas específicas?**  
A: Visite el foro de soporte de Aspose.Tasks **[aquí](https://forum.aspose.com/c/tasks/15)**.

---

**Última actualización:** 2026-09-09  
**Probado con:** Aspose.Tasks para Java 24.11 (última versión al momento de escribir)  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear dependencias de tareas de gestión de proyectos en Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Establecer fecha de inicio del proyecto y gestionar tareas padre e hijo en Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Crear proyecto MPP Java – Cambiar progreso de la tarea con Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}