---
date: 2026-07-29
description: Aprenda cómo programar días no laborables creando un calendario de proyecto
  con Aspose.Tasks for Java, definiendo excepciones de días de la semana y gestionando
  los horarios de vacaciones.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Programar días no laborables – Crear calendario de proyecto Aspose
og_description: Programe días no laborables usando Aspose.Tasks for Java. Aprenda
  a definir los días de la semana, agregar excepciones de calendario y gestionar los
  horarios de vacaciones de manera eficiente.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Programar días no laborables – Crear calendario de proyecto Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Programar días no laborables – Crear calendario de proyecto Aspose
url: /es/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Programar Días No Laborables – Crear Calendario de Proyecto Aspose

### Introducción
When you need to **schedule non working days** for a project, you must be able to model holidays, special shifts, or temporary closures directly in the project plan. Aspose.Tasks for Java gives you full control over calendar definitions, letting you add exceptions that mirror real‑world schedules. In this tutorial we’ll walk through the exact steps to define weekdays for calendar exceptions, so your project timelines stay accurate and reliable. By the end you’ll also see how this fits into a broader **non‑working days schedule** strategy for any enterprise project.

## Respuestas Rápidas
- **¿Qué significa “schedule non working days”?**  
  It means using Aspose.Tasks to create a calendar that marks specific dates as non‑working, influencing task dates automatically.  
- **¿Necesito una licencia para ejecutar el ejemplo?**  
  A free trial works for development; a commercial license is required for production.  
- **¿Qué IDEs son compatibles?**  
  IntelliJ IDEA, Eclipse, NetBeans, or any IDE that supports Java 8+.  
- **¿Puedo agregar múltiples excepciones al mismo calendario?**  
  Yes – you can add as many `CalendarException` objects as needed.  
- **¿A qué formatos de archivo puedo guardar el proyecto?**  
  XML, MPP, and several other formats supported by Aspose.Tasks.  

## ¿Qué es un Calendario de Proyecto en Aspose.Tasks?
The **project calendar** is Aspose.Tasks' top‑level object that defines working days and hours for a project. It directly influences task start/end dates, resource allocation, and overall schedule calculations. By customizing a calendar, you ensure the schedule respects real‑world constraints like company holidays or weekend work policies.

## ¿Por qué definir días de la semana para excepciones de calendario?
Defining weekday exceptions ensures that the project engine treats those days as non‑working, preventing tasks from being automatically scheduled on them and keeping the timeline aligned with real‑world constraints such as holidays, maintenance windows, or special shift patterns across the organization.

- **Líneas de tiempo precisas:** Tasks won’t be placed on holidays or blackout periods.  
- **Planificación de recursos:** Resources are allocated only on valid working days, preventing overallocation.  
- **Cumplimiento:** Schedules automatically follow organizational policies or legal holiday calendars.  

## Programa de Días No Laborables con Excepciones de Calendario
When you maintain a **non‑working days schedule**, you typically have a master list of holidays, maintenance windows, or other blackout periods. Adding those dates as `CalendarException` objects guarantees that every calculation—whether it’s critical‑path analysis or resource leveling—automatically respects those constraints. This approach eliminates manual date adjustments and reduces the risk of schedule drift.

## Requisitos Previos
Before you begin, make sure you have:

1. **Java Development Kit (JDK)** – version 8 or later.  
2. **Aspose.Tasks for Java** – download from the official [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, NetBeans, or any Java‑compatible editor.  

## Cómo programar días no laborables usando excepciones de calendario

Load your project, create a custom calendar, and add `CalendarException` objects that mark the desired weekdays as non‑working. This entire process can be completed in a handful of straightforward steps, and the resulting calendar will automatically influence all task scheduling logic.

### Guía Paso a Paso

### Paso 1: Importar Paquetes Necesarios
We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for date handling.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Paso 2: Definir el Directorio de Datos
Specify where the generated project file will be saved.

```java
String dataDir = "Your Data Directory";
```

### Paso 3: Crear una Instancia de Project
`Project` is the main object that holds all project data, including tasks, resources, and calendars.

```java
Project project = new Project();
```

### Paso 4: Definir un Calendario
`Calendar` represents a schedule of working and non‑working times within a project.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Paso 5: Definir Excepción de Días de la Semana
`CalendarException` represents a period that is marked as non‑working in a calendar.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Paso 6: Guardar el Proyecto
Persist the project, including the custom calendar and its exception, to an XML file.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problemas Comunes y Soluciones
| Problema | Solución |
|----------|----------|
| **Las fechas de excepción no se aplican** | Ensure `setEnteredByOccurrences(false)` and correct `FromDate/ToDate` values. |
| **El archivo guardado está vacío** | Verify `dataDir` points to a writable folder and the filename ends with `.xml`. |
| **El calendario no se refleja en la programación de tareas** | Assign the calendar to tasks or resources using `task.setCalendar(cal)` or `resource.setCalendar(cal)`. |

## Preguntas Frecuentes

**Q: ¿Puedo definir múltiples excepciones para diferentes días de la semana dentro del mismo calendario?**  
A: Yes. Add additional `CalendarException` objects to `cal.getExceptions()` for each distinct period or rule.

**Q: ¿Aspose.Tasks for Java es compatible con diferentes IDEs de Java?**  
A: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and any IDE that supports standard Java projects.

**Q: ¿Puedo personalizar tipos de excepción diferentes a las excepciones diarias?**  
A: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit your scheduling needs.

**Q: ¿Cómo puedo manejar excepciones dinámicamente según los requisitos del proyecto?**  
A: Build the exception objects programmatically—e.g., read holiday dates from a database or configuration file and create `CalendarException` instances in a loop.

**Q: ¿Hay una versión de prueba disponible para Aspose.Tasks for Java?**  
A: Yes, you can download a free trial from the [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## Conclusión
By following these steps you now know how to **schedule non working days** by creating a project calendar and defining weekday exceptions that accurately reflect holidays or special non‑working periods. Proper calendar configuration is essential for realistic schedules, resource allocation, and overall project success. Explore further by attaching the custom calendar to tasks or resources and experimenting with other exception types to build a comprehensive **non‑working days schedule** for any project.

---

**Última actualización:** 2026-07-29  
**Probado con:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Tutoriales Relacionados

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Create Calendar Exception Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)
- [How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}