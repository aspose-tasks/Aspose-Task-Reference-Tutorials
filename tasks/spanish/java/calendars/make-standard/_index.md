---
date: 2026-08-13
description: Aprenda cómo crear un calendario estándar de MS Project en Java usando
  Aspose.Tasks. Esta guía paso a paso le muestra cómo crear un calendario estándar
  de MS Project, añadirlo como predeterminado y guardar el archivo.
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: Crear calendario estándar en Aspose.Tasks
og_description: Cómo crear un calendario en Java con Aspose.Tasks. Aprenda a crear
  un calendario estándar de MS Project, establecerlo como predeterminado y guardar
  el archivo del proyecto en minutos.
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: Cómo crear un calendario – crear un calendario estándar en Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: Cómo crear un calendario – crear un calendario estándar en Aspose.Tasks
url: /es/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un calendario – crear calendario estándar en Aspose.Tasks

## Introducción
En este tutorial aprenderás **cómo crear un calendario** objetos para archivos de Microsoft Project usando la biblioteca Aspose.Tasks para Java. Recorreremos la creación de un calendario estándar de MS Project, estableciéndolo como el calendario predeterminado (estándar) y guardando el archivo del proyecto. Al final de la guía podrás integrar la creación de calendarios en cualquier solución de gestión de proyectos basada en Java.

## Respuestas rápidas
- **¿Qué significa “calendario estándar”?** Es la definición de tiempo de trabajo predeterminada aplicada a las tareas que no tienen un calendario personalizado asignado.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks for Java – una API pura de Java que funciona sin Microsoft Project instalado.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para implementaciones en producción.  
- **¿Qué formato de archivo se genera?** Un archivo de Microsoft Project basado en XML (`.xml`).  
- **¿Cuánto tiempo lleva la implementación?** Alrededor de 5‑10 minutos para una configuración básica de calendario.

## ¿Qué es un calendario estándar en Microsoft Project?
Un calendario estándar define los días y horas de trabajo predeterminados para un proyecto, típicamente de lunes a viernes, de 8 a.m. a 5 p.m. Cuando añades un calendario estándar, cualquier tarea que no tenga un calendario personalizado asignado hereda estos horarios de trabajo, garantizando una programación coherente en todo el proyecto.

## ¿Por qué usar Aspose.Tasks para crear un calendario?
Aspose.Tasks for Java soporta **más de 50 formatos de entrada y salida** y puede procesar proyectos con hasta **10,000 tareas** sin cargar todo el archivo en memoria. Esta biblioteca pura de Java le permite automatizar la creación de archivos Project en servidores, pipelines CI o cualquier aplicación Java, eliminando la necesidad de una instalación con licencia de Microsoft Project.

## Requisitos previos
Antes de comenzar, asegúrate de que lo siguiente esté listo:

### Instalación del Java Development Kit (JDK)
Instala el JDK más reciente desde el sitio web de Oracle o una distribución OpenJDK.

### Biblioteca Aspose.Tasks para Java
Descarga la biblioteca desde la [página de descarga](https://releases.aspose.com/tasks/java/). Añade el JAR a la ruta de clases de tu proyecto.

## Importar paquetes
Solo necesitamos una importación para este tutorial:

```java
import com.aspose.tasks.*;
```

## Guía paso a paso

### Paso 1: configurar el directorio de datos
Define dónde se guardará el archivo de proyecto generado.

```java
String dataDir = "Your Data Directory";
```

Reemplaza `"Your Data Directory"` con la ruta absoluta en tu máquina (p.ej., `C:/Projects/Output/`).

### Paso 2: crear una instancia de proyecto
`Project` es el objeto de nivel superior de Aspose.Tasks que representa un único archivo Microsoft Project en memoria. Instanciarlo te brinda un contenedor para calendarios, tareas, recursos y otros datos del proyecto.

```java
Project project = new Project();
```

### Paso 3: definir y establecer el calendario como estándar
`Calendar` es la clase que modela un horario de tiempo de trabajo. Añadir un nuevo calendario llamado **“My Cal”** y llamar a `makeStandardCalendar` lo promueve al calendario predeterminado para todo el proyecto.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Consejo profesional:** El método `makeStandardCalendar` marca automáticamente el calendario suministrado como predeterminado para el proyecto, lo cual es exactamente lo que necesitas cuando deseas **añadir funcionalidad de calendario estándar**.

### Paso 4: guardar el proyecto
`SaveFileFormat` es una enumeración que especifica el formato de archivo a usar al guardar un proyecto.  
Persistir el proyecto (incluyendo el nuevo calendario) a un archivo XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Puedes cambiar el nombre del archivo o el formato (`SaveFileFormat.Pp`) si prefieres una versión diferente de Project.

### Paso 5: mostrar mensaje de finalización
Proporciona una señal visual de que el proceso finalizó sin errores.

```java
System.out.println("Process completed Successfully");
```

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **Archivo no encontrado** | `dataDir` apunta a una carpeta que no existe | Crea la carpeta o usa una ruta absoluta |
| **Excepción de licencia** | Ejecutándose sin una licencia válida de Aspose.Tasks en producción | Aplica un archivo de licencia mediante `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Calendario vacío** | Olvidar añadir definiciones de tiempo de trabajo | Usa `cal1.getWeekDays().add(WeekDay.DayType.Monday)` etc., si necesitas horas personalizadas |

## Preguntas frecuentes

**Q: ¿Es Aspose.Tasks compatible con todas las versiones de Microsoft Project?**  
A: Sí, Aspose.Tasks soporta una amplia gama de versiones de Microsoft Project, desde 2000 hasta las versiones más recientes.

**Q: ¿Puedo personalizar aún más la configuración del calendario?**  
A: ¡Absolutamente! Puedes modificar los días laborables, añadir excepciones y definir horarios de trabajo específicos usando las clases `WeekDay` y `WorkingTime`.

**Q: ¿Es Aspose.Tasks adecuado para aplicaciones a nivel empresarial?**  
A: Ciertamente. La biblioteca está diseñada para entornos de alto rendimiento y escalables y ofrece soporte integral para archivos Project grandes.

**Q: ¿Aspose.Tasks ofrece soporte técnico para desarrolladores?**  
A: Sí, Aspose proporciona foros dedicados, soporte basado en tickets y documentación extensa para ayudarte a resolver cualquier problema rápidamente.

**Q: ¿Puedo probar Aspose.Tasks antes de comprar?**  
A: Sí, puedes explorar una versión de prueba gratuita disponible en el [sitio web](https://purchase.aspose.com/buy), lo que te permite evaluar todas las funciones antes de comprometerte.

---

**Última actualización:** 2026-08-13  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriales relacionados

- [Añadir calendario al proyecto con Aspose.Tasks para Java](/tasks/java/calendars/create/)
- [Cómo establecer el calendario del proyecto en Java con Aspose.Tasks](/tasks/java/calendars/properties/)
- [Crear excepciones de calendario personalizadas con Aspose.Tasks para Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}