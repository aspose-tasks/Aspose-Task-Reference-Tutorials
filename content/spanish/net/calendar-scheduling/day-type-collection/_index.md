---
title: Gestión de la recopilación de tipos de días en Aspose.Tasks
linktitle: Gestión de la recopilación de tipos de días en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar colecciones de tipos de días de manera eficiente en Aspose.Tasks para .NET. Cree, modifique y manipule excepciones de calendario con facilidad.
type: docs
weight: 28
url: /es/net/calendar-scheduling/day-type-collection/
---
## Introducción

 Aspose.Tasks para .NET proporciona una funcionalidad sólida para administrar colecciones de tipos de días, crucial para definir excepciones de calendario semanales en aplicaciones de gestión de proyectos. En este tutorial, exploraremos cómo utilizar el`DayTypeCollection` clase de manera eficiente. 

## Requisitos previos

Antes de continuar con el tutorial, asegúrese de tener los siguientes requisitos previos:

1. Visual Studio: asegúrese de tener Visual Studio instalado en su sistema.
2.  Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/tasks/net/).
3. Conocimientos básicos de C#: familiaridad con el lenguaje de programación C# y los conceptos del marco .NET.

## Importar espacios de nombres

Para comenzar, necesita importar los espacios de nombres necesarios a su proyecto C#:

```csharp
using Aspose.Tasks;
using System;


```

Ahora, dividamos el ejemplo proporcionado en varios pasos:

## Paso 1: cargar el proyecto y acceder al calendario

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Este paso inicializa una nueva instancia de proyecto y recupera el calendario por su UID.

## Paso 2: iterar a través de las excepciones del calendario

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Aquí, recorremos cada excepción del calendario e imprimimos su nombre y los tipos de días asociados.

## Paso 3: modificar las excepciones del calendario

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

Este paso demuestra cómo modificar las excepciones del calendario agregando, eliminando o actualizando tipos de días.

## Paso 4: crear y manipular nuevas excepciones de calendario

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

En este paso final, creamos nuevas excepciones de calendario y las manipulamos agregando y copiando tipos de días.

## Conclusión

 En conclusión, administrar colecciones de tipos de días en Aspose.Tasks para .NET es esencial para definir y modificar excepciones de calendario semanales en aplicaciones de gestión de proyectos. Si sigue la guía paso a paso proporcionada en este tutorial, podrá utilizar eficazmente el`DayTypeCollection` clase para manejar varias operaciones de calendario.

## Preguntas frecuentes

### P1: ¿Se puede utilizar Aspose.Tasks para .NET para crear diagramas de Gantt mediante programación?

R1: Sí, Aspose.Tasks para .NET proporciona API para crear y manipular diagramas de Gantt en aplicaciones .NET.

### P2: ¿Aspose.Tasks para .NET es compatible tanto con .NET Core como con .NET Framework?

R2: Sí, Aspose.Tasks para .NET es compatible con .NET Core y .NET Framework.

### P3: ¿Cómo puedo obtener soporte para Aspose.Tasks para .NET?

 R3: Puede obtener soporte visitando el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) donde podrás hacer preguntas e interactuar con otros usuarios.

### P4: ¿Aspose.Tasks para .NET ofrece una prueba gratuita?

 R4: Sí, puede obtener una prueba gratuita de Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/).

### P5: ¿Puedo comprar una licencia temporal de Aspose.Tasks para .NET?

 R5: Sí, las licencias temporales están disponibles para su compra en el[Aspose sitio web](https://purchase.aspose.com/temporary-license/).