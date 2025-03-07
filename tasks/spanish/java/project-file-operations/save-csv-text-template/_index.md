---
title: Guardar como CSV, texto y plantilla en Aspose.Tasks
linktitle: Guardar como CSV, texto y plantilla en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a guardar archivos de Microsoft Project en formatos CSV, texto y plantilla utilizando Aspose.Tasks para Java.
weight: 16
url: /es/java/project-file-operations/save-csv-text-template/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guardar como CSV, texto y plantilla en Aspose.Tasks

## Introducción
En este tutorial, exploraremos cómo guardar archivos de proyecto en varios formatos como CSV, texto y plantilla usando Aspose.Tasks para Java. Aspose.Tasks es una poderosa biblioteca de Java que permite a los desarrolladores trabajar con archivos de Microsoft Project sin la necesidad de instalar Microsoft Project.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK) instalado en su sistema.
2.  Biblioteca Aspose.Tasks para Java descargada y configurada en su proyecto Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/java/).
3. Conocimientos básicos del lenguaje de programación Java.

## Importar paquetes
Primero, necesitas importar los paquetes necesarios en tu archivo Java:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Guardar proyecto como CSV
Analicemos los pasos para guardar un proyecto como CSV:
### Paso 1: cargar el proyecto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Paso 2: guardar como CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Guardar proyecto como texto
Así es como puedes guardar un proyecto como Texto:
### Paso 1: cargar el proyecto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Paso 2: guardar como texto
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Guardar proyecto como plantilla
Guardar un proyecto como plantilla implica los siguientes pasos:
### Paso 1: cargar el proyecto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Paso 2: configurar las opciones de la plantilla
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Paso 3: guardar como plantilla
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Conclusión
En este tutorial, aprendimos cómo guardar archivos de Microsoft Project como CSV, texto y plantilla usando Aspose.Tasks para Java. Con estos sencillos pasos, podrá administrar de manera eficiente los archivos de su proyecto en varios formatos, mejorando su productividad como desarrollador de Java.
## Preguntas frecuentes
### P: ¿Puede Aspose.Tasks para Java manejar archivos de proyectos complejos?
R: ¡Absolutamente! Aspose.Tasks para Java puede manejar proyectos de diversa complejidad con facilidad, brindando soporte integral para formatos de archivo de Microsoft Project.
### P: ¿Existe una versión de prueba disponible de Aspose.Tasks para Java?
 R: Sí, puede obtener una prueba gratuita de Aspose.Tasks para Java desde[aquí](https://releases.aspose.com/).
### P: ¿Dónde puedo encontrar soporte para Aspose.Tasks para Java?
 R: Puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para cualquier ayuda o consulta sobre Aspose.Tasks para Java.
### P: ¿Puedo comprar una licencia temporal de Aspose.Tasks para Java?
 R: Sí, puede comprar una licencia temporal en[aquí](https://purchase.aspose.com/temporary-license/), permitiéndole evaluar todo el potencial de la biblioteca.
### P: ¿Aspose.Tasks para Java es compatible con diferentes sistemas operativos?
R: Sí, Aspose.Tasks para Java es compatible con varios sistemas operativos, incluidos Windows, macOS y Linux.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
