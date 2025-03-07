---
title: Administrar la colección de atributos de MS Project en Aspose.Tasks
linktitle: Gestión de la colección de atributos extendidos en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda cómo administrar eficientemente los atributos extendidos de MS Project usando Aspose.Tasks para .NET. Manipule sin problemas los atributos de las tareas con una guía paso a paso.
weight: 12
url: /es/net/tasks-project-management/extended-attribute-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Administrar la colección de atributos de MS Project en Aspose.Tasks

## Introducción
¿Está buscando administrar de manera eficiente los atributos extendidos de MS Project usando Aspose.Tasks para .NET? En este tutorial, lo guiaremos a través del proceso paso a paso. ¡Vamos a sumergirnos!
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Visual Studio: instale Visual Studio en su sistema.
2.  Aspose.Tasks para .NET: Descargue e instale Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/tasks/net/).
3. Conocimientos básicos de C#: familiarícese con los conceptos básicos del lenguaje de programación C#.

## Importar espacios de nombres
Comience importando los espacios de nombres necesarios a su proyecto:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Paso 1: cargar el archivo del proyecto
Primero, cargue el archivo de MS Project usando el siguiente fragmento de código:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Paso 2: acceder a la tarea y a los atributos extendidos
Acceda a una tarea específica y sus atributos extendidos:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Paso 3: borrar los atributos extendidos
Borre los atributos extendidos existentes si es necesario:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Paso 4: crear definiciones de atributos extendidos
Cree definiciones para nuevos atributos extendidos:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Paso 5: iterar sobre los atributos extendidos de la tarea
Iterar sobre los atributos extendidos de la tarea:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Paso 6: agregar atributos extendidos
Agregue nuevos atributos extendidos a la tarea:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Paso 7: trabajar con atributos extendidos
Realice operaciones en atributos extendidos según sea necesario.
## Paso 8: eliminar los atributos extendidos
Eliminar atributos extendidos por índice o condicionalmente:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Paso 9: copiar atributos a otra tarea
Copie atributos a otra tarea dentro del mismo proyecto o de uno diferente:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Conclusión
La gestión de colecciones de atributos extendidos de MS Project se vuelve perfecta con Aspose.Tasks para .NET. Si sigue los pasos descritos en este tutorial, podrá manejar eficientemente atributos extendidos, mejorando sus capacidades de gestión de proyectos.
## Preguntas frecuentes
### P: ¿Puedo manipular atributos extendidos en varios proyectos?
R: Sí, puede copiar atributos extendidos entre tareas en diferentes proyectos usando Aspose.Tasks para .NET.
### P: ¿Existen limitaciones en la cantidad de atributos extendidos por tarea?
R: Aspose.Tasks para .NET no impone limitaciones inherentes en la cantidad de atributos extendidos por tarea.
### P: ¿Puedo crear campos de atributos extendidos personalizados?
R: ¡Absolutamente! Aspose.Tasks para .NET le permite definir campos de atributos extendidos personalizados adaptados a los requisitos de su proyecto.
### P: ¿Aspose.Tasks para .NET admite la lectura y escritura en archivos de MS Project de varias versiones?
R: Sí, Aspose.Tasks para .NET admite formatos de archivo de MS Project en diferentes versiones.
### P: ¿Existe una versión de prueba disponible de Aspose.Tasks para .NET?
 R: Sí, puedes descargar una prueba gratuita desde[aquí](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
