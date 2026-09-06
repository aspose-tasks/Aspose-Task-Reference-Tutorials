---
date: 2026-08-13
description: Aprenda cómo agregar festivos a un calendario, asignar el calendario
  a un proyecto y guardar el archivo MS Project como MPP usando Aspose.Tasks for Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Actualizar el calendario al formato MPP en Aspose.Tasks
og_description: Agregar festivos al calendario, asignarlo a un proyecto y convertir
  el cronograma a MPP usando Aspose.Tasks for Java. Aprenda la automatización paso
  a paso.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Agregar festivos al calendario y guardarlo como MPP con Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Agregar festivos al calendario y guardarlo como MPP con Aspose.Tasks
url: /es/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar festivos al calendario y guardar como MPP con Aspose.Tasks

## Introducción

En la gestión moderna de proyectos a menudo necesitas **agregar festivos al calendario** archivos, crear un **calendario de MS Project**, y luego compartir el cronograma en el formato nativo MPP. Ya sea que estés consolidando líneas de tiempo de múltiples fuentes o migrando datos heredados, generar un calendario programáticamente elimina errores manuales y acelera la entrega. Este tutorial te guía a través del proceso completo de crear un calendario en MS Project, personalizarlo con festivos, **asignar calendario al proyecto**, y finalmente **convertir el proyecto a MPP** usando la API Java de Aspose.Tasks.

## Respuestas rápidas

- **¿Qué cubre este tutorial?** Agregar festivos a un calendario, asignarlo a un proyecto y guardar el resultado como un archivo MPP con Aspose.Tasks para Java.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java se requiere?** Java 8 o superior (JDK 8+).  
- **¿Puedo personalizar el calendario?** Sí – puedes agregar horarios de trabajo, excepciones y festivos.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un calendario básico.  

## ¿Qué es “crear calendario MS Project”?

Crear un calendario MS Project significa definir los días laborables, horas y excepciones que impulsan la programación de tareas dentro de un archivo de Microsoft Project. Usando Aspose.Tasks puedes crear este calendario programáticamente, establecer festivos e incrustarlo en un proyecto sin abrir la interfaz de MS Project.

## ¿Por qué usar Aspose.Tasks para esta tarea?

Deberías usar Aspose.Tasks porque ofrece compatibilidad total con Java, no necesita Microsoft Office y permite generar y guardar archivos MPP nativos directamente desde el código. La biblioteca soporta todas las funciones de calendario, funciona en cualquier entorno de servidor y procesa proyectos de hasta 10,000 tareas en menos de un segundo.

## Requisitos previos

1. **Java Development Kit (JDK) 8+** – asegúrate de que `java -version` muestre 1.8 o superior.  
2. **Aspose.Tasks for Java** – descarga el último JAR desde el [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, o cualquier editor que prefieras.  
4. **Basic Java knowledge** – familiaridad con clases, métodos y E/S de archivos.  

## Cómo agregar festivos al calendario

Para agregar festivos, creas un nuevo objeto `Calendar`, recuperas su colección `Exceptions` y añades entradas `DateException` para cada fecha de festivo. `DateException` representa una única fecha o rango no laborable en un calendario. Aspose.Tasks trata esas fechas como días no laborables, asegurando que las tareas se programen alrededor de los festivos definidos.

### Paso 1: importar paquetes requeridos

Primero, trae las clases de Aspose.Tasks y las utilidades de Java al alcance.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Paso 2: configurar el directorio de datos

Define dónde vivirán tus plantillas de entrada y archivos de salida. Reemplaza el marcador de posición con la ruta real en tu máquina.

```java
String dataDir = "Your Data Directory";
```

### Paso 3: definir nombres de archivo de entrada y salida

Cargaremos un archivo MPP existente (o un proyecto en blanco) y escribiremos el resultado en un nuevo archivo.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Paso 4: cargar el proyecto y agregar un nuevo calendario

La clase `Project` representa un archivo MS Project en memoria y brinda acceso a sus calendarios, tareas y recursos.

Crea una instancia `Project` a partir del archivo fuente y agrega un calendario llamado **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Paso 5: personalizar el calendario (opcional)

El objeto `Calendar` define los días laborables, horas y excepciones para el cronograma de un proyecto.

Si necesitas horarios de trabajo específicos, festivos o excepciones, llama a tu propio método auxiliar. El ejemplo usa `GetTestCalendar` como marcador de posición.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** Puedes manipular directamente `cal1.getWeekDays()` para establecer horas laborables para cada día de la semana, o usar `cal1.getExceptions()` para **agregar festivos al calendario**.

### Paso 6: asignar el calendario al proyecto

Indica al proyecto que use el calendario recién creado para todos sus cálculos de programación.

```java
project.set(Prj.CALENDAR, cal1);
```

### Paso 7: guardar el proyecto como MPP

La enumeración `SaveFileFormat` especifica el formato de salida, con `Mpp` indicando el formato nativo de Microsoft Project.

Ahora **convierte el proyecto a MPP** guardándolo con la opción `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Paso 8: confirmar la finalización exitosa

Un mensaje simple en la consola te indica que el proceso finalizó sin errores.

```java
System.out.println("Process completed Successfully");
```

## Casos de uso comunes

- **Generación automática de cronogramas** para proyectos recurrentes (p. ej., sprints semanales).  
- **Migrar calendarios heredados CSV o Excel** a un archivo MS Project con todas sus funciones.  
- **Informes del lado del servidor** donde un servicio web devuelve un archivo MPP bajo demanda.  

## Solución de problemas y obstáculos comunes

| Problema | Causa | Solución |
|----------|-------|----------|
| `NullPointerException` en `project.save` | `dataDir` apunta a una carpeta inexistente | Asegúrate de que el directorio exista o créalo programáticamente. |
| Calendario no aplicado a tareas | Las tareas aún hacen referencia al calendario predeterminado | Después de establecer `Prj.CALENDAR`, también actualiza `Task.CALENDAR` de cada tarea si fueron sobrescritas previamente. |
| El archivo de salida tiene 0 KB | Faltan permisos de escritura | Ejecuta la JVM con los derechos de sistema de archivos adecuados o elige una ruta con permisos de escritura. |

## Preguntas frecuentes

**Q: ¿Es Aspose.Tasks para Java compatible con diferentes versiones de MS Project?**  
A: Sí, Aspose.Tasks soporta todos los formatos de archivo de Microsoft Project desde Project 2007 hasta Project 2024, cubriendo más de 10 versiones.

**Q: ¿Puedo personalizar los calendarios según requisitos específicos del proyecto?**  
A: Absolutamente. Puedes definir días laborables, establecer semanas de trabajo personalizadas, agregar festivos e incluso crear múltiples calendarios dentro de un solo archivo de proyecto.

**Q: ¿Aspose.Tasks para Java ofrece soporte para solución de problemas y asistencia?**  
A: Sí, puedes obtener ayuda en el foro de la comunidad de Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: ¿Hay una prueba gratuita disponible para Aspose.Tasks para Java?**  
A: Sí, hay una prueba gratuita totalmente funcional disponible [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks para Java?**  
A: Las licencias temporales pueden solicitarse a través del sitio web de Aspose [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2026-08-13  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Agregar calendario al proyecto con Aspose.Tasks para Java](/tasks/java/calendars/create/)
- [Cómo definir días de la semana en calendarios de MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Crear excepciones de calendario personalizadas con Aspose.Tasks para Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}