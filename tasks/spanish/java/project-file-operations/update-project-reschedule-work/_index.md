---
date: 2026-03-29
description: Aprenda cómo reprogramar el trabajo no completado, actualizar el trabajo
  del proyecto y guardar archivos de MS Project como XML usando Aspose.Tasks para
  Java.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Reprogramar el trabajo no completado y actualizar archivos de MS Project con
  Aspose.Tasks
url: /es/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Reprogramar trabajo no completado y actualizar archivos MS Project con Aspose.Tasks

## Introducción
Microsoft Project es una herramienta de gestión de proyectos ampliamente utilizada que ayuda a los equipos a planificar tareas, asignar recursos y seguir cronogramas. Aspose.Tasks for Java brinda a los desarrolladores una API completa para manipular archivos de Microsoft Project de forma programática. En este tutorial, aprenderá a **actualizar el trabajo del proyecto**, **reprogramar trabajo no completado** y **guardar el archivo MS Project** en formato XML usando Aspose.Tasks for Java.

## Respuestas rápidas
- **¿Qué significa “reprogramar trabajo no completado”?** Mueve cualquier trabajo de tarea restante para que comience después de una fecha elegida, manteniendo intactas las partes completadas.  
- **¿Qué método marca el trabajo como completo?** `project.updateProjectWorkAsComplete(date, false)`.  
- **¿Cómo persisto los cambios?** Use `project.save(<path>, SaveFileFormat.Xml)`.  
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia válida de Aspose.Tasks para uso comercial.  
- **¿Qué versión de Java es compatible?** Java 8 y posteriores son totalmente compatibles.

## ¿Qué es “reprogramar trabajo no completado”?
Reprogramar trabajo no completado ajusta las fechas de inicio de todas las tareas que aún no han finalizado, desplazándolas para que comiencen después de una fecha límite especificada. Esto es útil cuando el cronograma del proyecto cambia debido a retrasos o cambios de alcance.

## ¿Por qué usar Aspose.Tasks para actualizar el trabajo del proyecto y reprogramar tareas?
- **Control granular:** Establezca directamente los porcentajes y fechas de finalización del trabajo.  
- **Sin interfaz de usuario requerida:** Automatice actualizaciones masivas en muchos archivos de proyecto.  
- **Multiplataforma:** Funciona en cualquier sistema que ejecute Java.  
- **Preserva la integridad de los datos:** Todas las dependencias, restricciones y recursos permanecen consistentes.

## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Java Development Kit (JDK) instalado en su sistema.  
2. Biblioteca Aspose.Tasks for Java. Puede descargarla desde [aquí](https://releases.aspose.com/tasks/java/).  
3. Conocimientos básicos del lenguaje de programación Java.

## Importar paquetes
Primero, importe los paquetes necesarios en su código Java:
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
Inicialice un nuevo objeto `Project`, defina tareas, establezca duraciones y cree dependencias. Esto crea el proyecto base que luego actualizaremos y reprogramaremos.
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
Marque el trabajo como completo hasta una fecha específica. Este paso demuestra la operación **actualizar trabajo del proyecto**, que suele ser la primera acción antes de reprogramar.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Paso 3: Reprogramar trabajo no completado
Ahora desplazamos cualquier trabajo restante (no completado) para que comience después de la misma fecha límite. Esta es la funcionalidad central de **reprogramar trabajo no completado**.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Conclusión
En este tutorial, cubrimos cómo **actualizar el trabajo del proyecto**, **reprogramar trabajo no completado** y **guardar el archivo MS Project** como XML usando Aspose.Tasks for Java. Estas capacidades son esenciales cuando los cronogramas del proyecto deben ajustarse según el progreso real o prioridades comerciales cambiantes.

## Preguntas frecuentes
### Q: ¿Puede Aspose.Tasks for Java manejar estructuras de proyecto complejas?
A: Sí, Aspose.Tasks for Java proporciona APIs robustas para gestionar tareas, dependencias, recursos y otros elementos del proyecto de manera eficiente.  
### Q: ¿Hay una versión de prueba disponible para Aspose.Tasks for Java?
A: Sí, puede obtener una prueba gratuita desde [aquí](https://releases.aspose.com/).  
### Q: ¿Cómo puedo obtener soporte para Aspose.Tasks for Java?
A: Puede visitar el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para cualquier asistencia o consulta.  
### Q: ¿Puedo comprar una licencia temporal para Aspose.Tasks for Java?
A: Sí, las licencias temporales están disponibles para compra [aquí](https://purchase.aspose.com/temporary-license/).  
### Q: ¿Dónde puedo encontrar documentación detallada para Aspose.Tasks for Java?
A: Puede consultar la documentación [aquí](https://reference.aspose.com/tasks/java/) para guías completas y referencias de API.

## Preguntas frecuentes adicionales

**Q: ¿Cómo aseguro que el archivo guardado sea compatible con versiones anteriores de Microsoft Project?**  
A: Guarde el proyecto usando `SaveFileFormat.Xml`; XML es ampliamente compatible con versiones de Project.

**Q: ¿Puedo reprogramar solo un subconjunto de tareas en lugar de todo el proyecto?**  
A: Sí, puede iterar sobre tareas específicas y llamar a `task.setStart(date)` después de calcular la nueva fecha de inicio.

**Q: ¿Qué ocurre con las asignaciones de recursos cuando reprogramo trabajo no completado?**  
A: Las asignaciones de recursos se desplazan automáticamente para coincidir con las nuevas fechas de inicio de las tareas, preservando la lógica de asignación.

**Q: ¿Es posible deshacer una operación de reprogramación programáticamente?**  
A: Puede volver a cargar el archivo de proyecto original (o una copia de seguridad) para revertir cualquier cambio.

**Q: ¿Aspose.Tasks admite guardar en otros formatos como .mpp?**  
A: Absolutamente. Use `SaveFileFormat.MPP` para guardar en el formato nativo de Microsoft Project.

---

**Última actualización:** 2026-03-29  
**Probado con:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}