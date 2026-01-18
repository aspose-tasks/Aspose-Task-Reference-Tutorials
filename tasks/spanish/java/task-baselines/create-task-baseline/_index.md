---
date: 2026-01-18
description: Aprenda cómo crear una lista de tareas en Java y agregar tareas a Microsoft
  Project, estableciendo una línea base sin MS Project usando Aspose.Tasks.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Crear lista de tareas Java – Línea base de MS Project usando Aspose.Tasks
url: /es/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear lista de tareas Java – Línea base de MS Project con Aspose.Tasks

## Introducción
En este tutorial, **create task list Java** generando una línea base de tareas de Microsoft Project usando Aspose.Tasks para Java. Aspose.Tasks te permite trabajar con archivos de Project sin tener Microsoft Project instalado, de modo que puedes **add task to Microsoft Project**, manipular recursos e incluso **set baseline without MS Project**—todo desde código Java puro.

## Respuestas rápidas
- **¿Qué hace Aspose.Tasks?** Proporciona una API Java para crear, leer y editar archivos de Microsoft Project sin necesidad de MS Project.  
- **¿Necesito tener Microsoft Project instalado?** No, Aspose.Tasks funciona de forma independiente.  
- **¿Qué versión de Java se requiere?** JDK 8 o superior.  
- **¿Puedo establecer una línea base para una sola tarea?** Sí, usa `setBaseline` con una lista de tareas.  
- **¿Se necesita una licencia para producción?** Sí, una licencia comercial elimina los límites de evaluación.

## ¿Qué es una línea base de tarea?
Una línea base de tarea registra los valores originales planificados de inicio, fin y trabajo para una tarea. Sirve como punto de referencia para comparar el progreso real con el plan original.

## ¿Por qué usar Aspose.Tasks para crear task list Java?
- **Sin dependencia de MS Project** – ideal para automatización del lado del servidor.  
- **Control total** sobre tareas, recursos y calendarios mediante código Java.  
- **Compatibilidad entre versiones** con archivos Project 2007‑2024.

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

## Paso 1: Crear un objeto Project
```java
Project project = new Project();
```
Aquí instanciamos un nuevo objeto `Project` – representa el archivo MS Project que contendrá nuestra lista de tareas.

## Paso 2: Añadir una tarea al proyecto
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Usando `getRootTask()` accedemos a la raíz de la jerarquía del proyecto y **add task to Microsoft Project**. La cadena `"Task"` es el nombre de la tarea; puedes reemplazarla con cualquier descripción que necesites.

## Paso 3: Establecer línea base para tareas especificadas
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Para **set baseline without MS Project**, crea una lista con las tareas que deseas incluir en la línea base (aquí `myList`) y pásala a `setBaseline`. Rellena `myList` con las tareas que agregaste si solo necesitas una línea base selectiva.

## Paso 4: Establecer línea base para todo el proyecto
```java
project.setBaseline(BaselineType.Baseline);
```
Si prefieres establecer la línea base de todo el proyecto en una sola llamada, simplemente invoca `setBaseline` con el `BaselineType` deseado.

## Cómo añadir tarea a Microsoft Project usando Aspose.Tasks
Más allá de la tarea única mostrada arriba, puedes añadir múltiples tareas, subtareas y asignar recursos. Cada llamada a `add()` devuelve un objeto `Task` que puedes configurar adicionalmente (duración, fecha de inicio, etc.).

## Cómo establecer línea base sin MS Project
Aspose.Tasks permite crear líneas base completamente mediante código. Puedes establecer diferentes tipos de línea base (Baseline, Baseline1‑Baseline10) cambiando el enumerado `BaselineType`, lo que te permite rastrear múltiples revisiones sin abrir nunca MS Project.

## Problemas comunes y soluciones
- **Línea base no aparece:** Asegúrate de llamar a `project.save("output.mpp")` después de establecer la línea base (paso de guardado omitido aquí por brevedad).  
- **La lista de tareas aparece vacía:** Verifica que estés añadiendo tareas al padre correcto (`getRootTask()` o una subtarea).  
- **Errores por incompatibilidad de versiones:** Usa el JAR más reciente de Aspose.Tasks para garantizar compatibilidad con los formatos .mpp más nuevos.

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Tasks para Java sin Microsoft Project instalado?**  
R: Sí, Aspose.Tasks funciona de forma independiente y no requiere Microsoft Project en la máquina host.

**P: ¿Aspose.Tasks para Java es compatible con diferentes versiones de Microsoft Project?**  
R: Absolutamente. La biblioteca soporta archivos Project desde 2007 hasta las últimas versiones de 2024.

**P: ¿Puedo manipular los recursos del proyecto usando Aspose.Tasks para Java?**  
R: Sí, puedes añadir, actualizar y eliminar recursos programáticamente, al igual que las tareas.

**P: ¿Aspose.Tasks para Java permite establecer dependencias entre tareas?**  
R: Sí, puedes definir relaciones predecesor‑sucesor usando la clase `TaskLink`.

**P: ¿Existe soporte técnico disponible para Aspose.Tasks para Java?**  
R: Sí, puedes obtener ayuda a través del [support forum](https://forum.aspose.com/c/tasks/15), donde el personal de Aspose y la comunidad responden a las consultas.

## Conclusión
Al seguir estos pasos, has aprendido cómo **create task list Java**, **add task to Microsoft Project** y **set baseline without MS Project** usando Aspose.Tasks. Este enfoque simplifica la automatización de proyectos, elimina la necesidad de instalaciones de escritorio de Project y te brinda control programático completo sobre los datos de tu proyecto.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-01-18  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

---