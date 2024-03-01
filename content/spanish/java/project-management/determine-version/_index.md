---
title: Determine la versión de MS Project con Aspose.Tasks
linktitle: Determinar la versión del proyecto con Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a determinar la versión de los archivos de MS Project mediante programación utilizando Aspose.Tasks para Java. Guía paso a paso con ejemplos de código.
type: docs
weight: 12
url: /es/java/project-management/determine-version/
---
## Introducción
Este tutorial lo guiará a través del uso de Aspose.Tasks para Java para determinar la versión de un archivo de MS Project paso a paso. Aspose.Tasks es una potente API de Java que permite a los desarrolladores manipular archivos de Microsoft Project sin necesidad de instalar Microsoft Project.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema.
2.  Archivo JAR Aspose.Tasks para Java: descargue la biblioteca Aspose.Tasks para Java desde[sitio web](https://releases.aspose.com/tasks/java/) y agréguelo a su proyecto Java.
3. Archivo de MS Project: prepare un archivo de MS Project (formato XML) para realizar pruebas.

## Importar paquetes
Antes de profundizar en el código, importemos los paquetes necesarios:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Paso 1: configurar el proyecto
```java
// La ruta al directorio de documentos.
String dataDir = "Your Data Directory";
```
 Reemplazar`"Your Data Directory"` con la ruta al directorio que contiene su archivo de MS Project.
## Paso 2: cargar el proyecto
```java
Project project = new Project(dataDir + "input.xml");
```
 Reemplazar`"input.xml"` con el nombre de su archivo de MS Project.
## Paso 3: determinar la versión del proyecto
```java
//Mostrar propiedad de versión del proyecto
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Este fragmento de código recupera e imprime la versión y la fecha del último guardado del archivo de MS Project.
## Paso 4: Mostrar resultado
```java
//Mostrar el resultado de la conversión.
System.out.println("Process completed Successfully");
```
Esta línea indica la finalización del proceso.

## Conclusión
En este tutorial, aprendió cómo determinar la versión de un archivo de MS Project usando Aspose.Tasks para Java. Si sigue la guía paso a paso, podrá trabajar de manera eficiente con archivos de MS Project en sus aplicaciones Java sin problemas.

## Preguntas frecuentes
### P: ¿Puedo utilizar Aspose.Tasks con otros lenguajes de programación?
R: Sí, Aspose.Tasks admite múltiples lenguajes de programación, incluidos .NET, Java y C.++.
### P: ¿Aspose.Tasks es adecuado para proyectos a gran escala?
R: Absolutamente, Aspose.Tasks está diseñado para manejar proyectos de cualquier tamaño con facilidad.
### P: ¿Puedo personalizar los datos del proyecto usando Aspose.Tasks?
R: Sí, puedes manipular datos del proyecto, modificar tareas, recursos y mucho más usando Aspose.Tasks.
### P: ¿Aspose.Tasks requiere la instalación de Microsoft Project?
R: No, Aspose.Tasks funciona de forma independiente y no requiere la instalación de Microsoft Project.
### P: ¿Hay soporte técnico disponible para Aspose.Tasks?
 R: Sí, puede obtener soporte técnico en el foro Aspose.Tasks en[aquí](https://forum.aspose.com/c/tasks/15).