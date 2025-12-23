---
date: 2025-12-23
description: Aprenda a crear un resumen MPP y actualizar el autor del proyecto usando
  Aspose.Tasks para Java. Establezca y recupere la información del proyecto sin esfuerzo.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo crear un resumen MPP y actualizar el autor del proyecto con Aspose.Tasks
url: /es/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Escribir Resumen de Proyecto MPP en Aspose.Tasks

## Introducción
En este tutorial, **creará información de resumen MPP** para un archivo de Microsoft Project y aprenderá a **actualizar los datos del autor del proyecto** usando la biblioteca Aspose.Tasks para Java. Ya sea que esté construyendo una herramienta de gestión de proyectos o automatizando informes, controlar las propiedades de resumen programáticamente ahorra tiempo y garantiza consistencia en todos sus proyectos.

## Respuestas rápidas
- **¿Qué significa “crear resumen MPP”?** Significa establecer las propiedades de alto nivel del proyecto (autor, revisión, palabras clave, etc.) que aparecen en el cuadro de diálogo Información de Resumen del Proyecto de Microsoft Project.  
- **¿Qué biblioteca maneja esto?** Aspose.Tasks para Java proporciona una API fluida para leer y escribir esas propiedades.  
- **¿Necesito una licencia?** Hay una prueba gratuita disponible, pero se requiere una licencia comercial para uso en producción.  
- **¿Puedo cambiar también el autor después de guardar el archivo?** Sí – puede **actualizar el autor del proyecto** llamando a `project.set(Prj.AUTHOR, "New Author")` y luego volver a guardar el archivo.  
- **¿Qué formatos de archivo son compatibles?** Tanto MPP como XML (SaveFileFormat.Xml) son totalmente compatibles.

## ¿Qué es crear resumen MPP?
Crear un resumen MPP implica rellenar los metadatos del proyecto—autor, número de revisión, palabras clave, comentarios, fecha de creación y fecha de impresión. Estos metadatos se almacenan dentro del registro de Información de Resumen del Proyecto y se muestran en la sección **Archivo → Información** de Microsoft Project.

## ¿Por qué actualizar el autor del proyecto?
Mantener la información del **autor del proyecto** precisa es esencial para auditorías, colaboración e informes. Cuando varios miembros del equipo contribuyen, puede necesitar **actualizar el autor del proyecto** para reflejar los últimos cambios o atribuir el trabajo correctamente.

## Requisitos previos
Antes de comenzar, asegúrese de contar con los siguientes requisitos:
1. Java Development Kit (JDK) instalado en su máquina.  
2. Aspose.Tasks para Java – descárguelo desde [aquí](https://releases.aspose.com/tasks/java/).  
3. Un IDE como IntelliJ IDEA, Eclipse o NetBeans.

## Importar paquetes
Primero, importe los paquetes necesarios en su clase Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Paso 1: Configurar el proyecto y definir la información de resumen
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
En el código anterior **creamos campos de resumen MPP** como autor, revisión y palabras clave. También puede **actualizar el autor del proyecto** más adelante llamando a `project.set(Prj.AUTHOR, "New Name")`.

## Paso 2: Guardar la información de resumen del proyecto
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Guardar el proyecto persiste todos los datos de resumen que acaba de definir.

## Paso 3: Leer la información de resumen del proyecto
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Este fragmento muestra cómo **leer de nuevo** la información de resumen, confirmando que la operación de **crear resumen MPP** se realizó con éxito.

## Problemas comunes y soluciones
- **Valores nulos después de la lectura:** Asegúrese de que el proyecto se haya guardado correctamente antes de volver a cargarlo. Verifique rutas de archivo y permisos.  
- **Diferencias en el formato de fecha:** `project.get(Prj.CREATION_DATE)` devuelve un `java.util.Date`. Use `SimpleDateFormat` si necesita un formato de visualización personalizado.  
- **Licencia no establecida:** Sin una licencia válida, Aspose.Tasks se ejecuta en modo de evaluación y puede insertar una marca de agua. Registre su licencia al inicio del código.

## Preguntas frecuentes
**P: ¿Puedo usar Aspose.Tasks para Java con otras bibliotecas Java?**  
R: Sí, Aspose.Tasks para Java se puede integrar sin problemas con otras bibliotecas Java para ampliar sus capacidades de gestión de proyectos.

**P: ¿Existe una versión de prueba disponible para Aspose.Tasks para Java?**  
R: Sí, puede descargar una versión de prueba gratuita desde [aquí](https://releases.aspose.com/).

**P: ¿Con qué frecuencia se actualiza Aspose.Tasks para Java?**  
R: Aspose.Tasks para Java se actualiza regularmente para garantizar compatibilidad con las últimas versiones de Java y archivos de Microsoft Project.

**P: ¿Puedo personalizar aún más la información de resumen del proyecto?**  
R: Por supuesto, Aspose.Tasks para Java ofrece amplias opciones para personalizar la información de resumen del proyecto según sus requisitos específicos.

**P: ¿Dónde puedo obtener soporte para Aspose.Tasks para Java?**  
R: Puede obtener soporte en el foro de la comunidad de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

## Conclusión
En este tutorial le hemos mostrado cómo **crear datos de resumen MPP**, **actualizar el autor del proyecto** y verificar esos cambios usando Aspose.Tasks para Java. Al automatizar estos pasos obtiene control total sobre los metadatos del proyecto, haciendo sus aplicaciones más robustas y sus informes de proyecto más precisos.

---

**Última actualización:** 2025-12-23  
**Probado con:** Aspose.Tasks para Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}