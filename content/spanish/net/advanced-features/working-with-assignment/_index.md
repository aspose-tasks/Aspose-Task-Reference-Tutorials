---
title: Trabajar con Asignación en Aspose.Tasks
linktitle: Trabajar con Asignación en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar asignaciones de proyectos en .NET usando Aspose.Tasks. Explore diferentes contornos para la programación de recursos.
type: docs
weight: 13
url: /es/net/advanced-features/working-with-assignment/
---
## Introducción

En este tutorial, exploraremos cómo trabajar con asignaciones en Aspose.Tasks para .NET. Las asignaciones son cruciales en la gestión de proyectos, ya que asignan recursos a las tareas, lo que ayuda a programar y seguir el progreso. Nos centraremos en generar datos de fase temporal de asignación de recursos con varios contornos utilizando Aspose.Tasks.

## Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1.  Instalación de Aspose.Tasks para .NET: Descargue e instale la biblioteca Aspose.Tasks para .NET desde[enlace de descarga](https://releases.aspose.com/tasks/net/).
2. Comprensión básica de C# y .NET Framework: para seguir adelante es necesario estar familiarizado con el lenguaje de programación C# y los conceptos de .NET Framework.

## Importar espacios de nombres

Asegúrese de importar los espacios de nombres necesarios a su proyecto C#:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Paso 1: crear un proyecto y una tarea

Comencemos creando un nuevo proyecto y agregándole una tarea. Establezca la fecha de inicio, duración y finalización de la tarea:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Paso 2: agregar un recurso y asignarlo a una tarea

A continuación, agregue un recurso al proyecto y asígnelo a la tarea creada anteriormente:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Paso 3: generar datos en fases temporales con diferentes contornos

Ahora, generemos datos en fases temporales con diferentes contornos para la asignación de recursos:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Paso 4: cambiar contornos y generar datos

Podemos cambiar el tipo de contorno y generar datos en fases temporales en consecuencia. Aquí hay unos ejemplos:

```csharp
// Cambiar contorno
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Generar datos en fases temporales e imprimir
// Repita este paso para otros tipos de contorno.
```

## Conclusión

En este tutorial, aprendimos cómo trabajar con asignaciones en Aspose.Tasks para .NET. Exploramos la generación de datos de asignación de recursos en fases temporales con varios contornos. Este conocimiento puede ser inmensamente útil en escenarios de gestión de proyectos.

## Preguntas frecuentes

### P1: ¿Puedo usar Aspose.Tasks para programar tareas en mi aplicación .NET?

R1: Sí, Aspose.Tasks proporciona API integrales para la programación y gestión de tareas en aplicaciones .NET.

### P2: ¿Hay una prueba gratuita disponible para Aspose.Tasks?

 R2: Sí, puedes aprovechar una prueba gratuita desde[aquí](https://releases.aspose.com/).

### P3: ¿Existe alguna limitación en la cantidad de tareas o recursos en Aspose.Tasks?

R3: Aspose.Tasks no impone ninguna limitación en la cantidad de tareas o recursos que puede administrar en sus proyectos.

### P4: ¿Puedo personalizar los contornos para las asignaciones de recursos en Aspose.Tasks?

R4: Sí, como se demuestra en este tutorial, puede configurar varios contornos, como tortuga, campana, pico, etc., según los requisitos de su proyecto.

### P5: ¿Dónde puedo encontrar soporte para consultas relacionadas con Aspose.Tasks?

 R5: Puede encontrar soporte en el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) donde expertos y miembros de la comunidad participan activamente en debates.