---
title: Administrar tareas en Aspose.Tasks
linktitle: Administrar tareas en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore la guía completa sobre cómo administrar tareas con Aspose.Tasks para .NET. Aprenda a agregar, mostrar partes divididas, mover, obtener/establecer propiedades y más.
weight: 15
url: /es/net/task-table-management/managing-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Administrar tareas en Aspose.Tasks

## Introducción
Si es un desarrollador de .NET y busca administrar de manera eficiente las tareas dentro de sus proyectos, Aspose.Tasks para .NET proporciona una solución sólida. Este tutorial lo guiará a través de varios aspectos de la gestión de tareas utilizando Aspose.Tasks, ofreciendo instrucciones paso a paso y ejemplos de código. Ya sea que esté agregando tareas, mostrando partes divididas, moviendo tareas bajo el mismo padre, obteniendo/configurando propiedades de tareas, iterando sobre asignaciones de tareas, leyendo líneas base de tareas o eliminando tareas, esta guía lo tiene cubierto.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
1. Aspose.Tasks para la biblioteca .NET: asegúrese de tener instalada la biblioteca Aspose.Tasks para .NET. Puedes descargarlo[aquí](https://releases.aspose.com/tasks/net/).
2. Directorio de documentos: configure un directorio donde se almacenarán los documentos de su proyecto.
## Importar espacios de nombres
En su proyecto .NET, incluya los espacios de nombres necesarios para trabajar con Aspose.Tasks:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Agregar una tarea a un proyecto
```csharp
// Crear un nuevo proyecto
var project = new Project();
// Agregar una tarea
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// guardar el proyecto
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Mostrar las partes divididas de la tarea
```csharp
// Cargar un proyecto con tareas divididas
var project = new Project(DataDir + "ViewSplitTasks.mpp");
// Acceder a una tarea
var task = project.RootTask.Children.GetById(4);
// Mostrar partes divididas
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Mover una tarea bajo el mismo padre
```csharp
try
{
    // Cargar un proyecto
    var project = new Project(DataDir + "MoveTask.mpp");
    // Mover tareas con id 5 antes de la tarea con id 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Guardar el proyecto modificado
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Obtener/establecer propiedades de tarea
```csharp
// Crear un nuevo proyecto
var project = new Project();
// Agregar una tarea y establecer propiedades
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Recopilar y mostrar propiedades de tareas
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Iterando sobre las asignaciones de tareas
```csharp
// Cargar un proyecto con asignaciones
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Recopilar y mostrar asignaciones de tareas
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Lectura de las líneas base de la tarea
```csharp
// Crear un nuevo proyecto
var project = new Project();
// Agregar una tarea y establecer una línea de base
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Mostrar la duración de la línea base de la tarea
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Eliminar una tarea
```csharp
// Crear un nuevo proyecto
var project = new Project();
// Agregar una tarea
var task = project.RootTask.Children.Add("Task");
//Mostrar el número de tareas antes y después de la eliminación
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Eliminar la tarea
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Conclusión
Administrar tareas en Aspose.Tasks para .NET es un proceso perfecto con los ejemplos proporcionados. Ya sea que sea un desarrollador experimentado o recién esté comenzando, la incorporación de estas técnicas mejorará sus capacidades de gestión de proyectos.
## Preguntas frecuentes
### P: ¿Aspose.Tasks es compatible con todos los marcos .NET?
R: Sí, Aspose.Tasks admite varios marcos .NET, lo que garantiza la compatibilidad con su entorno de desarrollo.
### P: ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks?
 R: Puede obtener una licencia temporal de 30 días en[aquí](https://purchase.aspose.com/temporary-license/).
### P: ¿Existe alguna limitación al trabajar con tareas divididas en Aspose.Tasks?
 R: Las tareas divididas son una característica poderosa y se puede encontrar documentación detallada.[aquí](https://reference.aspose.com/tasks/net/).
### P: ¿Puedo personalizar las propiedades de la tarea más allá de lo que se muestra en los ejemplos?
R: ¡Absolutamente! Aspose.Tasks proporciona amplias opciones de personalización para las propiedades de las tareas. Consulte la documentación para obtener más detalles.
### P: ¿Cómo obtengo soporte para Aspose.Tasks?
 R: Visita el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoyo y debates de la comunidad.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
