---
title: Configurar la vista del diagrama de Gantt en proyectos de Aspose.Tasks
linktitle: Configurar la vista del diagrama de Gantt en proyectos de Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a configurar la vista de gráfico del proyecto Gantt MS en Aspose.Tasks usando Java. Personalice el proyecto y visualícelo en el diagrama de Gantt paso a paso.
type: docs
weight: 10
url: /es/java/project-configuration/configure-gantt-chart/
---
## Introducción
En este tutorial, aprenderá cómo configurar la vista de gráfico del proyecto Gantt MS en proyectos Aspose.Tasks usando Java. Aspose.Tasks es una potente API de Java que le permite trabajar con archivos de Microsoft Project mediante programación. Si sigue estos pasos, podrá personalizar la vista del diagrama de Gantt según los requisitos de su proyecto.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK): asegúrese de tener Java instalado en su sistema.
2.  Biblioteca Aspose.Tasks: descargue e instale la biblioteca Aspose.Tasks. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/java/).
3. Entorno de desarrollo integrado (IDE): elija un IDE de su elección. Este tutorial utiliza IntelliJ IDEA, pero puede utilizar cualquier IDE con el que se sienta cómodo.
## Importar paquetes
Primero, necesita importar los paquetes necesarios para trabajar con Aspose.Tasks en su proyecto Java. Agregue las siguientes declaraciones de importación a su archivo Java:
```java
import com.aspose.tasks.*;
```
Ahora, analicemos el proceso de configuración de la vista del gráfico del proyecto Gantt MS en instrucciones paso a paso:
## Paso 1: configurar el directorio de datos
```java
String dataDir = "Your Data Directory";
```
 Reemplazar`"Your Data Directory"` con la ruta al directorio de datos de su proyecto.
## Paso 2: cargar el archivo del proyecto
```java
Project project = new Project(dataDir + "project.mpp");
```
Cargue el archivo de su proyecto (`project.mpp` en este ejemplo) usando el`Project` clase de Aspose.Tasks.
## Paso 3: agregar nueva actividad
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 Cree una nueva tarea en su proyecto usando el`Task` class y agréguela a los hijos de la tarea raíz.
## Paso 4: definir el atributo personalizado
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 Defina un nuevo atributo personalizado utilizando el`ExtendedAttributeDefinition`class y agréguela a los atributos extendidos del proyecto.
## Paso 5: agregar un atributo personalizado a la tarea
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Agregue el atributo personalizado a la tarea creada usando el`createExtendedAttribute` método.
## Paso 6: personalizar la tabla
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
Personalice la tabla agregando el campo de atributo de texto con el ancho, título y alineación especificados.
## Paso 7: guardar proyecto
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Guarde el proyecto con la vista de gráfico de proyecto de Gantt MS configurada. El archivo resultante se puede abrir en Microsoft Project 2010.
## Conclusión
¡Felicidades! Ha configurado correctamente la vista de gráfico del proyecto Gantt MS en proyectos Aspose.Tasks usando Java. Ahora puede personalizar los atributos del proyecto y visualizarlos en el diagrama de Gantt según las necesidades de su proyecto.
## Preguntas frecuentes
### P: ¿Puedo utilizar Aspose.Tasks con otros lenguajes de programación?
R: Sí, Aspose.Tasks está disponible para múltiples lenguajes de programación, incluidos .NET, Java y C.++.
### P: ¿Hay alguna prueba gratuita disponible para Aspose.Tasks?
 R: Sí, puedes descargar una prueba gratuita desde[aquí](https://releases.aspose.com/).
### P: ¿Dónde puedo encontrar soporte para Aspose.Tasks?
R: Puede encontrar soporte y hacer preguntas en el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### P: ¿Cómo puedo comprar una licencia para Aspose.Tasks?
 R: Puede comprar una licencia en[aquí](https://purchase.aspose.com/buy).
### P: ¿Necesito una licencia temporal para realizar pruebas?
 R: Sí, puede obtener una licencia temporal de[aquí](https://purchase.aspose.com/temporary-license/).