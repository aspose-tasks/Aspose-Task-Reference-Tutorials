---
title: Guardar como PDF en Aspose.Tasks
linktitle: Guardar como PDF en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a convertir archivos de proyecto a PDF usando Aspose.Tasks para Java. Pasos simples para una conversión eficiente.
weight: 17
url: /es/java/project-file-operations/save-as-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guardar como PDF en Aspose.Tasks

## Introducción
En este tutorial, lo guiaremos a través del proceso de guardar un proyecto como PDF usando Aspose.Tasks para Java. Con Aspose.Tasks, puede convertir de manera eficiente los archivos de su proyecto a formato PDF, garantizando compatibilidad y facilidad para compartir. Profundicemos en los pasos:
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema.
2.  Biblioteca Aspose.Tasks para Java: descargue e instale la biblioteca Aspose.Tasks. Puedes encontrar el enlace de descarga.[aquí](https://releases.aspose.com/tasks/java/).
3. Un archivo de proyecto: tenga listo un archivo de proyecto (por ejemplo, HomeMovePlan.mpp) que desee convertir a PDF.

## Importar paquetes
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Paso 1: leer el archivo de proyecto de entrada
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Asegúrese de reemplazar`"Your Data Directory"` con la ruta a su directorio de datos que contiene el archivo del proyecto.
## Paso 2: guarde el proyecto como PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Este fragmento de código guarda el proyecto como un archivo PDF con el nombre "Project5.pdf".
## Paso 3: Ajustar el contenido al tamaño de la celda
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Aquí, configuramos opciones para guardar el PDF, incluido el contenido adecuado, la escala de tiempo y el formato de presentación.
## Paso 4: Ocultar leyendas
```java
o.setLegendOnEachPage(false);
```
Este paso oculta leyendas en cada página del PDF.
## Paso 5: guarde el proyecto con las opciones aplicadas
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Finalmente, este código guarda el proyecto con las opciones aplicadas en un archivo PDF.

## Conclusión
En este tutorial, aprendimos cómo usar Aspose.Tasks para Java para guardar un proyecto como PDF. Si sigue estos sencillos pasos, podrá convertir de manera eficiente los archivos de su proyecto para compartirlos y distribuirlos fácilmente.
## Preguntas frecuentes
### P: ¿Aspose.Tasks es compatible con todas las versiones de Java?
R: Sí, Aspose.Tasks admite versiones de Java a partir de JDK 6 y superiores.
### P: ¿Puedo personalizar la apariencia del resultado PDF?
R: ¡Absolutamente! Aspose.Tasks ofrece varias opciones para personalizar la salida del PDF según sus requisitos.
### P: ¿Aspose.Tasks admite otros formatos de archivo para la conversión?
R: Sí, Aspose.Tasks admite una amplia gama de formatos de archivo, incluidos MPP, XML, XLSX y más.
### P: ¿Existe una versión de prueba disponible para Aspose.Tasks?
 R: Sí, puede obtener una prueba gratuita de Aspose.Tasks desde[aquí](https://releases.aspose.com/).
### P: ¿Dónde puedo obtener soporte para Aspose.Tasks?
 R: Para obtener soporte y asistencia, puede visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
