---
date: 2026-02-05
description: Aprenda cómo determinar los días laborables y calcular la duración de
  la tarea extrayendo las horas de trabajo de los calendarios de MS Project usando
  Aspose.Tasks para Java.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Determinar días hábiles y horas de trabajo con Aspose.Tasks
url: /es/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Determinar Días Laborables y Horas Laborales con Aspose.Tasks

## Introduction
Gestionar los calendarios de proyecto es una parte fundamental de la planificación exitosa. En este tutorial **determinará los días laborables** para cualquier tarea y **extraerá las horas laborables** de un calendario de MS Project usando Aspose.Tasks para Java. Al final de la guía podrá **calcular la duración de la tarea**, personalizar las horas laborables y cargar de forma fiable un **archivo MPP** para obtener los datos que necesita. También verá cómo **leer archivos de MS Project** sin tener Microsoft Project instalado, lo que permite la automatización en cualquier plataforma.

## Quick Answers
- **¿Qué significa “determinar días laborables”?** Significa identificar qué fechas del calendario se consideran días de trabajo para una tarea dada.  
- **¿Qué biblioteca debo usar?** Aspose.Tasks para Java ofrece una API completa para trabajar con archivos de MS Project.  
- **¿Cuánto tiempo lleva la implementación?** Normalmente 10–15 minutos para una extracción básica.  
- **¿Necesito una licencia?** Hay una prueba gratuita disponible; se requiere una licencia comercial para uso en producción.  
- **¿Puedo personalizar las horas laborables?** Sí, puede modificar los calendarios, añadir festivos y establecer rangos de tiempo de trabajo personalizados.  

## What is “determine working days”?
Cuando una tarea está programada, el calendario del proyecto define qué días son laborables y cuáles no lo son (fines de semana, festivos). Determinar los días laborables significa consultar ese calendario para saber exactamente cuándo puede realizarse el trabajo, lo cual es esencial para cálculos precisos de **calcular la duración de la tarea**.

## Why use Aspose.Tasks to retrieve working hours?
- **No se requiere Microsoft Project** – puede leer archivos de MS Project directamente desde código Java.  
- **Compatibilidad total con calendarios** – incluye calendarios predeterminados, de recursos y de tareas.  
- **Alto rendimiento** – procesa proyectos grandes rápidamente.  
- **Documentación extensa** – ejemplos y referencia de la API están disponibles fácilmente.

## Prerequisites
Antes de comenzar, asegúrese de tener:

1. **Java Development Kit (JDK)** – versión 8 o superior.  
2. **Aspose.Tasks para Java** – descargue el último JAR desde [here](https://releases.aspose.com/tasks/java/).  
3. Conocimientos básicos de programación en Java.  

## Import Packages
Primero, importe el espacio de nombres principal de Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## How to load an MPP file with Aspose.Tasks?
Cargar el archivo del proyecto es el primer paso para cualquier análisis de calendario. La API le permite **cargar un archivo MPP** en una sola línea de código, sin necesidad de la interfaz de MS Project.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Retrieve Task and Calendar Information
Seleccione la tarea que desea analizar y obtenga su calendario asociado. Aquí es donde **recuperamos las horas laborables** para la tarea:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Define Start and End Dates
Configure la ventana de tiempo para la que desea **determinar los días laborables**. Usar las fechas de inicio y fin de la tarea garantiza que solo evalúe el período relevante.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iterate Through Dates
Itere a través de cada fecha en la duración de la tarea. Este bucle nos ayudará a **personalizar las horas laborables** más adelante si es necesario:

```java
java.util.Calendar tempDate = calStartDate;
```

## Calculate Duration
Durante la iteración verificamos si cada día es laborable, sumamos las horas laborables y finalmente calculamos la duración de la tarea en minutos, horas y días. Este paso muestra cómo **calcular los días laborables** y **calcular la duración de la tarea** programáticamente.

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

## How to customize working hours and holidays
Aspose.Tasks le permite modificar los rangos de tiempo de trabajo del calendario y añadir excepciones como festivos. Puede llamar a `taskCalendar.addWorkingTime()` o `taskCalendar.addException()` para adaptar el horario a las políticas de su organización. Esto es útil cuando el horario predeterminado de 9‑5 no coincide con la realidad.

## Common Issues and Solutions
| Problema | Solución |
|----------|----------|
| **La tarea devuelve `null` para el calendario** | Asegúrese de que la tarea realmente tenga un calendario asignado; de lo contrario, hereda el calendario predeterminado del proyecto. |
| **Duración incorrecta por festivos** | Verifique que los festivos estén definidos en el calendario de la tarea o en el calendario base del proyecto. |
| **Desajuste de zona horaria** | Use `java.util.TimeZone` para alinear la zona horaria del calendario con su sistema si es necesario. |

## Frequently Asked Questions
### Q: ¿Puede Aspose.Tasks para Java manejar estructuras de proyecto complejas?
A: Sí, Aspose.Tasks para Java ofrece soporte integral para manejar estructuras de proyecto complejas, incluidas tareas, recursos y calendarios.

### Q: ¿Es Aspose.Tasks para Java compatible con diferentes versiones de MS Project?
A: Absolutamente, Aspose.Tasks para Java soporta varias versiones de MS Project, garantizando compatibilidad en diferentes entornos.

### Q: ¿Puedo personalizar las horas laborables y los festivos en los calendarios del proyecto?
A: Sí, puede personalizar fácilmente las horas laborables y los festivos según los requisitos de su proyecto usando las API de Aspose.Tasks para Java.

### Q: ¿Aspose.Tasks para Java ofrece soporte y documentación?
A: Sí, Aspose.Tasks para Java proporciona documentación extensa y foros de soporte dedicados para ayudar a los desarrolladores a utilizar sus funciones de manera eficaz.

### Q: ¿Existe una versión de prueba disponible para Aspose.Tasks para Java?
A: Sí, puede acceder a una versión de prueba gratuita de Aspose.Tasks para Java desde [here](https://releases.aspose.com/).

## Conclusion
En esta guía demostramos cómo **determinar los días laborables**, **recuperar las horas laborables** y **calcular la duración de la tarea** a partir de un calendario de MS Project usando Aspose.Tasks para Java. Siguiendo los pasos anteriores podrá automatizar el análisis de horarios, personalizar calendarios y mantener sus planes de proyecto precisos y actualizados. Ahora dispone de las herramientas para **leer datos de MS Project**, **cargar un archivo MPP** y realizar cálculos de duración precisos sin necesidad de Microsoft Project.

---

**Última actualización:** 2026-02-05  
**Probado con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}