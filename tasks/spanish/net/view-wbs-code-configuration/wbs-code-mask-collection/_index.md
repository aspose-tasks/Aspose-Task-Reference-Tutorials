---
title: Dominar las máscaras de código WBS con Aspose.Tasks para .NET
linktitle: Colección de máscaras de código WBS en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Mejore la gestión de proyectos con Aspose.Tasks para .NET. Aprenda a crear, administrar y transferir máscaras de código WBS sin esfuerzo en este completo tutorial.
weight: 15
url: /es/net/view-wbs-code-configuration/wbs-code-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominar las máscaras de código WBS con Aspose.Tasks para .NET

## Introducción
En el dinámico mundo de la gestión de proyectos, organizar las tareas de manera eficiente es crucial. Aspose.Tasks para .NET proporciona una solución poderosa para administrar códigos de estructura de desglose del trabajo del proyecto (WBS) sin esfuerzo. En este tutorial, profundizaremos en la Colección de máscaras de código WBS, explorando cómo implementarlas y manipularlas usando Aspose.Tasks para .NET.
## Requisitos previos
Antes de embarcarnos en este viaje de codificación, asegúrese de cumplir con los siguientes requisitos previos:
- Conocimiento práctico del lenguaje de programación C#.
-  Aspose.Tasks para .NET instalado en su entorno de desarrollo. Si no, descárgalo[aquí](https://releases.aspose.com/tasks/net/).
- Un editor de código como Visual Studio para una experiencia de codificación perfecta.
## Importar espacios de nombres
Para comenzar, importemos los espacios de nombres necesarios:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Inicializar el proyecto y la definición del código WBS
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Definir máscaras de código WBS
Borre las máscaras de código existentes y agregue otras nuevas:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Mostrar información de máscaras de código
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Agregar tareas al proyecto
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Recuperar información de la tarea
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Manipular máscaras de código
Elimine una máscara de código y asegúrese de que se elimine:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Copie máscaras de código a otro proyecto
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Mostrar máscaras de código en otro proyecto
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Agregar tareas al otro proyecto
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Mostrar códigos WBS en el otro proyecto
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Conclusión
Con Aspose.Tasks para .NET, administrar códigos WBS se convierte en una tarea sencilla. Este tutorial cubrió la creación, manipulación y transferencia de máscaras de código WBS, brindándole una guía completa para mejorar su experiencia de gestión de proyectos.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks para .NET con otros lenguajes de programación?
R: Aspose.Tasks admite principalmente lenguajes .NET, pero puede explorar opciones de interoperabilidad con otros lenguajes.
### P: ¿Existe una versión de prueba disponible de Aspose.Tasks para .NET?
 R: Sí, puedes descargar la versión de prueba.[aquí](https://releases.aspose.com/).
### P: ¿Cómo busco ayuda o informo problemas con Aspose.Tasks para .NET?
 R: Visita el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoyo y discusiones.
### P: ¿Cuál es el propósito de los códigos WBS en la gestión de proyectos?
R: Los códigos WBS ayudan a organizar y estructurar las tareas del proyecto de forma jerárquica, proporcionando un enfoque sistemático para la planificación del proyecto.
### P: ¿Puedo personalizar el formato de los códigos WBS en Aspose.Tasks para .NET?
R: Por supuesto, usted tiene control total sobre el formato y la estructura de los códigos WBS utilizando Aspose.Tasks para .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
