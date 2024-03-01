---
title: Configuración de parámetros de tareas recurrentes en Aspose.Tasks
linktitle: Configuración de parámetros de tareas recurrentes en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a configurar parámetros de tareas recurrentes en Microsoft Project usando Aspose.Tasks para .NET. Tutorial completo con guía paso a paso.
type: docs
weight: 14
url: /es/net/rate-recurring-tasks/recurring-task-parameters/
---
## Introducción
En este tutorial, lo guiaremos a través del proceso de configuración de los parámetros de tareas recurrentes de Microsoft Project usando Aspose.Tasks para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Conocimientos básicos del lenguaje de programación C#.
2. Visual Studio instalado o cualquier otro IDE de C#.
3. Aspose.Tasks para la biblioteca .NET instalada y referenciada en su proyecto.

## Importar espacios de nombres
En primer lugar, necesita importar los espacios de nombres necesarios en su código C#:
```csharp
using Aspose.Tasks;
using System;

```
## Paso 1: definir el directorio de documentos
```csharp
String DataDir = "Your Document Directory";
```
 Reemplazar`"Your Document Directory"` con la ruta a su directorio de documentos.
## Paso 2: cargue el archivo del proyecto
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Esta línea de código carga el archivo de Microsoft Project en el`project` variable.
## Paso 3: definir parámetros de tareas recurrentes
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Aquí, usted define los parámetros para la tarea recurrente, como el nombre de la tarea, la duración, el patrón de recurrencia, el rango de recurrencia y si se ignora el calendario de recursos.
## Paso 4: configurar el calendario para tareas recurrentes
```csharp
parameters.SetCalendar(project, "Standard");
```
Este paso establece el calendario para la tarea recurrente. En este ejemplo, establece el calendario en "Estándar".
## Paso 5: agregar parámetros al proyecto
```csharp
project.RootTask.Children.Add(parameters);
```
Finalmente, agregue los parámetros a la tarea raíz del proyecto.

## Conclusión
En este tutorial, hemos demostrado cómo configurar los parámetros de tareas recurrentes de Microsoft Project usando Aspose.Tasks para .NET. Si sigue estos pasos, podrá gestionar de manera eficiente las tareas recurrentes en sus proyectos.
## Preguntas frecuentes
### ¿Puedo personalizar aún más el patrón de recurrencia?
Sí, Aspose.Tasks proporciona varios patrones de recurrencia y opciones para personalizar según los requisitos de su proyecto.
### ¿Hay una versión de prueba disponible antes de comprar?
 Sí, puede descargar una prueba gratuita desde Aspose.Tasks[sitio web](https://purchase.aspose.com/buy) para evaluar las características de la biblioteca.
### ¿Aspose.Tasks admite otros formatos de archivos de proyecto?
Sí, Aspose.Tasks admite varios formatos de archivos de proyecto, incluidos MPP, XML, XLSX y más.
### ¿Puedo obtener soporte si encuentro algún problema durante la implementación?
Sí, puede visitar el foro Aspose.Tasks para obtener ayuda de la comunidad o comunicarse con el soporte para obtener ayuda directa.
### ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks?
 Puede obtener una licencia temporal del[sitio web](https://purchase.aspose.com/temporary-license/) con fines de prueba.