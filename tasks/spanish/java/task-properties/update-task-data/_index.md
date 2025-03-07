---
title: Actualice los datos de la tarea al formato MPP en Aspose.Tasks
linktitle: Actualice los datos de la tarea al formato MPP en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda cómo actualizar los datos de la tarea al formato MPP usando Aspose.Tasks para Java. Siga nuestra guía paso a paso para una gestión eficiente de proyectos.
weight: 35
url: /es/java/task-properties/update-task-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Actualice los datos de la tarea al formato MPP en Aspose.Tasks

## Introducción
Bienvenido a nuestra guía paso a paso sobre cómo actualizar los datos de las tareas al formato MPP utilizando Aspose.Tasks para Java. En este tutorial, lo guiaremos a través del proceso, asegurándonos de que comprenda cada paso con claridad. Aspose.Tasks para Java proporciona una solución sólida para trabajar con archivos de Microsoft Project y, al final de esta guía, podrá actualizar de manera eficiente los datos de las tareas en formato MPP.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
-  Aspose.Tasks para Java: asegúrese de tener instalada la biblioteca Aspose.Tasks. Puedes descargarlo desde el[página de lanzamiento](https://releases.aspose.com/tasks/java/).
- Kit de desarrollo de Java (JDK): asegúrese de tener Java instalado en su sistema.
- Entorno de desarrollo integrado (IDE): utilice un IDE de su elección para el desarrollo de Java.
## Importar paquetes
Comience importando los paquetes necesarios a su proyecto Java. El siguiente fragmento demuestra cómo importar paquetes:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. Cree y configure la tarea inicial
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Continúa con el resto del código)
```
## 2. Establecer fecha de inicio y duración
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Continúa con el resto del código)
```
## 3. Cree una tarea de resumen
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Continúa con el resto del código)
```
## 4. Establecer fechas límite y notas de tareas
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Continúa con el resto del código)
```
## 5. Configurar restricciones de tareas
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Continúa con el resto del código)
```
## 6. Cree tareas adicionales
```java
//Crea 10 nuevas tareas
for (int i = 0; i < 10; i++) {
    //... (Continúa con el resto del código)
}
//... (Continúa con el resto del código)
```
## 7. Guarde el proyecto
```java
// Guardar el proyecto
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Si sigue estos pasos, habrá actualizado correctamente los datos de la tarea al formato MPP utilizando Aspose.Tasks para Java.
## Conclusión
¡Felicidades! Ha completado una guía completa sobre cómo actualizar los datos de las tareas en formato MPP utilizando Aspose.Tasks para Java. Esta potente biblioteca simplifica las tareas de gestión de proyectos, lo que la convierte en una herramienta valiosa para los desarrolladores de Java.
## Preguntas frecuentes
### P: ¿Dónde puedo encontrar la documentación de Aspose.Tasks para Java?
 R: La documentación está disponible.[aquí](https://reference.aspose.com/tasks/java/).
### P: ¿Cómo puedo descargar Aspose.Tasks para Java?
 R: Puedes descargarlo desde[página de lanzamiento](https://releases.aspose.com/tasks/java/).
### P: ¿Hay una prueba gratuita disponible?
 R: Sí, puedes acceder a la prueba gratuita.[aquí](https://releases.aspose.com/).
### P: ¿Dónde puedo obtener soporte para Aspose.Tasks para Java?
 R: Visita el foro de soporte[aquí](https://forum.aspose.com/c/tasks/15).
### P: ¿Ofrecen licencias temporales para fines de prueba?
 R: Sí, puedes obtener una licencia temporal.[aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
