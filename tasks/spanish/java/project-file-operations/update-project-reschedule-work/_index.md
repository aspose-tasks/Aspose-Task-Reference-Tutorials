---
title: Actualizar y reprogramar MS Project en Aspose.Tasks
linktitle: Actualizar proyecto y reprogramar trabajo incompleto en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a actualizar y reprogramar archivos de MS Project mediante programación utilizando Aspose.Tasks para Java.
weight: 23
url: /es/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Actualizar y reprogramar MS Project en Aspose.Tasks

## Introducción
Microsoft Project es un software de gestión de proyectos ampliamente utilizado que permite a los usuarios gestionar tareas, recursos y cronogramas de manera eficiente. Aspose.Tasks para Java proporciona un potente conjunto de API para manipular archivos de Microsoft Project mediante programación. En este tutorial, aprenderemos cómo actualizar archivos de MS Project y reprogramar el trabajo no completado usando Aspose.Tasks para Java.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Kit de desarrollo de Java (JDK) instalado en su sistema.
2.  Aspose.Tasks para la biblioteca Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/java/).
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
## Paso 1: configurar el proyecto
Inicialice un nuevo objeto de proyecto y defina tareas dentro de él junto con sus duraciones y dependencias.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Definir tareas y sus duraciones.
// ...
// Definir dependencias de tareas
// ...
// Guardar el estado inicial del proyecto
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Paso 2: actualizar el trabajo del proyecto
Actualice el trabajo del proyecto para marcarlo como completo hasta una fecha determinada.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Guarde el proyecto actualizado
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Paso 3: reprogramar el trabajo incompleto
Reprograme cualquier trabajo incompleto para que comience después de una fecha específica.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Guarde el proyecto reprogramado
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Conclusión
En este tutorial, aprendimos cómo actualizar archivos de MS Project y reprogramar el trabajo no completado usando Aspose.Tasks para Java. Esto puede ser particularmente útil en escenarios donde los cronogramas del proyecto necesitan ajustarse en función del progreso o el cambio de prioridades.

## Preguntas frecuentes
### P: ¿Puede Aspose.Tasks para Java manejar estructuras de proyectos complejas?
R: Sí, Aspose.Tasks para Java proporciona API sólidas para administrar tareas, dependencias, recursos y otros elementos del proyecto de manera eficiente.
### P: ¿Existe una versión de prueba disponible de Aspose.Tasks para Java?
 R: Sí, puedes obtener una prueba gratuita desde[aquí](https://releases.aspose.com/).
### P: ¿Cómo puedo obtener soporte para Aspose.Tasks para Java?
 R: Puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para cualquier ayuda o consulta.
### P: ¿Puedo comprar una licencia temporal de Aspose.Tasks para Java?
 R: Sí, se pueden comprar licencias temporales[aquí](https://purchase.aspose.com/temporary-license/).
### P: ¿Dónde puedo encontrar documentación detallada sobre Aspose.Tasks para Java?
 R: Puede consultar la documentación.[aquí](https://reference.aspose.com/tasks/java/) para guías completas y referencias de API.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
