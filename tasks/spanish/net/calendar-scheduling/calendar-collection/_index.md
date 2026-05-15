---
date: 2026-04-13
description: Aprenda a establecer horas de trabajo y gestionar colecciones de calendarios
  en Aspose.Tasks para .NET. Importe calendarios de Microsoft Project, elimine el
  calendario del proyecto y obtenga el calendario por nombre fácilmente.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Administrar la colección de calendarios en Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Establecer horas de trabajo en la colección de calendarios de Aspose.Tasks
url: /es/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer horas de trabajo en la colección de calendarios de Aspose.Tasks

En este tutorial, aprenderá cómo **establecer horas de trabajo** y gestionar colecciones de calendarios usando Aspose.Tasks para .NET. Los calendarios definen días laborables, festivos y excepciones, por lo que dominarlos le permite controlar los cronogramas del proyecto con precisión. También le mostraremos cómo importar calendarios de Microsoft Project, eliminar un calendario de un proyecto y obtener un calendario por nombre.

## Respuestas rápidas
- **¿Cuál es la clase principal para los calendarios?** `Project.Calendars` collection.
- **¿Cómo establezco las horas de trabajo?** Crear o modificar un objeto `Calendar` y definir su `WorkingTime`.
- **¿Puedo importar calendarios de Microsoft Project?** Sí – cargue un archivo MPP y acceda a sus calendarios.
- **¿Cómo eliminar un calendario de un proyecto?** Use `Project.Calendars.Remove(calendar)`.
- **¿Cómo obtener un calendario por nombre?** Call `Project.Calendars.GetByName("YourCalendar")`.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Visual Studio: Instale Visual Studio o cualquier otro IDE compatible para desarrollo .NET.  
2. Aspose.Tasks for .NET: Descargue e instale Aspose.Tasks for .NET desde [here](https://releases.aspose.com/tasks/net/).  
3. Basic understanding of C#: Familiaridad con el lenguaje de programación C# será beneficiosa.

## Importar espacios de nombres

Primero, importemos los espacios de nombres necesarios para trabajar con Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Crear un nuevo calendario

### Paso 1: Inicializar un nuevo objeto `Project`.
```csharp
var project = new Project();
```

### Paso 2: Añadir calendarios a la colección de calendarios del proyecto.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Paso 3: Recorrer los calendarios y mostrar sus nombres.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## ¿Cómo establecer horas de trabajo para un calendario?

Para **establecer horas de trabajo**, modifica la colección `WorkingTime` de un `Calendar`.  
Por ejemplo, puedes definir una jornada estándar de 9 a.m.‑5 p.m. o agregar excepciones personalizadas.  
El código para esto es idéntico a los ejemplos mostrados más adelante cuando creamos un calendario estándar.

## Reemplazar un calendario con un nuevo calendario

### Paso 1: Cargar un proyecto existente.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Paso 2: Eliminar el calendario existente (si existe).  
Esto demuestra el escenario de **eliminar calendario del proyecto**.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Paso 3: Añadir un nuevo calendario.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Obtener calendario por nombre o ID

### Paso 1: Cargar el proyecto.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Paso 2: Recuperar calendarios por nombre o UID.  
Esto ilustra la operación de **obtener calendario por nombre**.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Paso 3: Mostrar detalles del calendario.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Recorrer calendarios

### Paso 1: Cargar el proyecto.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Paso 2: Obtener el recuento de calendarios.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Paso 3: Recorrer la colección de calendarios y mostrar los nombres.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Crear un calendario estándar

### Paso 1: Inicializar un nuevo proyecto.
```csharp
var project = new Project();
```

### Paso 2: Definir un nuevo calendario y hacerlo estándar.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Paso 3: Guardar el proyecto.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Problemas comunes y soluciones

- **Calendario no encontrado al usar `GetByName`** – Asegúrese de que el nombre exacto coincida con mayúsculas/minúsculas usadas al agregar el calendario.  
- **Horas de trabajo no aplicadas** – Después de establecer `WorkingTime`, recuerde guardar el proyecto; de lo contrario los cambios permanecen solo en memoria.  
- **Falla al importar calendarios de un archivo MPP** – Verifique que el archivo de origen sea un archivo válido de Microsoft Project y que tenga permisos de lectura.

## Preguntas frecuentes

### P1: ¿Puedo crear días laborables personalizados en Aspose.Tasks?

R1: Sí, puede crear días laborables personalizados añadiendo excepciones a los calendarios.

### P2: ¿Es posible importar calendarios de archivos de Microsoft Project?

R2: Absolutamente, Aspose.Tasks admite la importación de calendarios desde archivos de Microsoft Project.

### P3: ¿Cómo puedo eliminar un calendario específico de un proyecto?

R3: Puede eliminar un calendario obteniéndolo de la colección y luego llamando al método `Remove`.

### P4: ¿Aspose.Tasks admite la exportación de calendarios a diferentes formatos?

R4: Sí, Aspose.Tasks permite exportar calendarios a varios formatos como XML, MPP, etc.

### P5: ¿Puedo personalizar las horas de trabajo para días específicos en un calendario?

R5: Por supuesto, puede definir horas de trabajo para días individuales usando excepciones en el calendario.

## Preguntas frecuentes

**P: ¿Cuál es la mejor manera de establecer un calendario de turno de 24 horas?**  
R: Cree un nuevo calendario, elimine las entradas `WorkingTime` existentes y añada un único rango `WorkingTime` de 00:00 a 24:00 para cada día laborable.

**P: ¿Puedo copiar un calendario de un proyecto a otro?**  
R: Sí—exporte el calendario a XML usando `project.Save` y luego impórtelo en otro proyecto con `new Project(xmlPath)`.

**P: ¿Cómo importo programáticamente calendarios de Microsoft Project?**  
R: Cargue el archivo MPP con `new Project("source.mpp")`; los calendarios estarán disponibles a través de `project.Calendars`.

**P: ¿Existe un límite en la cantidad de calendarios en un proyecto?**  
R: Prácticamente no; la colección puede contener tantos calendarios como la memoria lo permita, pero mantenga la lista manejable para el rendimiento.

**P: ¿Los cambios en un calendario actualizan automáticamente las tareas que lo usan?**  
R: Sí—las tareas vinculadas a un calendario reflejan los horarios de trabajo actualizados después de guardar el proyecto.

---

**Última actualización:** 2026-04-13  
**Probado con:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}