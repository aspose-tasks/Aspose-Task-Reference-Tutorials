---
title: Gestión de la colección de calendarios en Aspose.Tasks
linktitle: Gestión de la colección de calendarios en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar colecciones de calendarios en Aspose.Tasks para .NET de manera eficiente. Cree, modifique y manipule calendarios con facilidad.
type: docs
weight: 11
url: /es/net/calendar-scheduling/calendar-collection/
---
## Introducción

En este tutorial, exploraremos cómo administrar colecciones de calendario en Aspose.Tasks para .NET. Los calendarios juegan un papel crucial en la gestión de proyectos, definiendo días laborables, festivos y excepciones. Aspose.Tasks proporciona una funcionalidad sólida para manipular calendarios dentro de sus proyectos.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Visual Studio: instale Visual Studio o cualquier otro IDE compatible para el desarrollo .NET.
2.  Aspose.Tasks para .NET: Descargue e instale Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/tasks/net/).
3. Comprensión básica de C#: será beneficiosa la familiaridad con el lenguaje de programación C#.

## Importar espacios de nombres

Primero, importemos los espacios de nombres necesarios para trabajar con Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Creando un nuevo calendario

###  Paso 1: Inicializar un nuevo`Project` object.
```csharp
var project = new Project();
```

### Paso 2: agregue calendarios a la colección de calendarios del proyecto.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Paso 3: recorra los calendarios y muestre sus nombres.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Reemplazo de un calendario por un calendario nuevo

### Paso 1: cargue un proyecto existente.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Paso 2: eliminar el calendario existente (si existe).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Paso 3: agrega un nuevo calendario.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Obtener calendario por nombre o ID

### Paso 1: carga el proyecto.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Paso 2: recuperar calendarios por nombre o UID.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Paso 3: muestra los detalles del calendario.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Iterando sobre calendarios

### Paso 1: carga el proyecto.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Paso 2: recuperar el recuento de calendarios.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Paso 3: iterar sobre la colección del calendario y los nombres para mostrar.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Hacer un calendario estándar

### Paso 1: Inicialice un nuevo proyecto.
```csharp
var project = new Project();
```

### Paso 2: Defina un nuevo calendario y conviértalo en estándar.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Paso 3: guarda el proyecto.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Conclusión

Administrar colecciones de calendarios en Aspose.Tasks para .NET es esencial para una gestión eficaz de proyectos. Con las funcionalidades proporcionadas, puede crear, modificar y manipular calendarios de manera eficiente según los requisitos de su proyecto.

## Preguntas frecuentes

### P1: ¿Puedo crear días laborales personalizados en Aspose.Tasks?

R1: Sí, puedes crear días laborales personalizados agregando excepciones a los calendarios.

### P2: ¿Es posible importar calendarios desde archivos de Microsoft Project?

R2: Por supuesto, Aspose.Tasks admite la importación de calendarios desde archivos de Microsoft Project.

### P3: ¿Cómo puedo eliminar un calendario específico de un proyecto?

R3: Puede eliminar un calendario al obtenerlo de la colección y luego llamar al`Remove` método.

### P4: ¿Aspose.Tasks admite la exportación de calendarios a diferentes formatos?

R4: Sí, Aspose.Tasks permite exportar calendarios a varios formatos como XML, MPP, etc.

### P5: ¿Puedo personalizar el horario laboral para días específicos en un calendario?

R5: Ciertamente, puedes definir horas de trabajo para días individuales usando excepciones en el calendario.