---
date: 2026-08-13
description: Aprenda cómo leer semanas laborables de un calendario de MS Project usando
  Aspose.Tasks para Java. Siga la guía paso a paso con ejemplos de código y consejos
  de solución de problemas.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Leer semanas laborables del calendario con Aspose.Tasks
og_description: Cómo leer semanas laborables de un calendario de MS Project usando
  Aspose.Tasks para Java. Siga el tutorial conciso con pasos de configuración, fragmentos
  de código y consejos de solución de problemas.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Cómo leer semanas laborables del calendario de MS con Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Cómo leer semanas laborables del calendario de MS con Aspose.Tasks
url: /es/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer semanas laborables del calendario de MS con Aspose.Tasks

## Introducción
En este tutorial **aprenderás a leer semanas laborables** de un calendario de Microsoft Project usando la biblioteca Aspose.Tasks para Java. Ya sea que estés construyendo un panel de informes, sincronizando horarios con un sistema ERP, o automatizando la extracción de datos para análisis, el acceso programático a las definiciones de semanas laborables ahorra innumerables horas manuales. Aspose.Tasks soporta **más de 50 formatos de entrada y salida** y puede procesar archivos de proyecto de cientos de páginas sin cargar todo el archivo en memoria, brindándote tanto flexibilidad como rendimiento.

## Respuestas rápidas
- **¿Qué significa “read workweeks”?** Se refiere a extraer definiciones de semanas laborables (fechas y reglas de tiempo de trabajo diario) de un archivo Project mediante código Java.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks para Java (prueba gratuita disponible).  
- **¿Necesito una licencia para desarrollo?** Una prueba funciona para pruebas; se requiere una licencia comercial para implementaciones en producción.  
- **¿Qué formatos de archivo son compatibles?** Se manejan tanto *.mpp* como archivos Project XML, además de más de 50 formatos adicionales para importación/exportación.  
- **¿Cuánto tiempo lleva la implementación?** Normalmente menos de 10 minutos una vez que la biblioteca está configurada.

## ¿Qué es una semana laborable en MS Project?
Una semana laborable define las reglas del calendario que determinan cuándo los recursos están disponibles durante un período específico. Incluye una fecha de inicio, una fecha de fin y intervalos diarios de tiempo de trabajo (p. ej., de 9 a.m. a 5 p.m.). En MS Project, cada calendario puede contener múltiples semanas laborables, lo que permite modelar festivos, patrones de turnos o horarios estacionales.

## ¿Cómo lee Aspose.Tasks las semanas laborables de un calendario?
Aspose.Tasks expone la `WorkWeekCollection` de un objeto `Calendar`. Creando una instancia de `Project`, seleccionando el calendario deseado (por UID o nombre) y recorriendo su `WorkWeekCollection`, puedes obtener la etiqueta de cada semana laborable, el rango de fechas efectivo y los intervalos diarios de tiempo de trabajo detallados. La API maneja todas las conversiones de fecha‑hora y respeta automáticamente la configuración de zona horaria del proyecto.

## ¿Por qué leer semanas laborables en Java desde un calendario de Microsoft Project?
Leer las semanas laborables programáticamente elimina la copia‑pega manual, asegura que los sistemas descendentes (ERP, RR.HH., informes) utilicen exactamente las mismas reglas de programación y garantiza la consistencia entre múltiples proyectos. La automatización también reduce errores humanos y acelera los pipelines de integración, especialmente cuando necesitas procesar decenas de archivos de proyecto cada noche.

## Requisitos previos
Antes de sumergirnos en el código, asegúrate de tener:

1. **Java Development Kit (JDK)** – versión 8 o posterior instalada.  
2. **Aspose.Tasks for Java** – descarga el JAR más reciente desde el sitio oficial: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Un **archivo de proyecto de muestra** (`ReadWorkWeeksInformation.mpp`) colocado en una carpeta conocida en tu máquina.

## Importar paquetes
Primero, importa las clases que necesitaremos para interactuar con calendarios y semanas laborables:
`Project` representa un archivo Microsoft Project, `Calendar` proporciona sus calendarios, `WorkWeek` define una semana laborable y `WeekDay` representa un día.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Paso 1: configurar tu directorio de datos
Define la carpeta que contiene el archivo `.mpp`. Reemplaza el marcador de posición con la ruta real en tu máquina:

```java
String dataDir = "Your Data Directory";
```

## Paso 2: crear una instancia de Project y acceder al calendario
`Project` representa un archivo Microsoft Project y proporciona acceso a sus estructuras de datos, incluidos calendarios, tareas y recursos.  
Instancia un objeto `Project`, elige el calendario que deseas (por UID) y obtén su `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Consejo profesional:** Si no estás seguro del UID del calendario, recorre `project.getCalendars()` e imprime primero el nombre y UID de cada calendario.

## Paso 3: iterar a través de las semanas laborables
La clase `WorkWeek` encapsula una definición de semana laborable, que contiene fechas de inicio/fin y configuraciones diarias de tiempo de trabajo.  
Recorre cada `WorkWeek` para mostrar su nombre, fechas de inicio/fin y los tiempos de trabajo diarios:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Lo que verás:** La consola imprime la etiqueta de cada semana laborable (p. ej., “Standard”), su rango de fechas efectivo, y puedes profundizar en las horas de trabajo exactas para cada día.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| `NullPointerException` al acceder a `calendar` | UID incorrecto o el calendario no existe | Verifica el UID con `project.getCalendars().size()` y lista primero los calendarios disponibles. |
| Sin salida para semanas laborables | El calendario seleccionado no tiene semanas laborables personalizadas (usa la predeterminada) | Usa el calendario predeterminado (`project.getDefaultCalendar()`) o crea una semana laborable programáticamente. |
| El formato de fecha se ve extraño | `System.out.println` usa el formato predeterminado de `java.util.Date` | Aplica un `SimpleDateFormat` para formatear las fechas según sea necesario. |

## Preguntas frecuentes
**P: ¿Puedo modificar la información de las semanas laborables usando Aspose.Tasks para Java?**  
R: Sí. La API proporciona `addWorkWeek()`, `removeWorkWeek()`, y setters de propiedades para cambiar nombres, fechas y horarios de trabajo.

**P: ¿Aspose.Tasks es compatible con diferentes versiones de archivos Microsoft Project?**  
R: Absolutamente. Soporta archivos MPP desde Project 98 hasta las versiones más recientes, así como archivos Project XML.

**P: ¿Puedo integrar Aspose.Tasks con otros frameworks Java?**  
R: Sí. La biblioteca es Java puro, por lo que puedes usarla junto a Spring, Jakarta EE o cualquier otro framework.

**P: ¿Hay una versión de prueba disponible para Aspose.Tasks?**  
R: Sí, puedes descargar una prueba gratuita de 30 días desde el sitio oficial: [Aspose.Tasks trial](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar soporte para Aspose.Tasks?**  
R: El foro de la comunidad de Aspose es el mejor lugar: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Última actualización:** 2026-08-13  
**Probado con:** Aspose.Tasks for Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Agregar calendario al proyecto con Aspose.Tasks para Java](/tasks/java/calendars/create/)
- [Recuperar excepciones de calendario con Aspose.Tasks – tutorial asp tasks java](/tasks/java/calendar-exceptions/retrieve/)
- [Cómo establecer el calendario y definir los días de la semana en MS Project con Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}