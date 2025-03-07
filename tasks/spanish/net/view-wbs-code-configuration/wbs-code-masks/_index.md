---
title: Configuración del código WBS paso a paso en Aspose.Tasks .NET
linktitle: Configuración de máscaras de código WBS en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore la configuración de máscaras de código WBS paso a paso en proyectos .NET utilizando Aspose.Tasks. Mejore las capacidades de gestión de proyectos sin esfuerzo.
weight: 14
url: /es/net/view-wbs-code-configuration/wbs-code-masks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuración del código WBS paso a paso en Aspose.Tasks .NET

## Introducción
Aspose.Tasks para .NET es una poderosa biblioteca que permite a los desarrolladores manipular de manera eficiente los datos de gestión de proyectos en aplicaciones .NET. En este tutorial, exploraremos el proceso de configuración de máscaras de código de estructura de desglose del trabajo (WBS) utilizando Aspose.Tasks.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
-  Aspose.Tasks para la biblioteca .NET: descargue e instale la biblioteca desde[Documentación de Aspose.Tasks para .NET](https://reference.aspose.com/tasks/net/).
- Entorno de desarrollo: asegúrese de tener configurado un entorno de desarrollo .NET que funcione.
- Directorio de documentos: elija un directorio en su sistema para almacenar los archivos del proyecto.
## Importar espacios de nombres
En su proyecto .NET, incluya los espacios de nombres necesarios para trabajar con Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Paso 1: crear una instancia de proyecto
Comience creando una nueva instancia de proyecto:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Paso 2: Definir la definición del código WBS
Configure la definición del código WBS para su proyecto:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Paso 3: agregar máscaras de código WBS
Defina máscaras de código WBS y agréguelas al proyecto:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Paso 4: crear tareas
Agregar tareas al proyecto:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Paso 5: recalcular
Vuelva a calcular el proyecto para garantizar que los códigos WBS se apliquen correctamente:
```csharp
project.Recalculate();
```
## Paso 6: Mostrar información de la máscara WBS
Envíe información sobre máscaras WBS a la consola:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Paso 7: guarde el proyecto
Guarde el proyecto con los códigos WBS agregados:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
¡Felicidades! Ha configurado correctamente las máscaras de código WBS en su proyecto Aspose.Tasks.
## Conclusión
En este tutorial, exploramos el proceso paso a paso de configurar máscaras de código WBS usando Aspose.Tasks para .NET. Esta potente biblioteca proporciona a los desarrolladores una forma sencilla de mejorar las capacidades de gestión de proyectos dentro de sus aplicaciones .NET.

## Preguntas frecuentes
### ¿Puedo utilizar Aspose.Tasks gratis?
 Aspose.Tasks ofrece una prueba gratuita, que puedes descargar[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar soporte adicional?
 Visita el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para el apoyo de la comunidad.
### ¿Cómo puedo obtener una licencia temporal?
 Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Hay documentación detallada disponible?
 Sí, la documentación completa está disponible.[aquí](https://reference.aspose.com/tasks/net/).
### ¿Dónde puedo comprar Aspose.Tasks?
 Comprar Aspose.Tasks[aquí](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
