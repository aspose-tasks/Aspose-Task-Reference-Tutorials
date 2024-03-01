---
title: Dominar el recuento de escala de tiempo de MS Project en Aspose.Tasks
linktitle: Establecer el recuento de escala de tiempo en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a gestionar eficazmente el recuento de escalas de tiempo en MS Project utilizando Aspose.Tasks para Java. Optimice la visualización y gestión de proyectos sin esfuerzo.
type: docs
weight: 22
url: /es/java/project-file-operations/set-time-scale-count/
---
## Introducción
La gestión del recuento de la escala de tiempo en MS Project puede afectar significativamente la visualización y gestión del proyecto. Con Aspose.Tasks para Java, una potente API para manejar tareas de gestión de proyectos mediante programación, puede manipular eficientemente el recuento de la escala de tiempo para adaptar las vistas del proyecto a sus necesidades específicas.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente en su lugar:
1. Entorno de desarrollo de Java: asegúrese de tener el kit de desarrollo de Java (JDK) instalado en su sistema.
2.  Biblioteca Aspose.Tasks para Java: descargue e instale la biblioteca Aspose.Tasks para Java. Puedes obtenerlo de[aquí](https://releases.aspose.com/tasks/java/).
3. Conocimientos básicos de programación Java: será beneficiosa la familiaridad con el lenguaje de programación Java.

## Importar paquetes
Importe los paquetes necesarios a su proyecto Java:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Paso 1: configurar el directorio de datos
Defina la ruta al directorio de datos donde se almacenarán los archivos de su proyecto:
```java
String dataDir = "Your Data Directory";
```
 Reemplazar`"Your Data Directory"` con la ruta a su directorio de datos.
## Paso 2: crear una instancia de proyecto
 Crear una instancia nueva`Project` objeto:
```java
Project project = new Project();
```
Esto crea un nuevo objeto de proyecto.
## Paso 3: configurar la vista del diagrama de Gantt
 Crear un`GanttChartView` objeto para configurar la vista del diagrama de Gantt:
```java
GanttChartView view = new GanttChartView();
```
## Paso 4: Establecer el recuento de escala de tiempo para el nivel inferior
Establezca el recuento y la visibilidad de ticks para el nivel de escala de tiempo inferior:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Esto especifica el recuento de intervalos y si se muestran ticks para el nivel inferior.
## Paso 5: Establecer el recuento de escala de tiempo para el nivel medio
De manera similar, configure el nivel de escala de tiempo medio:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Paso 6: agregar vista al proyecto
Agregue la vista configurada al proyecto:
```java
project.getViews().add(view);
```
Esto agrega la vista personalizada al proyecto.
## Paso 7: agregar datos de prueba al proyecto
Agregue algunos datos de prueba al proyecto para demostración:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Esto crea dos tareas con duraciones específicas.
## Paso 8: guarde el proyecto como PDF
Guarde el proyecto como un archivo PDF:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Esto guarda el proyecto con las configuraciones aplicadas en un archivo PDF.

## Conclusión
La gestión eficaz del recuento de la escala de tiempo en MS Project utilizando Aspose.Tasks para Java le permite personalizar las vistas del proyecto para una mejor visualización y gestión.
## Preguntas frecuentes
### P: ¿Puede Aspose.Tasks para Java manejar archivos de proyectos de gran escala?
R: Sí, Aspose.Tasks para Java es capaz de manejar archivos de proyectos a gran escala de manera eficiente.
### P: ¿Aspose.Tasks para Java es compatible con diferentes IDE de Java?
R: Sí, Aspose.Tasks para Java funciona perfectamente con entornos de desarrollo integrados (IDE) de Java populares, como Eclipse e IntelliJ IDEA.
### P: ¿Puedo personalizar la apariencia de los diagramas de Gantt usando Aspose.Tasks para Java?
R: Por supuesto, Aspose.Tasks para Java proporciona amplias capacidades para personalizar la apariencia de los diagramas de Gantt según sus requisitos.
### P: ¿Existe una versión de prueba disponible de Aspose.Tasks para Java?
 R: Sí, puedes obtener una versión de prueba gratuita en[aquí](https://releases.aspose.com/).
### P: ¿Dónde puedo obtener soporte para Aspose.Tasks para Java?
 R: Puede encontrar soporte y asistencia en el foro Aspose.Tasks[aquí](https://forum.aspose.com/c/tasks/15).