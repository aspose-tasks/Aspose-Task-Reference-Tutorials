---
title: Dominar la recopilación de datos en fases temporales en Aspose.Tasks
linktitle: Recopilación de datos en fases temporales en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore la recopilación de datos en fases temporales en Aspose.Tasks para .NET. Guía paso a paso, preguntas frecuentes y más. ¡Mejore sus capacidades de gestión de proyectos hoy!
type: docs
weight: 15
url: /es/net/text-view-configuration/timephased-data-collection/
---
## Introducción
¿Está buscando aprovechar el poder de los datos en fases temporales en sus aplicaciones .NET utilizando Aspose.Tasks? ¡No busque más! Esta guía completa lo guiará a través del proceso de recopilación de datos en fases temporales con Aspose.Tasks para .NET, asegurándose de que aproveche al máximo esta poderosa biblioteca.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
1.  Aspose.Tasks para la biblioteca .NET: descargue e instale la biblioteca desde[Documentación de Aspose.Tasks .NET](https://reference.aspose.com/tasks/net/).
2. Entorno de desarrollo .NET: asegúrese de tener configurado un entorno de desarrollo .NET que funcione.
3. Su directorio de documentos: reemplace el marcador de posición "Su directorio de documentos" en los fragmentos de código con la ruta a su directorio de documentos.
## Importar espacios de nombres
En su proyecto .NET, comience importando los espacios de nombres necesarios para aprovechar las funcionalidades de Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Crear un proyecto y recursos
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Agregar tareas al proyecto
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Establecer propiedades de tarea...
var task2 = project.RootTask.Children.Add("Task 2");
// Establecer propiedades de tarea2...
```
## 3. Asignar recursos a las tareas
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Establecer propiedades de asignación...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// Establecer propiedades de asignación2...
```
## 4. Trabajar con datos en fases temporales
```csharp
// Establecer contorno de trabajo contorneado
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Compruebe si la recopilación de datos en fases temporales es de solo lectura
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Borrar datos generados en fases temporales
assignment.TimephasedData.Clear();
// Crear y agregar datos en fases temporales
var td = new TimephasedData
{
    // Establecer propiedades de datos de fase temporal...
};
assignment.TimephasedData.Add(td);
// Agregar una lista de datos de fases temporales
var list = new List<TimephasedData>();
// Agregue más elementos de datos de fases temporales a la lista...
assignment.TimephasedData.AddRange(list);
// Filtrar datos de fases temporales por tipo y rango de fechas
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Imprimir datos filtrados en fases temporales...
```
## 5. Manipular datos en fases temporales
```csharp
//Agregue un elemento de datos de fase temporal incorrecto y luego elimínelo
var td4 = new TimephasedData
{
    // Establecer propiedades de datos de fase temporal incorrectas...
};
assignment.TimephasedData.Add(td4);
// Eliminar el elemento de datos de fase temporal incorrecto
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Iterar sobre todos los elementos de fase temporal
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Imprimir detalles del artículo en fases temporales...
}
```
## 6. Copie los datos de fases temporales a otra tarea
```csharp
// Copiar datos de fases temporales a otra tarea
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Convertir la colección en una lista simple
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Eliminar elementos de datos de fases temporales uno por uno
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Conclusión
En conclusión, este tutorial proporciona un tutorial detallado sobre la recopilación de datos en fases temporales utilizando Aspose.Tasks para .NET. Si sigue estos pasos, podrá integrar perfectamente esta funcionalidad en sus proyectos, lo que permitirá un seguimiento del tiempo y una gestión de recursos eficaces.
## Preguntas frecuentes
### ¿Puedo utilizar Aspose.Tasks para .NET con otras herramientas de gestión de proyectos?
Sí, Aspose.Tasks para .NET está diseñado para funcionar con herramientas populares de gestión de proyectos y admite varios formatos de archivo.
### ¿Existe un límite en la cantidad de recursos y tareas que puedo administrar con Aspose.Tasks?
Aspose.Tasks maneja proyectos de diferentes tamaños y no existe un límite estricto en la cantidad de recursos y tareas.
### ¿Cómo puedo obtener soporte para cualquier problema o consulta relacionada con Aspose.Tasks para .NET?
 Para obtener ayuda, visite el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para conectarse con la comunidad y obtener ayuda.
### ¿Puedo probar Aspose.Tasks para .NET antes de comprarlo?
 Sí, puede explorar las características de Aspose.Tasks para .NET accediendo al[prueba gratis](https://releases.aspose.com/).
### ¿Dónde puedo comprar una licencia de Aspose.Tasks para .NET?
 Puede comprar una licencia de Aspose.Tasks para .NET[aquí](https://purchase.aspose.com/buy).