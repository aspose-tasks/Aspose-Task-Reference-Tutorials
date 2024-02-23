---
title: Colección de asignaciones de recursos en Aspose.Tasks
linktitle: Colección de asignaciones de recursos en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar asignaciones de recursos en Microsoft Project usando Aspose.Tasks para .NET. Tutorial paso a paso con ejemplos de código.
type: docs
weight: 12
url: /es/net/resource-risk-analysis/resource-assignment-collection/
---
## Introducción
Bienvenido a este tutorial completo sobre cómo administrar asignaciones de recursos en Microsoft Project usando Aspose.Tasks para .NET. En este tutorial, profundizaremos en el proceso paso a paso, asegurándonos de que tenga una comprensión sólida de cómo manipular las asignaciones de recursos de manera eficiente. Ya sea que sea un desarrollador experimentado o recién esté comenzando, esta guía lo guiará a través de todo lo que necesita saber.
## Requisitos previos
Antes de profundizar en el código, asegúrese de tener la siguiente configuración:
1. Aspose.Tasks para .NET instalado: asegúrese de tener Aspose.Tasks para .NET instalado en su entorno de desarrollo. Si no, puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/net/).
2. Conocimientos básicos de C#: este tutorial asume que tienes un conocimiento básico del lenguaje de programación C#.
3. Archivo de Microsoft Project: tenga listo un archivo de Microsoft Project para realizar pruebas. Si no tiene uno, puede crear un archivo de muestra.

## Importar espacios de nombres
Primero, importemos los espacios de nombres necesarios:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Paso 1: cargue el archivo del proyecto
Comience cargando el archivo de Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Paso 2: agregar tarea y recurso
Ahora, agreguemos una tarea y un recurso al proyecto:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Paso 3: asignar recurso a la tarea
A continuación, asignaremos el recurso a la tarea:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Paso 4: trabajar con diferentes tipos de tareas
También puede trabajar con asignaciones que involucren unidades o costos:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Establezca propiedades para asignaciones con unidades y costos de manera similar a como se muestra en el Paso 3
```
## Paso 5: imprimir tareas
Imprima las tareas del proyecto:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Imprimir detalles de la tarea
}
```
## Paso 6: recuperar la asignación por UID
Puede recuperar asignaciones por UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Paso 7: Verifique el estado de solo lectura
Verifique si la colección de asignación de recursos es de solo lectura:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Paso 8: convertir la colección en lista e iterar
Convierta la colección en una lista y repita sobre ella:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Conclusión
¡Felicidades! Ha aprendido cómo administrar asignaciones de recursos en Microsoft Project usando Aspose.Tasks para .NET. Si sigue estos pasos, podrá manipular tareas y recursos de manera eficiente, haciendo que la gestión de proyectos sea muy sencilla.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks para .NET con diferentes versiones de archivos de Microsoft Project?
R: Sí, Aspose.Tasks para .NET admite varias versiones de archivos de Microsoft Project, incluidos los formatos MPP, MPT y XML.
### P: ¿Existe una versión de prueba disponible antes de comprar Aspose.Tasks para .NET?
 R: Sí, puede obtener una prueba gratuita de Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/).
### P: ¿Cómo puedo obtener asistencia si encuentro algún problema al utilizar Aspose.Tasks para .NET?
 R: Puede buscar ayuda en el foro Aspose.Tasks[aquí](https://forum.aspose.com/c/tasks/15).
### P: ¿Puedo utilizar licencias temporales de Aspose.Tasks para .NET?
 R: Sí, hay licencias temporales disponibles para fines de evaluación. Puedes conseguir uno de[aquí](https://purchase.aspose.com/temporary-license/).
### P: ¿Dónde puedo comprar una licencia completa de Aspose.Tasks para .NET?
 R: Puede comprar una licencia completa en la tienda en línea de Aspose[aquí](https://purchase.aspose.com/buy).