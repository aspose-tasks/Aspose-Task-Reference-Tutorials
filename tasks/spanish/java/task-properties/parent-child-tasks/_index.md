---
date: 2026-02-23
description: Aprenda a establecer la fecha de inicio del proyecto, fijar la duración
  de la tarea y guardar el proyecto como MPP usando Aspose.Tasks para Java. Administre
  eficientemente las tareas padre e hijo.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Establecer la fecha de inicio del proyecto y gestionar tareas padre e hijo
  en Aspose.Tasks
url: /es/java/task-properties/parent-child-tasks/
weight: 24
---

) support saving as MPP; check the release notes for any breaking changes." -> translate.

Then horizontal line "---"

Then "**Last Updated:** 2026-02-23" keep same.

"**Tested With:** Aspose.Tasks for Java 24.11" keep.

"**Author:** Aspose" keep.

Then closing shortcodes.

Make sure to keep all shortcodes exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer la fecha de inicio del proyecto y gestionar tareas padre e hijo en Aspose.Tasks

## Introducción
La organización eficaz de tareas es la columna vertebral de una gestión de proyectos exitosa, y **setting the project start date** correctamente es el primer paso hacia un cronograma bien estructurado. En este tutorial verás cómo **set project start date**, configurar la duración de las tareas y gestionar relaciones padre‑hijo usando Aspose.Tasks for Java. Al final, estarás listo para **save project as MPP**, actualizar los porcentajes de finalización de tareas y personalizar las propiedades de las tareas para adaptarlas a cualquier escenario del mundo real.

## Respuestas rápidas
- **How do I set the project start date?** Use `proj.set(Prj.START_DATE, startDate);` after initializing the `Project` object.  
- **Can I add child tasks under a parent task?** Yes – call `parentTask.getChildren().add("Child Task")`.  
- **What format does Aspose.Tasks save the file in?** Use `SaveFileFormat.Mpp` to **save project as MPP**.  
- **How do I update task completion?** Set `Tsk.PERCENT_COMPLETE` on the task object.  
- **Where can I obtain a temporary license?** Visit the temporary‑license page linked in the FAQs.

## Requisitos previos
Antes de sumergirte en el tutorial, asegúrate de contar con los siguientes requisitos:
- Comprensión básica de la programación en Java.  
- Biblioteca Aspose.Tasks for Java instalada. Puedes descargarla [here](https://releases.aspose.com/tasks/java/).  
- Un entorno de desarrollo integrado (IDE) para Java configurado en tu sistema.

## Importar paquetes
Para comenzar, importa los paquetes necesarios en tu proyecto Java. Estos paquetes facilitan una integración fluida con las funcionalidades de Aspose.Tasks for Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Paso 1: Establecer la fecha de inicio del proyecto
Comienza estableciendo la fecha de inicio del proyecto y otros parámetros relevantes.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Paso 2: Añadir tarea padre (Task 1)
Crea una tarea padre llamada "Task 1" y configura sus propiedades, incluyendo **set task duration**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Paso 3: Añadir tarea padre (Task 2) con tareas hijo
Ahora, añade otra tarea padre llamada "Task 2" e incluye tareas hijo (Task 3 y Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Paso 4: Configurar tareas hijo
Especifica fechas de inicio, duraciones y restricciones para Task 3 y Task 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Paso 5: Actualizar el porcentaje de finalización de la tarea
Ajusta el porcentaje de finalización para Task 3 y Task 4 – así es como **update task completion**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Paso 6: Guardar el proyecto
Finalmente, **save project as MPP** con los cambios aplicados.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Esta guía paso a paso demuestra cómo gestionar tareas padre e hijo de manera eficaz usando Aspose.Tasks for Java. Experimenta con diferentes configuraciones para adaptarlas a los requisitos de tu proyecto.

## ¿Por qué personalizar las propiedades de la tarea?
Personalizar propiedades de la tarea como fechas de inicio, duraciones, restricciones y porcentajes de finalización te brinda un control granular sobre el comportamiento del cronograma. Ya sea que necesites alinear tareas con la disponibilidad de recursos o imponer reglas de negocio, Aspose.Tasks te permite **customize task properties** programáticamente.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **Start date not applied** | Asegúrate de llamar a `proj.set(Prj.START_DATE, …)` **after** crear el objeto `Project` y antes de añadir tareas. |
| **Child tasks inherit wrong constraints** | Establece explícitamente `ConstraintType` y `ConstraintDate` de cada hijo, como se muestra en el Paso 4. |
| **Saved file cannot be opened in MS Project** | Verifica que estés usando la última versión de Aspose.Tasks y guarda con `SaveFileFormat.Mpp`. |
| **Percentage not reflecting in UI** | Después de establecer `Tsk.PERCENT_COMPLETE`, llama a `proj.calculateTaskSchedule()` si necesitas recalcular las fechas. |

## Preguntas frecuentes
### ¿Aspose.Tasks for Java es compatible con diferentes formatos de archivo de proyecto?
Sí, Aspose.Tasks for Java soporta varios formatos de archivo de proyecto, incluidos MPP y XML.

### ¿Puedo personalizar las propiedades de la tarea más allá de lo cubierto en este tutorial?
¡Absolutamente! Aspose.Tasks for Java ofrece amplias opciones de personalización para las propiedades de las tareas.

### ¿Existe un foro comunitario para Aspose.Tasks donde pueda buscar soporte?
Sí, puedes visitar el [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para obtener soporte de la comunidad.

### ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks for Java?
Puedes obtener una licencia temporal [here](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo encontrar documentación completa para Aspose.Tasks for Java?
La documentación está disponible [here](https://reference.aspose.com/tasks/java/).

**Additional Q&A**

**Q: ¿Cómo puedo obtener programáticamente una licencia temporal?**  
A: Load the temporary license file using `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q: ¿Puedo cambiar la unidad de duración de tarea predeterminada?**  
A: Yes – modify the `TimeUnitType` argument in `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q: ¿Qué versión de Aspose.Tasks se requiere para usar `SaveFileFormat.Mpp`?**  
A: All recent versions (2022‑2026) support saving as MPP; check the release notes for any breaking changes.

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}