---
date: 2026-08-03
description: Aprenda cómo crear un calendario de ms project, agregar el calendar a
  un proyecto y guardar el proyecto como XML usando Aspose.Tasks for Java.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Agregar Calendar a Project usando Aspose.Tasks
og_description: Crear calendario de ms project programáticamente usando Aspose.Tasks
  for Java. Add calendars, personalizar schedules y exportar a XML en minutos.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Crear calendario de ms project con Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Crear calendario de ms project con Aspose.Tasks for Java
url: /es/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear calendario de MS Project con Aspose.Tasks para Java

## Introducción
En los flujos de trabajo modernos de gestión de proyectos, la capacidad de **crear calendario de MS Project** programáticamente puede ahorrar horas de edición manual. Aspose.Tasks para Java le brinda una API limpia y segura en tiempo de compilación para manipular archivos de Microsoft Project sin necesidad de abrir el cliente de escritorio. En este tutorial aprenderá cómo agregar un calendario, cómo crear un calendario de MS Project y cómo guardar el proyecto como XML, todo con solo unas pocas líneas de código Java.

## Respuestas rápidas
- **¿Qué significa “crear calendario de MS Project”?**  
  Significa insertar una nueva definición de tiempo de trabajo (calendario) en un archivo de Microsoft Project mediante código.  
- **¿Qué biblioteca maneja esto?**  
  Aspose.Tasks para Java proporciona la clase `Calendar` y el contenedor `Project` para gestionar calendarios.  
- **¿Necesito una licencia?**  
  Una licencia de evaluación temporal funciona para pruebas; se requiere una licencia completa para uso en producción.  
- **¿Puedo guardar el archivo como XML?**  
  Sí—utilice `SaveFileFormat.Xml` para exportar el proyecto como un archivo XML.  
- **¿Cuáles son los requisitos previos?**  
  Java JDK 8+ y el JAR de Aspose.Tasks para Java en su classpath.

## ¿Qué es crear calendario de MS Project?
Crear un calendario de MS Project significa agregar programáticamente una nueva definición de calendario a un archivo de Project, especificando días laborables, excepciones y horas de trabajo diarias, y luego asignar ese calendario a tareas, recursos o al proyecto completo para que los cálculos de programación respeten el tiempo de trabajo definido.

## ¿Por qué usar Aspose.Tasks para Java para agregar un calendario al proyecto?
Debería usar Aspose.Tasks para Java porque proporciona una API totalmente segura en tiempo de compilación que funciona sin necesidad de instalar Microsoft Project, admite todas las versiones principales de Project (2007‑2021, cubriendo más de 5 versiones) y puede exportar a XML, MPP y **más de 10** formatos adicionales, lo que permite la creación automatizada masiva de calendarios en cualquier servidor.

## Requisitos previos
- **Java Development Kit (JDK) 8 o más reciente** instalado y configurado.  
- **Aspose.Tasks for Java** library – descargue desde el [sitio web oficial](https://releases.aspose.com/tasks/java/) y añada el JAR al classpath de su proyecto.  
- Un IDE o herramienta de compilación (Maven/Gradle) de su elección.

## Guía paso a paso

### Paso 1: importar el paquete Aspose.Tasks requerido
Primero, importe las clases de Aspose.Tasks al alcance para que pueda trabajar con proyectos y calendarios.

```java
import com.aspose.tasks.*;
```

### Paso 2: establecer la ruta del directorio de datos
Defina dónde se escribirá el archivo de proyecto generado. Reemplace el marcador de posición con una ruta absoluta o relativa en su máquina.

```java
String dataDir = "Your Data Directory";
```

### Paso 3: crear una nueva instancia de Project
`Project` es la clase principal que representa un archivo de Microsoft Project en memoria.

```java
Project prj = new Project();
```

### Paso 4: definir los calendarios que desea agregar
`Calendar` define un horario con días laborables, excepciones y horarios de trabajo para un proyecto.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Consejo profesional:** Después de agregar un calendario, puede personalizar sus días laborables con `cal1.getWeekDays().add(...)` y establecer las horas de trabajo diarias usando `cal1.getBaseCalendar().setWorkingTime(...)`.

### Paso 5: guardar el proyecto (guardar proyecto como XML)
`SaveFileFormat.Xml` indica a Aspose.Tasks que escriba el proyecto en formato XML.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Paso 6: mostrar un mensaje de finalización
Informe al usuario que la operación se completó con éxito.

```java
System.out.println("Process completed Successfully");
```

Al seguir estos seis pasos concisos, ha agregado correctamente **un calendario a un proyecto** y guardado el resultado como un archivo XML.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **`NullPointerException` en `prj.getCalendars()`** | Objeto Project no inicializado correctamente. | Asegúrese de que se llame a `new Project()` antes de acceder a los calendarios. |
| **Archivo no encontrado al guardar** | `dataDir` apunta a una carpeta que no existe. | Cree el directorio primero o use una ruta absoluta. |
| **El nombre del calendario aparece como “no info”** | Se usaron nombres de marcador de posición en el ejemplo. | Reemplace con nombres significativos que reflejen el horario (p. ej., “Calendario de vacaciones de EE. UU.”). |
| **El XML guardado no se puede abrir en MS Project** | Uso de una versión desactualizada de Aspose.Tasks. | Actualice a la última versión de Aspose.Tasks para Java. |

## Preguntas frecuentes

**P: ¿Puede Aspose.Tasks manejar calendarios complejos con múltiples excepciones?**  
R: Sí – después de agregar un calendario puede definir excepciones, horas de trabajo y días no laborables usando las clases `WeekDay` y `Exception`.

**P: ¿Es posible asignar el nuevo calendario a tareas específicas?**  
R: Absolutamente. Obtenga una tarea mediante `prj.getRootTask().getChildren().add("Task Name")` y establezca `task.set(Tsk.CALENDAR, cal3);`.

**P: ¿La biblioteca admite guardar en otros formatos como MPP?**  
R: Sí. Reemplace `SaveFileFormat.Xml` por `SaveFileFormat.Mpp` o `SaveFileFormat.P6` según sea necesario; Aspose.Tasks admite **12** formatos de salida.

**P: ¿Necesito una licencia para compilaciones de desarrollo?**  
R: Una licencia de evaluación temporal es suficiente para pruebas; se requiere una licencia completa para implementaciones en producción.

**P: ¿Dónde puedo obtener ayuda si encuentro problemas?**  
R: El foro de la comunidad de Aspose.Tasks es un recurso excelente: [Foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Última actualización:** 2026-08-03  
**Probado con:** Aspose.Tasks for Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo definir los días de la semana en calendarios de MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Cómo establecer el calendario del proyecto en Java con Aspose.Tasks](/tasks/java/calendars/properties/)
- [Crear excepciones de calendario personalizadas con Aspose.Tasks para Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}