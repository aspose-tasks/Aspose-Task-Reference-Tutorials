---
title: Manejo de partes divididas de MS Project en Aspose.Tasks
linktitle: Manejo de partes divididas en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a manejar partes divididas de MS Project de manera eficiente con Aspose.Tasks para .NET. Mejore el flujo de trabajo de gestión de proyectos.
weight: 18
url: /es/net/rate-recurring-tasks/split-parts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manejo de partes divididas de MS Project en Aspose.Tasks


## Introducción
La gestión de partes divididas de MS Project puede ser un aspecto crucial de la gestión de proyectos cuando se utiliza Aspose.Tasks para .NET. En este tutorial, exploraremos cómo manejar eficazmente piezas divididas siguiendo una guía paso a paso.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
1.  Instalación de Aspose.Tasks para .NET: Descargue e instale Aspose.Tasks para .NET desde[sitio web](https://releases.aspose.com/tasks/net/).
   
2. Comprensión básica de C#: será beneficiosa la familiaridad con el lenguaje de programación C#.

## Importar espacios de nombres
En su código C#, asegúrese de importar los espacios de nombres necesarios:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Paso 1: crear una instancia de proyecto
```csharp
var project = new Project();
```
 Crear una nueva instancia del`Project` clase.
## Paso 2: Establecer las fechas de inicio y finalización del proyecto
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Establecer las fechas de inicio y finalización del proyecto.
## Paso 3: agregar una tarea
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Agregue una nueva tarea al proyecto.
## Paso 4: configurar las propiedades de la tarea
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Establezca propiedades como el estado manual, la fecha de inicio y la duración de la tarea.
## Paso 5: Agregar asignaciones de recursos
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Agregue asignaciones de recursos a la tarea.
## Paso 6: Configurar las propiedades de la tarea
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Establezca propiedades como la fecha de inicio, el trabajo y la fecha de finalización de la tarea.
## Paso 7: Generar datos en fases temporales
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Genere datos de fases temporales para la tarea según el calendario del proyecto.
## Paso 8: dividir la tarea
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Divida la tarea en varias partes dentro del período de tiempo especificado.
## Paso 9: Iterar sobre partes divididas
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Itere sobre las partes divididas de la tarea e imprima sus fechas de inicio y finalización.

## Conclusión
Manejar eficazmente las partes divididas de MS Project en Aspose.Tasks para .NET es crucial para la eficiencia de la gestión de proyectos. Si sigue los pasos descritos en este tutorial, podrá gestionar sin problemas las tareas divididas y mejorar el flujo de trabajo de gestión de proyectos.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks para .NET con otros marcos .NET?
R: Sí, Aspose.Tasks para .NET es compatible con varios marcos .NET, incluidos .NET Core y .NET Standard.
### P: ¿Hay una prueba gratuita disponible para Aspose.Tasks para .NET?
 R: Sí, puedes obtener una prueba gratuita desde[aquí](https://releases.aspose.com/).
### P: ¿Aspose.Tasks para .NET admite la gestión de recursos?
R: Sí, Aspose.Tasks para .NET le permite administrar los recursos del proyecto de manera eficiente.
### P: ¿Puedo personalizar los calendarios de proyectos usando Aspose.Tasks para .NET?
R: Por supuesto, puedes personalizar los calendarios del proyecto según los requisitos de tu proyecto.
### P: ¿Dónde puedo encontrar soporte para Aspose.Tasks para .NET?
 R: Puede encontrar soporte y asistencia en el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
