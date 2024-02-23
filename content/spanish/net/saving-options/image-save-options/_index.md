---
title: Opciones para guardar imágenes de MS Project para Aspose.Tasks
linktitle: Opciones de guardado de imágenes para Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a guardar opciones de MS Project como imágenes usando Aspose.Tasks para .NET. Siga nuestra guía paso a paso para una integración perfecta.
type: docs
weight: 11
url: /es/net/saving-options/image-save-options/
---

## Introducción
En el mundo del desarrollo de software, manejar las tareas del proyecto de manera eficiente es crucial para una gestión exitosa del proyecto. Aspose.Tasks para .NET ofrece una poderosa solución para desarrolladores que trabajan con archivos de Microsoft Project, permitiéndoles manipular, convertir y administrar tareas de proyectos sin problemas dentro de sus aplicaciones .NET.
## Requisitos previos
Antes de sumergirse en el uso de Aspose.Tasks para .NET para guardar las opciones de MS Project como imágenes, asegúrese de cumplir con los siguientes requisitos previos:
### 1. Instale Aspose.Tasks para .NET
 Para comenzar, necesita tener Aspose.Tasks para .NET instalado en su entorno de desarrollo. Puedes descargar la biblioteca desde[sitio web](https://releases.aspose.com/tasks/net/) y siga las instrucciones de instalación proporcionadas.
### 2. Obtener una licencia (opcional)
 Si bien Aspose.Tasks para .NET se puede utilizar sin licencia en modo de evaluación, se recomienda obtener una licencia para obtener una funcionalidad completa y eliminar las limitaciones de evaluación. Puede adquirir una licencia del[pagina de compra](https://purchase.aspose.com/buy) u optar por un[licencia temporal](https://purchase.aspose.com/temporary-license/) con fines de prueba.
### 3. Conocimientos básicos de desarrollo de C# y .NET
Es necesaria una comprensión fundamental del lenguaje de programación C# y del marco .NET para seguir los ejemplos e integrar las funcionalidades de Aspose.Tasks en sus aplicaciones de manera efectiva.
## Importar espacios de nombres
Antes de comenzar a guardar las opciones de MS Project como imágenes usando Aspose.Tasks para .NET, asegurémonos de importar los espacios de nombres necesarios a nuestro proyecto C#:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Paso 1: configurar la ruta del directorio de documentos
Asegúrese de tener un directorio designado para sus documentos y establezca la ruta en consecuencia:
```csharp
String DataDir = "Your Document Directory";
```
## Paso 2: cargue el archivo de MS Project
 Inicializar un nuevo`Project` objeto cargando el archivo de MS Project:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Paso 3: definir las opciones para guardar imágenes
 Crear una instancia de`ImageSaveOptions` y especifique la configuración deseada:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## Paso 4: especifique las páginas para guardar
Si es necesario, especifique las páginas que se guardarán. En este ejemplo, estamos agregando la página 2:
```csharp
options.Pages.Add(2);
```
## Paso 5: guarde la imagen
Finalmente, guarde las páginas seleccionadas como una imagen con las opciones especificadas:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## Conclusión
Aspose.Tasks para .NET simplifica el proceso de trabajar con archivos de MS Project, permitiendo a los desarrolladores manipular las tareas del proyecto sin esfuerzo. Si sigue los pasos descritos en este tutorial, puede guardar de manera eficiente las opciones de MS Project como imágenes dentro de sus aplicaciones .NET.
## Preguntas frecuentes
### P1: ¿Puedo utilizar Aspose.Tasks para .NET sin licencia?
R: Sí, puede utilizar Aspose.Tasks para .NET sin licencia en modo de evaluación. Sin embargo, se recomienda obtener una licencia para obtener una funcionalidad completa y eliminar las limitaciones de evaluación.
### P2: ¿Cómo puedo obtener una licencia temporal para realizar pruebas?
 R: Puede obtener una licencia temporal para realizar pruebas en el[página de licencia temporal](https://purchase.aspose.com/temporary-license/).
### P3: ¿Aspose.Tasks para .NET es compatible con otros marcos .NET?
R: Sí, Aspose.Tasks para .NET es compatible con varios marcos .NET, incluidos .NET Core y .NET Standard.
### P4: ¿Puedo personalizar aún más las opciones para guardar imágenes?
R: Sí, puede personalizar las opciones para guardar imágenes según sus requisitos específicos, como ajustar el tamaño de la página, la resolución o el formato de salida.
### P5: ¿Dónde puedo encontrar soporte para Aspose.Tasks para .NET?
 R: Puede encontrar soporte y asistencia para Aspose.Tasks para .NET en el[foro](https://forum.aspose.com/c/tasks/15).