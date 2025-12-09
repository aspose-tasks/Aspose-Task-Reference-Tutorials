---
date: 2025-12-02
description: Aprenda a configurar el calendario, definir los días laborables en MS
  Project y establecer días laborables personalizados usando Aspose.Tasks para Java.
  Guarde el proyecto como XML con solo unas pocas líneas de código.
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo configurar el calendario y definir los días de la semana en MS Project
  con Aspose.Tasks
url: /es/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer el calendario y definir los días laborables en MS Project con Aspose.Tasks

## Introducción
En este tutorial descubrirá **cómo establecer el calendario** de forma programática y definir los días laborables en un archivo Microsoft Project usando la biblioteca Aspose.Tasks para Java. Ya sea que necesite crear una semana laboral estándar, agregar días laborables en fin de semana, o configurar un horario corto para el viernes, esta guía lo acompañará en cada paso, desde la creación del proyecto hasta guardar el archivo como XML.

## Respuestas rápidas
- **¿Qué biblioteca se necesita?** Aspose.Tasks for Java  
- **¿Puedo agregar días laborables en fin de semana?** Sí, solo agregue sábado y domingo como días laborables.  
- **¿Cómo guardo el proyecto?** Use `prj.save(..., SaveFileFormat.Xml)`.  
- **¿Necesito una licencia?** Una prueba gratuita sirve para evaluación; se requiere una licencia para producción.  
- **¿Qué versión de Java se requiere?** Java 8 o superior.

## ¿Qué significa “cómo establecer el calendario” en el contexto de MS Project?
Establecer un calendario en MS Project significa definir qué días son laborables, las horas de trabajo diarias y cualquier excepción, como festivos. Este calendario impulsa la programación de tareas, la asignación de recursos y los cronogramas generales del proyecto.

## ¿Por qué usar Aspose.Tasks para la manipulación de calendarios?
- **Control total** – crear, modificar o eliminar calendarios de forma programática sin abrir la interfaz de usuario.  
- **Multiplataforma** – funciona en cualquier SO que soporte Java.  
- **Soporta todos los formatos de archivo** – MPP, MPT y XML, por lo que puede *guardar el proyecto como XML* para una fácil integración con otros sistemas.  
- **Sin dependencias COM** – a diferencia de la biblioteca Microsoft Project Interop.

## Prerrequisitos
Antes de comenzar, asegúrese de tener:

1. **Java Development Kit (JDK) 8+** – descargue desde el [sitio web de Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – obtenga el último JAR desde la [página de descarga de Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Un IDE o herramienta de construcción (Maven/Gradle) para agregar el JAR de Aspose.Tasks al classpath de su proyecto.

## Importar paquetes
Primero, importe las clases que necesitará. Estas importaciones le dan acceso a objetos de proyecto, calendario y tiempo de trabajo.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Guía paso a paso

### Paso 1: Crear una instancia de Project
Cree un nuevo objeto `Project`. Este objeto representa el archivo MS Project que estará editando.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Paso 2: Definir un nuevo calendario
Agregue un calendario nuevo al proyecto. Asignarle un nombre claro ayuda cuando tiene varios calendarios.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Paso 3: Agregar días laborables estándar (lunes‑jueves)
Utilice el asistente incorporado `WeekDay.createDefaultWorkingDay` para establecer el horario predeterminado de 9 am‑5 pm para la semana laboral principal.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Paso 4: Agregar días laborables de fin de semana
Si su proyecto se ejecuta los fines de semana, simplemente agregue sábado y domingo como días laborables regulares. Esto demuestra **agregar días laborables de fin de semana**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Paso 5: Establecer un día laborable corto personalizado (viernes)
Aquí **establecemos días laborables personalizados** para el viernes: un turno matutino (9 am‑12 pm) y un turno vespertino (1 pm‑4 pm).

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

### Paso 6: Guardar el proyecto como XML
Finalmente, persista los cambios. La opción `SaveFileFormat.Xml` le permite **guardar el proyecto como XML**, lo cual es útil para la integración con otras herramientas.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **Los tiempos de trabajo no se aplican** | Asegúrese de que `setDayWorking(true)` se llame en el `WeekDay` personalizado. |
| **Archivo no encontrado al guardar** | Verifique que `dataDir` apunte a una carpeta existente y que su aplicación tenga permisos de escritura. |
| **El calendario no se refleja en las tareas** | Asigne el calendario recién creado a recursos o tareas usando `task.setCalendar(cal)`. |

## Preguntas frecuentes

**P: ¿Puedo definir días no laborables personalizados usando Aspose.Tasks para Java?**  
R: Sí. Establezca la propiedad `DayWorking` a `false` para cualquier `WeekDay` que desee tratar como día no laborable.

**P: ¿Cómo puedo agregar festivos o excepciones a nivel de empresa?**  
R: Cree objetos `CalendarException`, especifique las fechas de excepción y agréguelos a `cal.getExceptions()`.

**P: ¿Es la biblioteca compatible con versiones antiguas de MS Project?**  
R: Absolutamente. Aspose.Tasks soporta formatos MPP, MPT y XML en múltiples versiones de Project.

**P: ¿Puedo modificar un calendario existente en un proyecto importado?**  
R: Cargue el proyecto con `new Project("existing.mpp")`, recupere el calendario deseado, realice cambios y guarde.

**P: ¿Aspose.Tasks también maneja tareas recurrentes?**  
R: Sí, puede crear y editar tareas recurrentes usando la clase `RecurringTask`.

## Conclusión
Ahora sabe **cómo establecer el calendario**, **definir los días laborables en MS Project**, agregar días laborables de fin de semana y crear un horario corto para el viernes, todo con Aspose.Tasks para Java. Guarde el resultado como XML e integre la lógica del calendario en cualquier solución de gestión de proyectos basada en Java.

---

**Last Updated:** 2025-12-02  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}