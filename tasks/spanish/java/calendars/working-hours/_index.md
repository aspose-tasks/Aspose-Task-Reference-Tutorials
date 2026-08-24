---
date: 2026-08-24
description: Aprenda cómo agregar un calendario de festivos, determinar los días laborables
  y calcular la duración de la tarea extrayendo las horas laborables de los calendarios
  de MS Project usando Aspose.Tasks para Java.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Cómo agregar un calendario de festivos y determinar los días laborables
og_description: Aprenda cómo agregar un calendario de festivos, determinar los días
  laborables y calcular la duración de la tarea extrayendo las horas laborables de
  los calendarios de MS Project usando Aspose.Tasks para Java.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Cómo agregar un calendario de festivos y determinar los días laborables
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: Cómo agregar un calendario de festivos y determinar los días laborables
url: /es/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar un calendario de festivos y determinar los días laborables

Gestionar los calendarios de proyecto es una parte fundamental de la planificación exitosa. En este tutorial **agregarás un calendario de festivos**, **determinarás los días laborables** para cualquier tarea y **extraerás las horas laborables** de un calendario de MS Project usando Aspose.Tasks for Java. Al final de la guía podrás **calcular la duración de la tarea**, personalizar las horas laborables y cargar de forma fiable un **archivo MPP** para obtener los datos que necesitas, todo sin instalar Microsoft Project.

## Respuestas rápidas
- **¿Qué significa “determinar días laborables”?** Significa identificar qué fechas del calendario se consideran días laborables para una tarea dada.  
- **¿Qué biblioteca debo usar?** Aspose.Tasks for Java ofrece una API completa para trabajar con archivos de MS Project.  
- **¿Cuánto tiempo lleva la implementación?** Normalmente 10–15 minutos para una extracción básica.  
- **¿Necesito una licencia?** Hay una prueba gratuita disponible; se requiere una licencia comercial para uso en producción.  
- **¿Puedo personalizar las horas laborables?** Sí, puedes modificar los calendarios, agregar festivos y establecer rangos de tiempo de trabajo personalizados.  

## Qué es “determinar días laborables”
**Determinar días laborables** significa consultar un calendario de proyecto para averiguar qué fechas están marcadas como días laborables frente a días no laborables (fines de semana, festivos o excepciones personalizadas). Esta información es esencial para **calcular la duración de la tarea** con precisión, ya que solo los días laborables contribuyen al tiempo transcurrido de una tarea.

## ¿Por qué usar Aspose.Tasks para obtener horas laborables?
Aspose.Tasks te permite leer archivos de MS Project sin necesidad de tener Microsoft Project instalado, lo que habilita la automatización en cualquier plataforma. También ofrece procesamiento de alto rendimiento, amplio soporte de formatos y documentación detallada.  

- **Compatibilidad total con calendarios** – los calendarios predeterminados, de recursos y de tareas son accesibles.  
- **Alto rendimiento** – puede procesar proyectos que contengan **más de 10 000 tareas en menos de 2 segundos** en una CPU estándar de 2.5 GHz.  
- **Amplia cobertura de formatos** – admite **más de 50 formatos de entrada y salida**, incluidos MPP, MPX, XML y Primavera.  
- **Documentación completa** – ejemplos de código, referencia de API y foros de la comunidad están disponibles.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Java Development Kit (JDK)** – versión 8 o superior.  
2. **Aspose.Tasks for Java** – descarga el último JAR desde [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/).  
3. Conocimientos básicos de programación en Java.  

## Importar paquetes
La clase `Project` es el objeto de nivel superior de Aspose.Tasks que representa un archivo único de MS Project en memoria. Importa el espacio de nombres requerido antes de comenzar:

Importar paquetes

```java
import com.aspose.tasks.*;
```

## ¿Cómo cargar un archivo MPP con Aspose.Tasks?
La clase `Project` carga un archivo de MS Project y brinda acceso a sus datos. Carga el archivo del proyecto en una sola línea de código; no se requiere UI ni interop COM. Este paso sencillo te brinda acceso completo a calendarios, tareas y recursos.

