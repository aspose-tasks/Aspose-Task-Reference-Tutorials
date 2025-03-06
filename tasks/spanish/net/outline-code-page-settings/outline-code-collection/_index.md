---
title: Colección MS Project de códigos de esquema en Aspose.Tasks
linktitle: Colección de códigos de esquema en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a recopilar códigos de esquema de Microsoft Project utilizando Aspose.Tasks para .NET. Este completo tutorial proporciona instrucciones paso a paso.
weight: 11
url: /es/net/outline-code-page-settings/outline-code-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Colección MS Project de códigos de esquema en Aspose.Tasks

## Introducción
En este tutorial, exploraremos cómo recopilar códigos de esquema de Microsoft Project usando Aspose.Tasks para .NET. Dividiremos el proceso en instrucciones paso a paso para garantizar la claridad y la comprensión.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Visual Studio: instale Visual Studio en su sistema.
2.  Aspose.Tasks para .NET: Descargue e instale Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/tasks/net/).
3. Comprensión básica de la programación en C#: la familiaridad con C# será beneficiosa.

## Importar espacios de nombres
En primer lugar, importe los espacios de nombres necesarios para acceder a la funcionalidad Aspose.Tasks en su proyecto C#.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Paso 1: cargue el archivo del proyecto
 Comience cargando el archivo de Microsoft Project usando el`Project` clase.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Paso 2: recopilar códigos de esquema
Cree un recopilador para recopilar los códigos de esquema de las tareas del proyecto.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Paso 3: iterar a través de tareas y códigos de esquema
Repita las tareas recopiladas y los códigos de esquema, imprimiendo sus detalles.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Paso 4: Agregar una definición de código de esquema personalizado
Agregue una definición de código de esquema personalizado al proyecto.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Paso 5: crear e insertar código de esquema
Cree un código de esquema e insértelo en una tarea.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Paso 6: manipular códigos de esquema
Manipule los códigos de esquema según sea necesario, como insertarlos, eliminarlos o borrarlos.
```csharp
// Ejemplo de manipulación
// ...
// Insertar código con 2 en la posición correcta
task.OutlineCodes.Insert(2, code2);
// Compruebe si se insertó el código
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Conclusión
En este tutorial, aprendimos cómo recopilar códigos de esquema de Microsoft Project usando Aspose.Tasks para .NET. Si sigue estos pasos, podrá gestionar eficazmente los códigos de esquema dentro de sus proyectos, mejorando la organización y la claridad.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks para .NET con otros lenguajes de programación?
R: Sí, Aspose.Tasks para .NET se dirige principalmente a la plataforma .NET, pero también brinda soporte para otros lenguajes de programación a través de Aspose.Tasks para la nube.
### P: ¿Existe alguna limitación en el tamaño de los archivos de proyecto que Aspose.Tasks para .NET puede manejar?
R: Aspose.Tasks para .NET puede manejar archivos de proyecto grandes de manera eficiente, pero el rendimiento puede variar según la complejidad y el tamaño del archivo.
### P: ¿Aspose.Tasks para .NET es compatible con las últimas versiones de Microsoft Project?
R: Sí, Aspose.Tasks para .NET admite varias versiones de Microsoft Project, incluidas las más recientes.
### P: ¿Puedo personalizar el formato de salida cuando trabajo con Aspose.Tasks para .NET?
R: Por supuesto, Aspose.Tasks para .NET ofrece amplias opciones para personalizar el formato de salida según sus requisitos.
### P: ¿Dónde puedo encontrar soporte o recursos adicionales para Aspose.Tasks para .NET?
 R: Puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para cualquier ayuda o consulta sobre Aspose.Tasks para .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
