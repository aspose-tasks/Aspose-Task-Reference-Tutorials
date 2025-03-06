---
title: Personalice las semanas laborales en Aspose.Tasks
linktitle: Colección de semanas laborales en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a personalizar las semanas laborales en Aspose.Tasks para .NET. Guía paso a paso para crear calendarios de proyectos personalizados. ¡Descargar ahora!
weight: 17
url: /es/net/time-recurrence-configuration/workweek-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Personalice las semanas laborales en Aspose.Tasks

## Introducción
¡Bienvenido a nuestro tutorial sobre cómo crear una semana laboral personalizada usando Aspose.Tasks para .NET! En esta guía paso a paso, lo guiaremos a través del proceso de definir una semana laboral personalizada para un calendario en su proyecto. Aspose.Tasks es una poderosa biblioteca que permite a los desarrolladores trabajar de manera eficiente con documentos de Microsoft Project en sus aplicaciones .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
1. Visual Studio: asegúrese de tener Visual Studio instalado en su máquina.
2.  Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks. Puedes encontrar el enlace de descarga.[aquí](https://releases.aspose.com/tasks/net/).
3. Conocimientos básicos de C#: familiarícese con los conceptos básicos del lenguaje de programación C#.
## Importar espacios de nombres
En su proyecto C#, asegúrese de importar los espacios de nombres necesarios:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Paso 1: crear un proyecto y un calendario
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Paso 2: definir una semana laboral personalizada
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Paso 3: establecer días laborables
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Paso 4: Mostrar información sobre las semanas laborales
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Esta guía completa le permite crear y administrar de manera eficiente semanas laborales personalizadas utilizando Aspose.Tasks para .NET.
## Conclusión
En conclusión, Aspose.Tasks para .NET proporciona una solución sólida para manejar calendarios de proyectos con semanas laborales personalizadas. Siguiendo este tutorial, habrá aprendido cómo crear y mostrar información sobre semanas laborales personalizadas en su proyecto.
## Preguntas frecuentes
### ¿Puedo tener varias semanas laborales personalizadas en un solo proyecto?
Sí, puede agregar varias semanas laborales personalizadas al calendario de un proyecto.
### ¿Cómo puedo modificar las semanas laborales existentes?
 Utilice el proporcionado`WorkWeek`Propiedades y métodos para modificar las semanas laborales existentes.
### ¿Aspose.Tasks es compatible con .NET Core?
Sí, Aspose.Tasks es compatible con .NET Core.
### ¿Puedo exportar el proyecto con semanas laborales personalizadas al formato de archivo de Microsoft Project?
Por supuesto, Aspose.Tasks te permite guardar tu proyecto en varios formatos, incluido Microsoft Project.
### ¿Dónde puedo buscar ayuda para consultas relacionadas con Aspose.Tasks?
 Visita el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para cualquier apoyo o asistencia.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
