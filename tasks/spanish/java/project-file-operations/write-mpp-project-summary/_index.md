---
title: Escriba el resumen del proyecto MPP en Aspose.Tasks
linktitle: Escriba el resumen del proyecto MPP en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a escribir resúmenes de proyectos MPP en Java usando Aspose.Tasks. Configure y recupere información del proyecto sin esfuerzo.
weight: 27
url: /es/java/project-file-operations/write-mpp-project-summary/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Escriba el resumen del proyecto MPP en Aspose.Tasks

## Introducción
En este tutorial, aprenderemos cómo utilizar Aspose.Tasks para Java para escribir resúmenes de proyectos MPP. Aspose.Tasks es una potente biblioteca Java para trabajar con archivos de Microsoft Project. Si sigue los pasos que se describen a continuación, podrá configurar y recuperar información resumida diversa sobre un proyecto utilizando esta biblioteca.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema.
2.  Aspose.Tasks para Java: descargue e instale la biblioteca Aspose.Tasks para Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/java/).
3. Entorno de desarrollo integrado (IDE): elija su IDE preferido para el desarrollo de Java, como IntelliJ IDEA, Eclipse o NetBeans.

## Importar paquetes
En primer lugar, importe los paquetes necesarios a su clase Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Paso 1: configurar el proyecto y definir la información resumida
```java
// La ruta al directorio de documentos.
String dataDir = "Your Data Directory";
//Inicialice un nuevo objeto de proyecto con la ruta a su archivo de proyecto
Project project = new Project(dataDir + "project.mpp");
// Establecer información resumida sobre el proyecto.
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Establecer fecha de creación del proyecto.
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Establecer palabras clave para el proyecto.
project.set(Prj.KEYWORDS, "MPP Aspose");
// Establecer la última fecha impresa del proyecto.
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Paso 2: guardar la información resumida del proyecto
```java
// Guarde el proyecto nuevamente en formato MPP
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Mostrar un mensaje de éxito
System.out.println("Process completed Successfully");
```
## Paso 3: leer la información resumida del proyecto
```java
// Lectura de información resumida del proyecto
project = new Project(dataDir + "MppAspose.xml");
// Autor impreso del proyecto.
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Imprimir último autor del proyecto
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Imprimir número de revisión del proyecto.
System.out.println("Revision: " + project.get(Prj.REVISION));
// Imprimir palabras clave del proyecto.
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Imprimir comentarios del proyecto.
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Imprimir fecha de creación del proyecto.
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Imprimir palabras clave del proyecto (nuevamente)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Imprimir la última fecha impresa del proyecto.
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Conclusión
En este tutorial, cubrimos cómo escribir resúmenes de proyectos MPP usando Aspose.Tasks para Java. Si sigue estos pasos, puede configurar y recuperar de manera eficiente información resumida sobre los archivos de su proyecto. Aspose.Tasks simplifica el proceso de trabajar con archivos de Microsoft Project en aplicaciones Java, ofreciendo una funcionalidad sólida y facilidad de uso.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks para Java con otras bibliotecas de Java?
R: Sí, Aspose.Tasks para Java se puede integrar perfectamente con otras bibliotecas de Java para mejorar sus capacidades de gestión de proyectos.
### P: ¿Existe una versión de prueba disponible de Aspose.Tasks para Java?
 R: Sí, puedes descargar una versión de prueba gratuita desde[aquí](https://releases.aspose.com/).
### P: ¿Con qué frecuencia se actualiza Aspose.Tasks para Java?
R: Aspose.Tasks para Java se actualiza periódicamente para garantizar la compatibilidad con las últimas versiones de archivos Java y Microsoft Project.
### P: ¿Puedo personalizar aún más la información del resumen del proyecto?
R: Por supuesto, Aspose.Tasks para Java ofrece amplias opciones para personalizar la información resumida del proyecto de acuerdo con sus requisitos específicos.
### P: ¿Dónde puedo obtener soporte para Aspose.Tasks para Java?
R: Puede obtener soporte en el foro de la comunidad Aspose.Tasks[aquí](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
