---
title: Colección de excepciones de calendario en Aspose.Tasks
linktitle: Colección de excepciones de calendario en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a manejar eficientemente las excepciones de calendario en sus proyectos .NET utilizando Aspose.Tasks, garantizando una programación y gestión de recursos precisas.
weight: 13
url: /es/net/calendar-scheduling/calendar-exception-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Colección de excepciones de calendario en Aspose.Tasks

## Introducción

En la gestión de proyectos, una programación precisa es vital para el éxito. Sin embargo, los escenarios del mundo real a menudo requieren desviaciones de los horarios estándar debido a días festivos, eventos especiales u otros factores. Aspose.Tasks para .NET proporciona una solución sólida para administrar dichas excepciones a través de su función Calendar Exception Collection. Este tutorial lo guiará a través del proceso de utilización de esta funcionalidad paso a paso.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:

1.  Aspose.Tasks para .NET: asegúrese de tener la biblioteca instalada. Puedes descargarlo[aquí](https://releases.aspose.com/tasks/net/).
2. Conocimientos básicos de C#: la familiaridad con el lenguaje de programación C# será útil para comprender los ejemplos.
3. Entorno de desarrollo: configure su entorno de desarrollo preferido, como Visual Studio o JetBrains Rider.

## Importar espacios de nombres

Antes de comenzar a trabajar con Aspose.Tasks para .NET, debe importar los espacios de nombres necesarios a su proyecto. Este paso le permite acceder a las clases y métodos necesarios para gestionar las excepciones del calendario.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Ahora, dividamos el ejemplo proporcionado en varios pasos:

## Paso 1: cargar el proyecto y recuperar el calendario

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

En este paso, cargamos un archivo de proyecto y recuperamos el calendario deseado por su UID.

## Paso 2: borre las excepciones existentes y establezca un calendario estándar

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Este paso borra cualquier excepción existente del calendario y lo establece en una configuración estándar.

## Paso 3: Definir y agregar una excepción de tiempo de trabajo

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

Este paso define una excepción de horario laboral con fechas de inicio y finalización específicas, junto con horarios laborales dentro de esas fechas, y la agrega al calendario.

## Paso 4: Definir y agregar excepciones de tiempo no laborable

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Agregue más excepciones si es necesario

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

Este paso define excepciones de tiempo no laborable, como días festivos, y las agrega al calendario.

## Paso 5: Mostrar excepciones del calendario

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

Este paso muestra las excepciones de calendario agregadas junto con sus detalles.

## Paso 6: eliminar todas las excepciones

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Finalmente, este paso elimina todas las excepciones del calendario.

## Conclusión

Gestionar las excepciones del calendario es crucial para una programación precisa del proyecto. Aspose.Tasks para .NET simplifica esta tarea al proporcionar un conjunto completo de características, incluida la Colección de excepciones de calendario. Si sigue los pasos descritos en este tutorial, podrá manejar de manera eficiente varios escenarios de programación dentro de sus proyectos.

## Preguntas frecuentes

### P1: ¿Puedo agregar varias excepciones a un solo calendario?

 R1: Sí, puede agregar múltiples excepciones a un calendario usando el`AddRange` método.

### P2: ¿Cómo manejo las excepciones recurrentes, como los días festivos semanales?

R2: Puede calcular excepciones recurrentes mediante programación y agregarlas al calendario usando lógica personalizada.

### P3: ¿Es posible importar excepciones de calendario desde fuentes externas?

R3: Sí, puedes leer excepciones de calendario de fuentes externas como bases de datos o archivos CSV e integrarlas en tu proyecto.

### P4: ¿Qué sucede si hay excepciones superpuestas en el calendario?

R4: Aspose.Tasks para .NET le permite manejar excepciones superpuestas definiendo prioridades o resolviendo conflictos según los requisitos de su proyecto.

### P5: ¿Puedo personalizar los horarios de trabajo para cada día dentro de una excepción?

R5: Sí, puede especificar horarios de trabajo personalizados para días individuales dentro de una excepción para adaptarse a necesidades de programación específicas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
