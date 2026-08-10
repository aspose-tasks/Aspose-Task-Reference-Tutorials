---
date: 2026-03-29
description: Aprenda cómo establecer palabras clave y la fecha de creación en un proyecto
  MPP usando Aspose.Tasks para Java. Guía paso a paso con ejemplos de código.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo establecer palabras clave en el resumen del proyecto MPP con Aspose.Tasks
url: /es/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer palabras clave en el resumen del proyecto MPP con Aspose.Tasks

## Introducción
En este tutorial descubrirás **cómo establecer palabras clave** y otra información de resumen para un archivo de proyecto MPP usando Aspose.Tasks para Java. Ya sea que necesites incrustar detalles del autor, números de revisión o una fecha de creación personalizada, esta guía te lleva paso a paso, con código listo para ejecutar. Al final podrás establecer palabras clave, establecer la fecha de creación en Java y recuperar los datos del archivo.

## Respuestas rápidas
- **¿Qué biblioteca se utiliza?** Aspose.Tasks for Java  
- **¿Propósito principal?** Establecer palabras clave, información del autor y fecha de creación en un archivo MPP  
- **¿Cuántos pasos de código?** Tres bloques de código simples (inicializar, guardar, leer)  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción  
- **¿Versión de Java compatible?** Java 8 o superior  

## Qué es “cómo establecer palabras clave” en un archivo MPP?
Las palabras clave son campos de metadatos almacenados dentro de un archivo Microsoft Project (MPP). Ayudan a categorizar proyectos, permiten búsquedas rápidas y proporcionan información contextual para herramientas posteriores. Aspose.Tasks expone la propiedad `Prj.KEYWORDS`, lo que facilita escribir o actualizar este valor de forma programática.

## Por qué usar Aspose.Tasks para Java para establecer palabras clave y fecha de creación?
* **Compatibilidad total con .MPP** – funciona con todos los formatos Project 2007‑2023.  
* **No se requiere instalación de COM ni Office** – Java puro, perfecto para entornos de servidor.  
* **API rica** – además de palabras clave, puedes establecer autor, revisión, comentarios y fechas en una sola llamada.  
* **Optimizado para rendimiento** – lectura/escritura rápida incluso para archivos de proyecto grandes.

## Requisitos previos
Antes de comenzar, asegúrate de tener:
1. **Java Development Kit (JDK)** – JDK 8 o superior instalado.  
2. **Aspose.Tasks for Java** – descarga el último JAR desde [aquí](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans o cualquier editor que prefieras.

## Importar paquetes
Primero, importa las clases que necesitarás. Estas importaciones te dan acceso al objeto `Project`, a la enumeración `Prj` para los campos de resumen y al enum `SaveFileFormat` para guardar.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Paso 1: Configurar el proyecto y definir la información de resumen
Crea una instancia de `Project`, luego usa el método `set` para escribir los metadatos deseados. Observa cómo **establecemos las palabras clave** y **establecemos la fecha de creación en Java** usando un objeto `Calendar`.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Paso 2: Guardar la información de resumen del proyecto
Después de rellenar los campos, persiste los cambios. Aquí guardamos el proyecto como XML para una inspección fácil, pero también puedes guardarlo nuevamente como MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Paso 3: Leer la información de resumen del proyecto
Para verificar que los metadatos se escribieron correctamente, vuelve a cargar el archivo y lee cada propiedad. Este paso demuestra que **cómo establecer palabras clave** realmente funciona de extremo a extremo.

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
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **NullPointerException en `project.get(Prj.CREATION_DATE)`** | El calendario nunca se estableció antes de guardar. | Asegúrate de llamar a `project.set(Prj.CREATION_DATE, cal.getTime())` antes de `save()`. |
| **Las palabras clave no aparecen en la UI de Microsoft Project** | El archivo se guardó como XML y se abrió directamente en Project. | Guarda nuevamente como MPP (`SaveFileFormat.MPP`) o abre el XML mediante *Import* en Project. |
| **Los valores de fecha se desplazan por la zona horaria** | `Date` de Java incluye información de zona horaria. | Usa `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` si necesitas fechas en UTC. |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Tasks para Java con otras bibliotecas Java?**  
R: Sí, Aspose.Tasks para Java se puede integrar sin problemas con otras bibliotecas Java para mejorar tus capacidades de gestión de proyectos.

**P: ¿Hay una versión de prueba disponible para Aspose.Tasks para Java?**  
R: Sí, puedes descargar una versión de prueba gratuita desde [aquí](https://releases.aspose.com/).

**P: ¿Con qué frecuencia se actualiza Aspose.Tasks para Java?**  
R: Aspose.Tasks para Java se actualiza regularmente para garantizar la compatibilidad con las últimas versiones de Java y los archivos de Microsoft Project.

**P: ¿Puedo personalizar aún más la información de resumen del proyecto?**  
R: Absolutamente, Aspose.Tasks para Java ofrece amplias opciones para personalizar la información de resumen del proyecto según tus requisitos específicos.

**P: ¿Dónde puedo obtener soporte para Aspose.Tasks para Java?**  
R: Puedes obtener soporte en el foro de la comunidad de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

---

**Última actualización:** 2026-03-29  
**Probado con:** Aspose.Tasks para Java 24.11 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}