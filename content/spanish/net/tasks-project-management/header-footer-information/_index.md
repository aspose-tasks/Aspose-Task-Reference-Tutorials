---
title: Extraiga información de encabezado y pie de página con Aspose.Tasks
linktitle: Información de encabezado y pie de página en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a extraer información de encabezado y pie de página de archivos de MS Project usando Aspose.Tasks para .NET. Solución fácil, eficiente y amigable para los desarrolladores.
type: docs
weight: 29
url: /es/net/tasks-project-management/header-footer-information/
---
## Introducción
Aspose.Tasks para .NET es una poderosa biblioteca que permite a los desarrolladores manipular archivos de Microsoft Project con facilidad. En este tutorial, aprenderemos cómo recuperar información de encabezado y pie de página de archivos de MS Project usando Aspose.Tasks.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Visual Studio: instale Visual Studio en su sistema.
2.  Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/tasks/net/).
3. Conocimientos básicos de C#: Familiaridad con el lenguaje de programación C#.

## Importar espacios de nombres
Primero, necesita importar los espacios de nombres necesarios a su proyecto C#. Esto le permitirá acceder a las clases y métodos proporcionados por la biblioteca Aspose.Tasks.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Paso 1: inicializar el objeto del proyecto
 Para comenzar, necesita inicializar un`Project` objeto cargando un archivo de MS Project existente.
```csharp
// La ruta al directorio de documentos.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Paso 2: recuperar la información del encabezado y pie de página
 Una vez que haya cargado el archivo del proyecto, puede recuperar la información del encabezado y pie de página usando el`PageInfo` propiedad.
```csharp
var info = project.DefaultView.PageInfo;
// Información del encabezado
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Información de pie de página
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Si sigue estos sencillos pasos, puede recuperar fácilmente información de encabezado y pie de página de archivos de MS Project utilizando Aspose.Tasks para .NET.

## Conclusión
En este tutorial, exploramos cómo extraer información de encabezado y pie de página de archivos de MS Project usando Aspose.Tasks para .NET. Esta potente biblioteca simplifica la tarea de trabajar con archivos de proyecto en aplicaciones C# y proporciona a los desarrolladores herramientas sólidas de manipulación.
### Preguntas frecuentes
### ¿Puedo modificar la información del encabezado y pie de página usando Aspose.Tasks?
Sí, puede modificar la información del encabezado y pie de página mediante programación utilizando Aspose.Tasks para .NET.
### ¿Aspose.Tasks admite otros formatos de archivos de proyecto además de MS Project?
Sí, Aspose.Tasks admite varios formatos de archivos de proyecto, incluidos MPP, XML y MPX.
### ¿Hay una prueba gratuita disponible para Aspose.Tasks?
 Sí, puede descargar una prueba gratuita de Aspose.Tasks desde[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar documentación para Aspose.Tasks?
 Puede encontrar la documentación para Aspose.Tasks[aquí](https://reference.aspose.com/tasks/net/).
### ¿Cómo puedo obtener soporte para Aspose.Tasks?
 Puede obtener soporte para Aspose.Tasks visitando el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).