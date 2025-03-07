---
title: Recuperar información del calendario de MS Project en Aspose.Tasks
linktitle: Recuperar información del calendario en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda cómo recuperar información del calendario de MS Project usando Aspose.Tasks para Java. Guía paso a paso para acceder a los detalles del calendario mediante programación.
weight: 14
url: /es/java/project-file-operations/retrieve-calendar-info/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recuperar información del calendario de MS Project en Aspose.Tasks

## Introducción
En este tutorial, exploraremos cómo recuperar información del calendario de archivos de Microsoft Project usando la biblioteca Aspose.Tasks para Java. Aspose.Tasks proporciona potentes funciones para manipular los datos del proyecto, incluido el acceso a detalles del calendario, como días y horas laborables.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
- Conocimientos básicos de programación Java.
- Kit de desarrollo de Java (JDK) instalado en su sistema.
-  Aspose.Tasks para la biblioteca Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/java/).
## Importar paquetes
Primero, necesita importar los paquetes necesarios en su código Java para usar las funcionalidades de Aspose.Tasks.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Ahora dividamos el ejemplo proporcionado en varios pasos para una mejor comprensión.
## Paso 1: configurar el directorio de datos
```java
String dataDir = "Your Data Directory";
```
 Reemplazar`"Your Data Directory"` con la ruta al directorio de archivos de su proyecto.
## Paso 2: definir unidades de tiempo
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Estas constantes representan unidades de tiempo en microsegundos.
## Paso 3: crear una instancia de proyecto
```java
Project project = new Project(dataDir + "project.mpp");
```
 Esta línea crea una instancia de la`Project` clase, inicializándola con la ruta al archivo del proyecto (`project.mpp`).
## Paso 4: recuperar información de calendarios
```java
CalendarCollection alCals = project.getCalendars();
```
Aquí, recuperamos una colección de calendarios presentes en el archivo del proyecto.
## Paso 5: iterar a través de calendarios
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Información del calendario
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterar a través de los días de la semana
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Tiempo en milisegundos
            double time = ts / (OneHour); // Convertir a horas
            if (wd.getDayWorking()) {
                // Mostrar días y horas laborables
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Este bucle recorre cada calendario e imprime su UID, nombre y días laborables con sus respectivos horarios laborales.
## Paso 6: Mostrar mensaje de finalización
```java
System.out.println("Process completed Successfully");
```
Finalmente, se muestra un mensaje indicando la finalización del proceso.
## Conclusión
En este tutorial, aprendimos cómo recuperar información del calendario de archivos de MS Project usando Aspose.Tasks para Java. Si sigue estos pasos, podrá acceder y manipular eficazmente los datos del proyecto en sus aplicaciones Java.

## Preguntas frecuentes
### P: ¿Puedo utilizar Aspose.Tasks con otros lenguajes de programación?
R: Sí, Aspose.Tasks admite múltiples plataformas y lenguajes de programación, incluidos .NET, C++, Python y Java.
### P: ¿Hay una prueba gratuita disponible para Aspose.Tasks?
 R: Sí, puedes descargar una versión de prueba gratuita desde[aquí](https://releases.aspose.com/).
### P: ¿Cómo puedo obtener soporte para Aspose.Tasks?
R: Puede obtener soporte en el foro de la comunidad Aspose.Tasks[aquí](https://forum.aspose.com/c/tasks/15).
### P: ¿Puedo comprar una licencia temporal para Aspose.Tasks?
 R: Sí, se pueden comprar licencias temporales[aquí](https://purchase.aspose.com/temporary-license/).
### P: ¿Dónde puedo encontrar documentación detallada para Aspose.Tasks?
 R: Puede consultar la documentación.[aquí](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
