---
title: WBS asociado con la tarea en Aspose.Tasks
linktitle: WBS asociado con la tarea en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Domine la WBS con Aspose.Tasks para Java aprenda a leer y renumerar códigos WBS de tareas. ¡Impulse la eficiencia de la gestión de proyectos!
type: docs
weight: 36
url: /es/java/task-properties/wbs-associated-with-task/
---
## Introducción
¡Bienvenido al mundo de la gestión de proyectos con Aspose.Tasks para Java! En este tutorial, profundizaremos en las complejidades de la estructura de desglose del trabajo (WBS) asociada con las tareas que utilizan Aspose.Tasks para Java. Ya sea que sea un desarrollador experimentado o recién esté comenzando, esta guía lo ayudará a explorar los aspectos esenciales para administrar códigos WBS de manera eficiente.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Kit de desarrollo de Java (JDK) instalado en su máquina.
-  Biblioteca Aspose.Tasks para Java descargada y agregada a su proyecto. Puedes obtenerlo de[aquí](https://releases.aspose.com/tasks/java/).
## Importar paquetes
Asegúrese de importar los paquetes necesarios para iniciar su proyecto:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## Leer códigos WBS
Comencemos leyendo los códigos WBS asociados con las tareas. Sigue estos pasos:
## Paso 1: cargar el proyecto
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Paso 2: recopilar tareas
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Paso 3: analizar y personalizar
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Este fragmento lee y personaliza los códigos WBS asociados con las tareas de su proyecto.
## Renumerar códigos WBS de tareas
Ahora, exploremos la renumeración de códigos WBS para tareas:
## Paso 1: cargar el proyecto
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Paso 2: seleccione todas las tareas
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Paso 3: generar códigos WBS iniciales
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Paso 4: Renumerar los códigos WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Paso 5: generar códigos WBS actualizados
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Si sigue estos pasos, volverá a numerar de manera efectiva los códigos WBS para las tareas de su proyecto.
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo trabajar con códigos WBS utilizando Aspose.Tasks para Java. Este conocimiento le permitirá gestionar y personalizar de manera eficiente la jerarquía de tareas de su proyecto.
## Preguntas frecuentes
### P: ¿Dónde puedo encontrar la documentación de Aspose.Tasks para Java?
 R: La documentación está disponible.[aquí](https://reference.aspose.com/tasks/java/).
### P: ¿Cómo puedo descargar Aspose.Tasks para Java?
 R: Puedes descargarlo[aquí](https://releases.aspose.com/tasks/java/).
### P: ¿Hay una prueba gratuita disponible para Aspose.Tasks para Java?
 R: Sí, puedes obtener una prueba gratuita[aquí](https://releases.aspose.com/).
### P: ¿Dónde puedo obtener soporte para Aspose.Tasks para Java?
 R: Visita el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para soporte.
### P: ¿Puedo obtener una licencia temporal de Aspose.Tasks para Java?
 R: Sí, obtenga una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).