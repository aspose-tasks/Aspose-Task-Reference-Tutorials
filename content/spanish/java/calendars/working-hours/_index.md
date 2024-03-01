---
title: Obtenga horas de trabajo del calendario usando Aspose.Tasks
linktitle: Obtenga horas de trabajo del calendario usando Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Extraiga fácilmente las horas de trabajo de los calendarios de MS Project con Aspose.Tasks para Java. Simplifique las tareas de gestión de proyectos.
type: docs
weight: 13
url: /es/java/calendars/working-hours/
---
## Introducción
Gestionar los calendarios de los proyectos y extraer las horas de trabajo es esencial para una gestión eficaz de los proyectos. Aspose.Tasks para Java proporciona una funcionalidad sólida para recuperar las horas de trabajo de los calendarios de MS Project sin esfuerzo. En este tutorial, lo guiaremos a través del proceso paso a paso.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK) instalado en su sistema.
2.  Biblioteca Aspose.Tasks para Java descargada y agregada a su proyecto. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/java/).
3. Conocimientos básicos del lenguaje de programación Java.
## Importar paquetes
Primero, importe los paquetes necesarios para trabajar con Aspose.Tasks para Java:
```java
import com.aspose.tasks.*;
```
## Paso 1: cargar el archivo del proyecto
Comience cargando su archivo de MS Project:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Paso 2: recuperar información de tareas y calendario
Extraiga los detalles de la tarea y el calendario del proyecto:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Paso 3: definir las fechas de inicio y finalización
Configure las fechas de inicio y finalización de la tarea:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Paso 4: iterar a través de las fechas
Iterar a través de fechas dentro de la duración de la tarea:
```java
java.util.Calendar tempDate = calStartDate;
```
## Paso 5: Calcular la duración
Calcular la duración en minutos, horas y días:
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
## Conclusión
En este tutorial, cubrimos cómo recuperar horas de trabajo de un calendario de MS Project usando Aspose.Tasks para Java. Si sigue estos pasos, podrá gestionar de manera eficiente los cronogramas de los proyectos y calcular la duración de las tareas con facilidad.
## Preguntas frecuentes
### P: ¿Puede Aspose.Tasks para Java manejar estructuras de proyectos complejas?
R: Sí, Aspose.Tasks para Java brinda soporte integral para manejar estructuras de proyectos complejas, incluidas tareas, recursos y calendarios.
### P: ¿Aspose.Tasks para Java es compatible con diferentes versiones de MS Project?
R: Por supuesto, Aspose.Tasks para Java admite varias versiones de MS Project, lo que garantiza la compatibilidad entre diferentes entornos.
### P: ¿Puedo personalizar el horario laboral y los días festivos en los calendarios del proyecto?
R: Sí, puede personalizar fácilmente el horario laboral y los días festivos de acuerdo con los requisitos de su proyecto utilizando Aspose.Tasks para las API de Java.
### P: ¿Aspose.Tasks para Java ofrece soporte y documentación?
R: Sí, Aspose.Tasks para Java proporciona documentación extensa y foros de soporte dedicados para ayudar a los desarrolladores a utilizar sus funciones de manera efectiva.
### P: ¿Existe una versión de prueba disponible de Aspose.Tasks para Java?
 R: Sí, puede acceder a una versión de prueba gratuita de Aspose.Tasks para Java desde[aquí](https://releases.aspose.com/).