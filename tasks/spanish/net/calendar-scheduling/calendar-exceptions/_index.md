---
title: Manejo de excepciones de calendario en Aspose.Tasks
linktitle: Manejo de excepciones de calendario en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar excepciones de calendario en Aspose.Tasks para .NET con tutoriales y ejemplos paso a paso.
type: docs
weight: 12
url: /es/net/calendar-scheduling/calendar-exceptions/
---
## Introducción

En este tutorial, exploraremos cómo administrar excepciones de calendario en Aspose.Tasks usando el marco .NET. Las excepciones de calendario nos permiten definir fechas o períodos especiales en el calendario de un proyecto donde se altera el horario de trabajo habitual, como días festivos o cierres temporales. Cubriremos varios métodos para manejar excepciones de calendario paso a paso, usando Aspose.Tasks para .NET.

## Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Conocimientos básicos del lenguaje de programación C#.
- Visual Studio instalado en su sistema.
- Biblioteca Aspose.Tasks para .NET agregada a su proyecto.

## Importar espacios de nombres

En primer lugar, importemos los espacios de nombres necesarios para nuestro proyecto:

```csharp
using Aspose.Tasks;
using System;


```

## Paso 1: eliminar una excepción del calendario

Para eliminar una excepción de calendario, siga estos pasos:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Mostrar información del calendario
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Eliminar la primera excepción
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Paso 2: Obtener el tiempo de trabajo de una excepción de calendario

Para recuperar el tiempo de trabajo de una excepción de calendario, siga estos pasos:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Mostrar calendario e información de excepciones
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Obtener tiempo de trabajo y mostrar detalles
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Paso 3: Definir excepciones de calendario

Para agregar o eliminar excepciones de calendario, siga estos pasos:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Crear una nueva excepción de calendario
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Establecer detalles de excepción
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Comprobar si una fecha es una excepción
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Agregar la excepción al calendario
    calendar.Exceptions.Add(exception);

    // Eliminar una excepción si existe
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Agregar una nueva excepción
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Imprimir excepciones
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Conclusión

En este artículo, cubrimos varios aspectos del manejo de excepciones de calendario en Aspose.Tasks para .NET. Si sigue los pasos proporcionados, puede gestionar eficazmente las excepciones en los cronogramas de su proyecto, garantizando una representación precisa de las horas de trabajo y eventos especiales.

## Preguntas frecuentes

### P1: ¿Puedo agregar varias excepciones a un solo calendario?

R1: Sí, puedes agregar múltiples excepciones a un calendario para acomodar varias fechas o períodos especiales.

### P2: ¿Cómo puedo comprobar si una fecha específica es una excepción?

 A2: Puedes usar el`CheckException()` método para verificar si una fecha particular cae bajo una excepción.

### P3: ¿Es posible eliminar una excepción existente de un calendario?

 R3: Sí, puede eliminar excepciones accediendo al`Exceptions` recopilación del calendario y uso del`Remove()` método.

### P4: ¿Qué tipos de excepciones de calendario se admiten?

R4: Aspose.Tasks admite varios tipos de excepciones, incluidas excepciones diarias, semanales, mensuales y anuales, lo que brinda flexibilidad para definir reglas de excepción.

### P5: ¿Puedo personalizar el horario laboral para fechas de excepción específicas?

R5: Sí, puede definir horarios de trabajo personalizados para fechas de excepción individuales utilizando los métodos apropiados proporcionados por Aspose.Tasks.