Cargando un archivo MPP

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Recuperar información de tareas y calendarios
`Task` representa una tarea del proyecto, y `Calendar` define sus reglas de tiempo de trabajo. Selecciona la tarea que deseas analizar y obtén su calendario asociado. El objeto `Task` proporciona los métodos `getStart()` y `getFinish()`, mientras que el objeto `Calendar` expone las definiciones de tiempo de trabajo.

Recuperando tarea y calendario

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Definir fechas de inicio y fin
Los objetos `Date` especifican la ventana de tiempo para el análisis del calendario. Establece la ventana de tiempo para la que deseas **determinar los días laborables**. Usar las fechas de inicio y fin de la tarea garantiza que solo evalúes el período relevante.

Definiendo fechas

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iterar a través de fechas
Un bucle `for` puede iterar sobre cada día en el rango de fechas. Recorre cada fecha en la duración de la tarea. Este bucle te permitirá **personalizar las horas laborables** más adelante si es necesario y es la base para calcular el tiempo total de trabajo.

Iterando fechas

```java
java.util.Calendar tempDate = calStartDate;
```

## Calcular duración
`Duration` agrega el tiempo total de trabajo calculado a partir de la iteración. Durante la iteración verificas si cada día es laborable, sumas las horas laborables y finalmente calculas la duración de la tarea en minutos, horas y días. Esto demuestra cómo **calcular los días laborables** y **calcular la duración de la tarea** de forma programática.

Calculando duración

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## Cómo personalizar horas laborables y festivos
Puedes modificar los rangos de tiempo de trabajo del calendario y agregar excepciones como festivos. Usa `taskCalendar.addWorkingTime()` para establecer nuevos períodos de trabajo y `taskCalendar.addException()` para insertar un festivo. Esto es útil cuando el horario predeterminado de 9‑5 no coincide con las políticas de tu organización.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **La tarea devuelve `null` para el calendario** | Asegúrate de que la tarea realmente tenga un calendario asignado; de lo contrario hereda el calendario predeterminado del proyecto. |
| **Duración incorrecta debido a festivos** | Verifica que los festivos estén definidos en el calendario de la tarea o en el calendario base del proyecto. |
| **Desajuste de zona horaria** | Utiliza `java.util.TimeZone` para alinear la zona horaria del calendario con tu sistema si es necesario. |

## Preguntas frecuentes
### Q: ¿Puede Aspose.Tasks for Java manejar estructuras de proyecto complejas?
A: Sí, Aspose.Tasks for Java ofrece soporte integral para manejar estructuras de proyecto complejas, incluidas tareas, recursos y calendarios.

### Q: ¿Es Aspose.Tasks for Java compatible con diferentes versiones de MS Project?
A: Absolutamente, Aspose.Tasks for Java admite varias versiones de MS Project, garantizando compatibilidad en diferentes entornos.

### Q: ¿Puedo personalizar las horas laborables y los festivos en los calendarios del proyecto?
A: Sí, puedes personalizar fácilmente las horas laborables y los festivos según los requisitos de tu proyecto usando las API de Aspose.Tasks for Java.

### Q: ¿Aspose.Tasks for Java ofrece soporte y documentación?
A: Sí, Aspose.Tasks for Java proporciona documentación extensa y foros de soporte dedicados para ayudar a los desarrolladores a utilizar sus funciones de manera eficaz.

### Q: ¿Hay una versión de prueba disponible para Aspose.Tasks for Java?
A: Sí, puedes acceder a una versión de prueba gratuita de Aspose.Tasks for Java desde la [página de lanzamientos de Aspose](https://releases.aspose.com/).

## Conclusión
En esta guía demostramos cómo **agregar un calendario de festivos**, **determinar los días laborables**, **recuperar las horas laborables** y **calcular la duración de la tarea** a partir de un calendario de MS Project usando Aspose.Tasks for Java. Siguiendo los pasos anteriores puedes automatizar el análisis de horarios, personalizar calendarios y mantener tus planes de proyecto precisos y actualizados. Ahora tienes las herramientas para **leer datos de MS Project**, **cargar un archivo MPP** y realizar cálculos precisos de duración sin necesidad de Microsoft Project.

---

**Última actualización:** 2026-08-24  
**Probado con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Tutoriales relacionados

- [Agregar calendario al proyecto con Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Agregar festivos al calendario y guardar como MPP con Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [Crear excepciones de calendario personalizadas con Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}