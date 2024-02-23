---
title: Guardar archivos de MS Project en varios formatos en Aspose.Tasks
linktitle: Guardar archivos en varios formatos en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a guardar archivos de MS Project en varios formatos usando Aspose.Tasks para .NET. Pasos sencillos para una gestión eficiente de proyectos.
type: docs
weight: 17
url: /es/net/rate-recurring-tasks/save-file-formats/
---
## Introducción
En este tutorial, exploraremos cómo guardar archivos de Microsoft Project en varios formatos usando Aspose.Tasks para .NET. Aspose.Tasks es una potente API que permite a los desarrolladores manipular y gestionar archivos de proyectos mediante programación.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1.  Aspose.Tasks para .NET: Descargue e instale Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/tasks/net/).
2. Entorno de desarrollo: configure un entorno de desarrollo .NET, como Visual Studio.
3. Comprensión básica de C#: será beneficiosa la familiaridad con el lenguaje de programación C#.

## Importar espacios de nombres
Asegúrese de importar los espacios de nombres necesarios al principio de su archivo C#:
```csharp

using Aspose.Tasks.Saving;
```
## Paso 1: crear un objeto de proyecto
Primero, cree un objeto de Proyecto y cargue su archivo de Microsoft Project.
```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Paso 2: guardar el proyecto en formato CSV
Ahora, guardemos el proyecto en formato CSV. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Paso 3: explore otros formatos
 Aspose.Tasks admite varios formatos para guardar archivos de proyectos, como XML, PDF, XLSX y más. Puede explorar estos formatos simplemente cambiando el`SaveFileFormat` parámetros en el`Save` método.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Siguiendo estos pasos, puede guardar fácilmente archivos de Microsoft Project en varios formatos usando Aspose.Tasks para .NET.

## Conclusión
En este tutorial, aprendimos cómo guardar archivos de MS Project en diferentes formatos usando Aspose.Tasks para .NET. Aspose.Tasks simplifica el proceso de manipulación de archivos de proyecto mediante programación, ofreciendo flexibilidad y eficiencia a los desarrolladores.
## Preguntas frecuentes
### P: ¿Aspose.Tasks es compatible con todas las versiones de Microsoft Project?
R: Aspose.Tasks admite los formatos Microsoft Project 2003 XML, Microsoft Project 2007 MPP y Microsoft Project 2010 MPP.
### P: ¿Puedo probar Aspose.Tasks antes de comprarlo?
 R: Sí, puedes descargar una prueba gratuita desde[aquí](https://releases.aspose.com/).
### P: ¿Cómo puedo obtener soporte para Aspose.Tasks?
 R: Puede obtener soporte en el foro de la comunidad Aspose.Tasks.[aquí](https://forum.aspose.com/c/tasks/15).
### P: ¿Hay licencias temporales disponibles para Aspose.Tasks?
 R: Sí, hay licencias temporales disponibles para fines de evaluación. puedes conseguir uno[aquí](https://purchase.aspose.com/temporary-license/).
### P: ¿Cuál es el precio de Aspose.Tasks?
 R: La información sobre precios se puede encontrar en la página de compra de Aspose.Tasks[aquí](https://purchase.aspose.com/buy).