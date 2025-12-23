---
date: 2025-12-23
description: Aprenda cómo actualizar archivos de MS Project y reprogramar el trabajo
  no completado usando Aspose.Tasks para Java. También vea cómo guardar XML de MS
  Project.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Actualizar MS Project y reprogramar el trabajo con Aspose.Tasks
url: /es/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Actualizar MS Project y Reprogramar Trabajo con Aspose.Tasks

## Introducción
Microsoft Project es una herramienta de gestión de proyectos ampliamente utilizada que ayuda a los equipos a planificar, rastrear y entregar el trabajo a tiempo. Cuando los cronogramas cambian, a menudo necesitas **actualizar MS Project** de forma programática: marcar el trabajo como completado, mover las tareas restantes y mantener la línea base del proyecto precisa. Aspose.Tasks for Java te brinda una API limpia y segura en tipos para hacer exactamente eso sin abrir la interfaz gráfica. En este tutorial verás cómo actualizar un proyecto, marcar el trabajo como finalizado hasta una fecha específica y luego **cómo reprogramar MS Project** el trabajo que aún está pendiente.

## Respuestas rápidas
- **¿Qué significa “update MS Project”?** Marca las tareas como completadas hasta una fecha determinada y escribe los cambios de vuelta al archivo.  
- **¿Puedo reprogramar el trabajo restante automáticamente?** Sí—utiliza `rescheduleUncompletedWorkToStartAfter` para mover las tareas incompletas hacia adelante.  
- **¿Qué formato de archivo se guarda?** Los ejemplos guardan el proyecto como XML (`SaveFileFormat.Xml`).  
- **¿Necesito una licencia para ejecutar el código?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java se requiere?** JDK 8 o superior.

## ¿Qué es “update MS Project” en código?
Actualizar un proyecto significa cambiar programáticamente las fechas, duraciones o porcentajes de finalización de las tareas y persistir esos cambios. Aspose.Tasks expone métodos como `updateProjectWorkAsComplete` que aplican los cambios basándose en una `Date` de referencia que proporcionas.

## ¿Por qué usar Aspose.Tasks for Java para actualizar MS Project?
- **Sin dependencia de UI** – automatiza cambios masivos en muchos archivos.  
- **Alta fidelidad** – la biblioteca conserva todos los datos nativos de Project (recursos, calendarios, campos personalizados).  
- **Multiplataforma** – ejecuta el mismo código en Windows, Linux o macOS.  
- **Guardar MS Project XML** – puedes exportar el proyecto actualizado al formato XML ampliamente soportado para herramientas posteriores.

## Requisitos previos
1. Java Development Kit (JDK) instalado.  
2. Biblioteca Aspose.Tasks for Java – descárgala desde [here](https://releases.aspose.com/tasks/java/).  
3. Familiaridad básica con la sintaxis de Java y conceptos de programación orientada a objetos.

## Importar paquetes
Primero, importa las clases necesarias de Aspose.Tasks y las utilidades de Java:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Paso 1: Configurar el proyecto
Crea una nueva instancia de `Project`, define algunas tareas de ejemplo, establece sus duraciones y crea dependencias. Luego persiste el estado inicial para que puedas ver el efecto antes y después.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Paso 2: Actualizar el trabajo del proyecto
Marca el trabajo como completado hasta una fecha límite específica. Este es el núcleo de **update MS Project**—la API ajustará automáticamente el progreso y las fechas de las tareas.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Paso 3: Reprogramar el trabajo no completado
Después de marcar el trabajo completado, a menudo necesitas mover las tareas restantes hacia adelante. La siguiente llamada desplaza cualquier trabajo sin terminar para que comience después de la misma fecha límite, efectivamente **cómo reprogramar MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| Las tareas no muestran fechas actualizadas | El proyecto se guardó en un formato diferente (p. ej., `.mpp`) | Usa `SaveFileFormat.Xml` para mantener intacta la estructura XML. |
| `updateProjectWorkAsComplete` parece no hacer nada | La fecha de referencia es anterior al inicio del proyecto | Asegúrate de que la fecha del `Calendar` esté dentro del cronograma del proyecto. |
| Las tareas reprogramadas se superponen | No se aplicó nivelación de calendario o recursos | Aplica un calendario de `Project` o usa `Task.setStart` manualmente después de la reprogramación. |

## Preguntas frecuentes (extendidas)

**Q: ¿Puede Aspose.Tasks for Java manejar estructuras de proyecto complejas?**  
A: Sí, Aspose.Tasks for Java proporciona APIs robustas para gestionar tareas, dependencias, recursos y otros elementos del proyecto de manera eficiente.

**Q: ¿Existe una versión de prueba disponible para Aspose.Tasks for Java?**  
A: Sí, puedes obtener una prueba gratuita desde [here](https://releases.aspose.com/).

**Q: ¿Cómo puedo obtener soporte para Aspose.Tasks for Java?**  
A: Puedes visitar el [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para cualquier asistencia o consulta.

**Q: ¿Puedo comprar una licencia temporal para Aspose.Tasks for Java?**  
A: Sí, las licencias temporales están disponibles para su compra [here](https://purchase.aspose.com/temporary-license/).

**Q: ¿Dónde puedo encontrar documentación detallada para Aspose.Tasks for Java?**  
A: Puedes consultar la documentación [here](https://reference.aspose.com/tasks/java/) para guías completas y referencias de la API.

## Conclusión
En este tutorial recorrimos el proceso completo de **actualizar MS Project** archivos, marcar el trabajo como completado y luego **cómo reprogramar MS Project** las tareas que permanecen sin terminar. Al guardar el proyecto como XML mantienes la compatibilidad con otras herramientas y conservas un registro claro de los cambios. Usa estos patrones para automatizar ajustes de cronograma en grandes carteras, integrarlos con pipelines CI o crear paneles de informes personalizados.

---

**Última actualización:** 2025-12-23  
**Probado con:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}