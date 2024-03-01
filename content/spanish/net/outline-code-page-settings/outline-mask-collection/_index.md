---
title: Domine las máscaras de esquema de MS Project con Aspose.Tasks
linktitle: Colección de máscaras de contorno en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a manipular máscaras de esquema de colección de MS Project usando Aspose.Tasks para .NET. Mejore la productividad con este completo tutorial.
type: docs
weight: 15
url: /es/net/outline-code-page-settings/outline-mask-collection/
---
## Introducción
¿Está buscando aprovechar el poder de las máscaras de esquema de Microsoft Project utilizando Aspose.Tasks para .NET? ¡Has venido al lugar correcto! En este completo tutorial, lo guiaremos a través del proceso paso a paso, asegurándonos de que obtenga una comprensión sólida de cómo manipular eficazmente las máscaras de contorno en sus proyectos. Ya sea que sea un desarrollador experimentado o recién esté comenzando, esta guía le brindará el conocimiento y las habilidades necesarias para optimizar su flujo de trabajo.
## Requisitos previos
Antes de sumergirse en este tutorial, asegúrese de cumplir con los siguientes requisitos previos:
### 1. Instalación de Aspose.Tasks para .NET
Asegúrese de tener Aspose.Tasks para .NET instalado en su entorno de desarrollo. Puede descargar la biblioteca desde el sitio web de Aspose.[aquí](https://releases.aspose.com/tasks/net/).
### 2. Conocimientos básicos de C# y .NET Framework
Familiarícese con el lenguaje de programación C# y .NET Framework, ya que este tutorial utilizará ambos.
### 3. Archivo de proyecto de Microsoft
Tenga un archivo de Microsoft Project (MPP) listo para realizar pruebas. Puede utilizar un archivo existente o crear uno nuevo para experimentar.
## Importar espacios de nombres
Comencemos importando los espacios de nombres necesarios a su proyecto C#. Este paso garantiza que tenga acceso a las clases y funcionalidades requeridas proporcionadas por Aspose.Tasks para .NET.

Agregue los siguientes espacios de nombres al comienzo de su archivo de código:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Ahora, dividamos el ejemplo proporcionado en varios pasos y expliquemos cada paso en detalle:
## Paso 1: Inicializar el objeto del proyecto
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 Aquí, creamos una nueva instancia del`Project` clase y cargue un archivo de Microsoft Project existente llamado "OutlineValues2010.mpp".
## Paso 2: Acceda a los códigos de esquema
```csharp
var outline = project.OutlineCodes[0];
```
Accedemos a los códigos de esquema del proyecto. Los códigos de esquema son campos personalizados en Microsoft Project que le permiten categorizar y organizar tareas.
## Paso 3: Borrar máscaras de contorno
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
Este paso garantiza que se borre cualquier máscara de contorno existente antes de continuar.
## Paso 4: crea máscaras de contorno
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
Creamos nuevas máscaras de contorno y especificamos sus tipos. En este ejemplo, creamos una máscara de contorno válida y otra incorrecta.
## Paso 5: insertar y editar máscaras
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
Aquí, insertamos una máscara incorrecta en la colección y editamos la longitud de una máscara usando su índice.
## Paso 6: quitar las máscaras
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
Eliminamos la máscara incorrecta de la colección según su índice.
## Paso 7: iterar sobre máscaras
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
Este bucle itera sobre cada máscara de contorno de la colección e imprime sus propiedades, como longitud, nivel, separador y tipo.
## Paso 8: copiar máscaras a otro proyecto
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
Finalmente, copiamos las máscaras de esquema de un proyecto a otro, asegurando la coherencia entre los diferentes proyectos.
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo manipular máscaras de esquema de colección de MS Project usando Aspose.Tasks para .NET. Al seguir este tutorial, ahora estará equipado con las habilidades para administrar de manera eficiente las máscaras de contorno en sus proyectos, mejorando en última instancia su productividad y flujo de trabajo.
## Preguntas frecuentes
### P1: ¿Puedo usar Aspose.Tasks para .NET con diferentes versiones de archivos de Microsoft Project?
R: Sí, Aspose.Tasks para .NET admite varias versiones de archivos de Microsoft Project, incluidos los formatos MPP, MPT y XML.
### P2: ¿Aspose.Tasks para .NET es compatible con .NET Core?
R: Sí, Aspose.Tasks para .NET es compatible con .NET Core, lo que le permite usarlo en aplicaciones multiplataforma.
### P3: ¿Puedo personalizar las propiedades de las máscaras de contorno según los requisitos de mi proyecto?
R: ¡Absolutamente! Puede personalizar las máscaras de contorno ajustando su longitud, nivel, separador y tipo para satisfacer las necesidades específicas de su proyecto.
### P4: ¿Aspose.Tasks para .NET proporciona documentación y soporte?
R: Sí, Aspose.Tasks para .NET ofrece documentación completa y soporte dedicado a través de su sitio web y[foros](https://forum.aspose.com/c/tasks/15).
### P5: ¿Hay una prueba gratuita disponible para Aspose.Tasks para .NET?
 R: Sí, puede acceder a una prueba gratuita de Aspose.Tasks para .NET desde su[sitio web](https://releases.aspose.com/tasks/net/). para explorar sus características y funcionalidades antes de realizar una compra.