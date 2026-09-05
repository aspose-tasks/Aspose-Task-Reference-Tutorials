---
date: 2026-08-08
description: Aprenda a establecer el calendario en MS Project, fijar las horas de
  trabajo diarias y añadir días laborables de fin de semana usando Aspose.Tasks para
  Java. Guarde el proyecto como XML en solo unas pocas líneas de código.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Cómo establecer el calendario en MS Project y definir los días laborables
og_description: Establezca el calendario en MS Project, defina los días laborables
  y añada días laborables de fin de semana usando Aspose.Tasks para Java. Siga este
  tutorial paso a paso y guárdelo como XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Establecer el calendario en MS Project con Aspose.Tasks – Guía de Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Cómo establecer el calendario en MS Project y definir los días laborables
url: /es/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer el calendario ms project y definir los días laborables

En este tutorial aprenderá **cómo establecer el calendario ms project** programáticamente, definir los días laborables y configurar días laborables personalizados usando la biblioteca Aspose.Tasks para Java. Ya sea que esté construyendo un motor de programación, integrándose con sistemas ERP, o simplemente necesite generar un plan de proyecto sin abrir Microsoft Project, los pasos a continuación le muestran cómo crear un calendario, establecer horas de trabajo diarias y agregar días laborables de fin de semana en unas pocas líneas de código.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Tasks for Java.  
- **¿Puedo agregar días laborables de fin de semana?** Sí – solo marque sábado y domingo como días laborables.  
- **¿Cómo guardo el proyecto?** Llame a `prj.save(..., SaveFileFormat.Xml)`.  
- **¿Se necesita una licencia?** Una prueba gratuita funciona para evaluación; se requiere una licencia para uso en producción.  
- **¿Qué versión de Java es compatible?** Java 8 o superior.

## Qué es establecer el calendario ms project?
Establecer el calendario en MS Project determina qué días se consideran laborables, la cantidad de horas de trabajo cada día y cualquier excepción especial como festivos o cierres a nivel de empresa. Esta información impulsa la programación de tareas, la asignación de recursos y los cronogramas generales del proyecto, asegurando que los cálculos respeten los patrones de trabajo reales de la organización.

## Por qué usar Aspose.Tasks para la manipulación de calendarios?
Aspose.Tasks le brinda control programático sobre los calendarios sin lanzar la interfaz de Microsoft Project. Funciona en cualquier sistema operativo que soporte Java, admite más de 50 formatos de entrada y salida, y puede procesar proyectos de cientos de páginas sin cargar todo el archivo en memoria, lo que lo hace ideal para la automatización del lado del servidor.

## Requisitos previos
- **Java Development Kit (JDK) 8+** – descargue desde el [sitio web de Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – obtenga el último JAR desde la [página de descarga de Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
- Un IDE o herramienta de compilación (Maven/Gradle) para agregar el JAR de Aspose.Tasks a su classpath.

## Importar paquetes
Importe las clases que proporcionan acceso a proyectos, calendarios y objetos de tiempo de trabajo.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Guía paso a paso

### Paso 1: crear una instancia de proyecto
Instancie un objeto `Project`, que representa el archivo MS Project que va a manipular.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Paso 2: definir un nuevo calendario
`Calendar` representa un conjunto de horarios de trabajo, excepciones y festivos para un proyecto.  

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Paso 3: agregar días laborables estándar (lunes‑jueves)
`WeekDay` define el horario de trabajo para un día específico de la semana.  

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Paso 4: agregar días laborables de fin de semana
Si su proyecto se ejecuta los fines de semana, agregue sábado y domingo como días laborables regulares. Esto demuestra **agregar días laborables de fin de semana**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Paso 5: establecer un día laborable corto personalizado (viernes)
Configure el viernes con un turno matutino (9 am‑12 pm) y un turno vespertino (1 pm‑4 pm) para ilustrar **establecer horas de trabajo diarias** y un día laborable corto personalizado.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Paso 6: guardar el proyecto como XML
`SaveFileFormat` enumera los formatos de archivo compatibles al guardar un proyecto, como XML o MPP.  

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **Los horarios de trabajo no se aplican** | Asegúrese de que `setDayWorking(true)` se llame en cada `WeekDay` personalizado. |
| **Archivo no encontrado al guardar** | Verifique que `dataDir` apunte a una carpeta existente y que la aplicación tenga permisos de escritura. |
| **El calendario no se refleja en las tareas** | Asigne el calendario recién creado a recursos o tareas usando `task.setCalendar(cal)`. |

## Preguntas frecuentes

**P: ¿Puedo definir días no laborables personalizados usando Aspose.Tasks para Java?**  
R: Sí. Establezca la propiedad `DayWorking` a `false` para cualquier `WeekDay` que desee tratar como día no laborable.

**P: ¿Cómo puedo agregar festivos o excepciones a nivel de empresa?**  
R: Cree objetos `CalendarException`, especifique las fechas de excepción y agréguelos a `cal.getExceptions()`.

**P: ¿Es la biblioteca compatible con versiones anteriores de MS Project?**  
R: Absolutamente. Aspose.Tasks admite los formatos MPP, MPT y XML en múltiples versiones de Project.

**P: ¿Puedo modificar un calendario existente en un proyecto importado?**  
R: Cargue el proyecto con `new Project("existing.mpp")`, obtenga el calendario deseado, realice cambios y guarde.

**P: ¿Aspose.Tasks maneja también tareas recurrentes?**  
R: Sí, puede crear y editar tareas recurrentes usando la clase `RecurringTask`.

## Conclusión
Ahora sabe **cómo establecer el calendario ms project**, definir los días laborables, agregar días laborables de fin de semana y configurar un horario corto para el viernes, todo con Aspose.Tasks para Java. Guarde el resultado como XML e integre la lógica del calendario en cualquier solución de gestión de proyectos basada en Java.

---

**Última actualización:** 2026-08-08  
**Probado con:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Tutoriales relacionados

- [Agregar calendario al proyecto con Aspose.Tasks para Java](/tasks/java/calendars/create/)
- [Determinar días laborables y horas laborables con Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Agregar festivos al calendario y guardar como MPP con Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}