---
title: Domine el manejo de datos en fases temporales con Aspose.Tasks para .NET
linktitle: Manejo de datos en fases temporales en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore Aspose.Tasks para .NET para manejar sin esfuerzo datos en fases temporales, mejorar la planificación de proyectos y optimizar la gestión de recursos. #Aspose #Tareas #Proyecto MS
weight: 14
url: /es/net/text-view-configuration/timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Domine el manejo de datos en fases temporales con Aspose.Tasks para .NET

## Introducción
En el mundo de la gestión de proyectos, el manejo eficaz de los datos en fases temporales es crucial para la asignación de recursos, la estimación de costos y la planificación general del proyecto. Aspose.Tasks para .NET proporciona una potente solución para trabajar sin problemas con datos personalizados en fases temporales. Este tutorial lo guiará a través del proceso de manejo de datos en fases temporales utilizando Aspose.Tasks, permitiéndole optimizar la gestión de recursos en sus proyectos.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Una comprensión básica de los conceptos de gestión de proyectos.
-  Aspose.Tasks instalado para .NET. Puedes descargarlo[aquí](https://releases.aspose.com/tasks/net/).
- Un editor de código, como Visual Studio, para implementar los ejemplos proporcionados.
## Importar espacios de nombres
En su proyecto .NET, asegúrese de importar los espacios de nombres necesarios para aprovechar las funcionalidades de Aspose.Tasks. Agregue las siguientes líneas al comienzo de su archivo de código:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Ahora, dividamos el ejemplo proporcionado en varios pasos para guiarlo en el manejo de datos en fases temporales usando Aspose.Tasks:
## Paso 1: configurar el proyecto
```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Aquí, inicializamos un nuevo proyecto y configuramos su modo de cálculo.
## Paso 2: definir recursos y tareas
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Cree recursos de trabajo y costos, así como una tarea, para simular la estructura de un proyecto.
## Paso 3: asignar recursos a la tarea
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Asigne recursos de trabajo y costos a la tarea.
## Paso 4: agregar datos personalizados en fases temporales
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Pasos similares para costAssignment
costAssignment.TimephasedData.Clear();
```
Agregue datos personalizados de fases temporales para asignaciones de trabajo y costos.
## Paso 5: Mostrar datos en fases temporales
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Mostrar información relevante sobre cada entrada de datos en fases temporales
    }
}
```
Finalmente, muestre los datos de fases temporales para cada tarea.
#
## Conclusión
El manejo eficaz de datos de fases temporales en Aspose.Tasks abre nuevas posibilidades para la planificación detallada de proyectos y la gestión de recursos. Siguiendo esta guía paso a paso, habrá aprendido cómo manipular datos en fases temporales para satisfacer las necesidades específicas de sus proyectos.
## Preguntas frecuentes
### ¿Puedo utilizar Aspose.Tasks para .NET con otras herramientas de gestión de proyectos?
Aspose.Tasks está diseñado principalmente para el desarrollo .NET. Sin embargo, sus funcionalidades pueden complementar varias herramientas de gestión de proyectos.
### ¿Hay una prueba gratuita disponible para Aspose.Tasks para .NET?
 Sí, puedes explorar una prueba gratuita.[aquí](https://releases.aspose.com/).
### ¿Cómo puedo obtener soporte para Aspose.Tasks para .NET?
 Visita el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para el apoyo de la comunidad.
### ¿Qué es una licencia temporal y cómo puedo obtenerla?
 Más información sobre licencias temporales[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo encontrar la documentación de Aspose.Tasks para .NET?
 Consulte el completo[documentación](https://reference.aspose.com/tasks/net/) para obtener información detallada.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
