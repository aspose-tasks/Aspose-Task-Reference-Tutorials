---
title: Convertir MS Project a SVG en Java
linktitle: Guardar como SVG en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda cómo guardar archivos de Microsoft Project como SVG en Java usando la biblioteca Aspose.Tasks. Guía paso a paso con ejemplos de código.
type: docs
weight: 18
url: /es/java/project-file-operations/save-as-svg/
---
## Introducción
Aspose.Tasks para Java es una poderosa biblioteca para trabajar con archivos de gestión de proyectos, que permite a los desarrolladores manipular datos del proyecto, realizar diversas operaciones y generar informes de manera eficiente. En este tutorial, exploraremos cómo guardar un proyecto como SVG usando Aspose.Tasks para Java. SVG (Scalable Vector Graphics) es un formato ampliamente utilizado para mostrar gráficos vectoriales en la web, proporcionando escalabilidad y renderizado de alta calidad.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
### Entorno de desarrollo Java
Asegúrese de tener instalado el kit de desarrollo de Java (JDK) en su sistema. Puede descargar e instalar JDK desde el sitio web de Oracle.
### Aspose.Tasks para la biblioteca Java
 Descargue e instale la biblioteca Aspose.Tasks para Java desde el sitio web. Puede encontrar el enlace de descarga en la documentación proporcionada.[aquí](https://releases.aspose.com/tasks/java/).

## Importar paquetes
Primero, necesita importar los paquetes necesarios en su programa Java para trabajar con las funcionalidades de Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Ahora dividamos el ejemplo proporcionado en varios pasos:
## Paso 2: definir el directorio de datos
```java
String dataDir = "Your Data Directory";
```
 Reemplazar`"Your Data Directory"`con la ruta al directorio donde se encuentra el archivo de su proyecto.
## Paso 3: cargar el archivo del proyecto
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Este paso carga el archivo de proyecto llamado "HomeMovePlan.mpp" desde el directorio de datos especificado.
## Paso 4: guardar como SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Este paso guarda el proyecto cargado en formato SVG con el nombre "project5.svg" en el directorio de datos especificado.

## Conclusión
En este tutorial, hemos aprendido cómo guardar un proyecto como SVG usando Aspose.Tasks para Java. Si sigue los pasos proporcionados, puede convertir de manera eficiente archivos de proyecto a formato SVG, lo que permite una integración perfecta con aplicaciones basadas en web o herramientas de visualización.
## Preguntas frecuentes
### ¿Aspose.Tasks para Java es compatible con todas las versiones de archivos de Microsoft Project?
Sí, Aspose.Tasks para Java admite varias versiones de archivos de Microsoft Project, incluidos los formatos MPP, MPT y XML.
### ¿Puedo personalizar la apariencia de la salida SVG?
Sí, puede personalizar la apariencia de la salida SVG ajustando parámetros como fuentes, colores y configuraciones de diseño.
### ¿Aspose.Tasks para Java requiere una licencia para uso comercial?
 Sí, se requiere una licencia válida para el uso comercial de Aspose.Tasks para Java. Puede obtener una licencia desde el sitio web.[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Puedo probar Aspose.Tasks para Java antes de comprarlo?
 Sí, puede solicitar una prueba gratuita de Aspose.Tasks para Java desde el sitio web[aquí](https://purchase.aspose.com/buy) para evaluar sus características y capacidades.
### ¿Dónde puedo obtener soporte para Aspose.Tasks para Java?
 Puede obtener soporte para Aspose.Tasks para Java visitando el foro[aquí](https://forum.aspose.com/c/tasks/15), donde podrás hacer preguntas e interactuar con la comunidad.