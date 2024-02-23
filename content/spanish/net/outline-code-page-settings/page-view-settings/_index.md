---
title: Personalice la configuración de vista de página de MS Project en Aspose.Tasks
linktitle: Configurar los ajustes de vista de página en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a configurar los ajustes de vista de página en Aspose.Tasks para .NET para adaptar el formato de impresión de sus documentos de Microsoft Project.
type: docs
weight: 21
url: /es/net/outline-code-page-settings/page-view-settings/
---
## Introducción
Microsoft Project es una poderosa herramienta para la gestión de proyectos, pero a veces es necesario personalizar la forma en que se ve e imprime su proyecto. Con Aspose.Tasks para .NET, puede configurar fácilmente los ajustes de vista de página para satisfacer sus requisitos específicos. En este tutorial, lo guiaremos a través del proceso paso a paso.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1.  Aspose.Tasks para .NET: asegúrese de haber descargado e instalado la biblioteca Aspose.Tasks para .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/net/).
2. Archivo de Microsoft Project: tenga listo un archivo de Microsoft Project para el que desee configurar los ajustes de vista de página.

## Importar espacios de nombres
Primero, necesita importar los espacios de nombres necesarios para trabajar con Aspose.Tasks en su proyecto .NET.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Paso 1: cargue el archivo del proyecto
 Comience cargando su archivo de Microsoft Project en una instancia del`Project` clase.
```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Paso 2: establecer el recuento de las primeras columnas
Especifique el número de primeras columnas que se imprimirán en todas las páginas.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## Paso 3: imprimir notas
Elija si desea imprimir notas junto con el proyecto.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Paso 4: Ajustar la escala de tiempo al final de la página
Decida si desea ajustar la escala de tiempo al final de una página al imprimir.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Paso 5: imprimir todas las columnas de la hoja
Especifique si se imprimirán todas las columnas de la hoja de una vista.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Paso 6: imprima páginas en blanco
Elija si desea imprimir páginas en blanco de una vista.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Paso 7: imprima las primeras columnas en todas las páginas
Establezca si se imprimirá un número específico de primeras columnas en todas las páginas.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Paso 8: guarde el proyecto con los ajustes configurados
Finalmente, guarde el proyecto con los ajustes de vista de página configurados, especificando el formato de salida, como PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## Conclusión
Configurar los ajustes de vista de página de Microsoft Project en Aspose.Tasks para .NET es sencillo y le permite adaptar el formato de impresión a sus necesidades exactas. Si sigue los pasos descritos en este tutorial, puede asegurarse de que los documentos de su proyecto se presenten exactamente como se requiere.
## Preguntas frecuentes
### P: ¿Puedo configurar los ajustes de vista de página para otros formatos de archivo además de PDF?
R: Sí, Aspose.Tasks admite varios formatos de archivo para guardar proyectos, incluidos XLSX, MPP y HTML.
### P: ¿Existe alguna limitación en la cantidad de columnas que puedo imprimir?
R: Aspose.Tasks le permite personalizar la cantidad de columnas que se imprimirán según sus requisitos.
### P: ¿Puedo aplicar diferentes configuraciones de vista de página para diferentes proyectos?
R: Sí, puedes ajustar la configuración de vista de página de forma independiente para cada archivo de proyecto con el que trabajes.
### P: ¿Aspose.Tasks es compatible con todas las versiones de Microsoft Project?
R: Aspose.Tasks ofrece compatibilidad con Microsoft Project 2003 y versiones posteriores.
### P: ¿Dónde puedo encontrar más ayuda o soporte para Aspose.Tasks?
 R: Puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15)para cualquier consulta o problema que encuentre durante el uso.