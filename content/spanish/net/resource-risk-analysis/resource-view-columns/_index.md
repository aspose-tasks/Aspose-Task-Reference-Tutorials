---
title: Personalice las columnas de vista de recursos de MS Project en Aspose.Tasks
linktitle: Personalización de columnas de vista de recursos en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a personalizar las columnas de la vista de recursos de MS Project de manera eficiente usando Aspose.Tasks para .NET. Cree vistas personalizadas para una mejor gestión de proyectos.
type: docs
weight: 17
url: /es/net/resource-risk-analysis/resource-view-columns/
---
## Introducción
Aspose.Tasks para .NET es una potente API que permite a los desarrolladores trabajar con archivos de Microsoft Project mediante programación. Una tarea común en la gestión de proyectos es personalizar las vistas para mostrar información específica. En este tutorial, exploraremos cómo personalizar las columnas de la vista de recursos de MS Project usando Aspose.Tasks para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1.  Aspose.Tasks para la biblioteca .NET: puede descargarlo desde[aquí](https://releases.aspose.com/tasks/net/).
2. Archivo de Microsoft Project: tenga a mano un archivo de muestra de MS Project para realizar pruebas.
3. Entorno de desarrollo: un entorno de desarrollo configurado con .NET framework.
## Importar espacios de nombres
Primero, importemos los espacios de nombres necesarios a nuestro proyecto:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Paso 1: cargue el archivo del proyecto
Cargue el archivo de MS Project usando la API Aspose.Tasks:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Paso 2: obtener recursos y definir opciones
continuación, obtenga el recurso cuyas columnas de vista desea personalizar y defina las opciones para guardar PDF:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Paso 3: definir columnas personalizadas
Ahora, defina columnas personalizadas para la vista de recursos. Puede especificar varios campos e incluso utilizar delegados para cálculos personalizados:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Paso 4: iterar sobre las columnas
Itere sobre las columnas definidas y muestre sus propiedades:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Paso 5: guarde la vista personalizada
Finalmente, configure la vista personalizada y guárdela como un archivo PDF:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Si sigue estos pasos, puede personalizar de manera eficiente las columnas de la vista de recursos de MS Project usando Aspose.Tasks para .NET.
## Conclusión
Personalizar las columnas de la vista de recursos de MS Project es esencial para mostrar información relevante adaptada a las necesidades de su proyecto. Con Aspose.Tasks para .NET, esta tarea se vuelve sencilla y eficiente, lo que le permite crear vistas personalizadas sin esfuerzo.
## Preguntas frecuentes
### ¿Puedo personalizar vistas para otros elementos además de los recursos?
Sí, Aspose.Tasks también permite la personalización de tareas, asignaciones y otros elementos del proyecto.
### ¿Aspose.Tasks admite guardar vistas en formatos distintos de PDF?
Sí, puede guardar vistas en varios formatos, como XLSX, HTML e imágenes.
### ¿Es posible aplicar formato a la vista personalizada?
Por supuesto, Aspose.Tasks ofrece amplias opciones de formato para mejorar la apariencia de sus vistas personalizadas.
### ¿Puedo actualizar dinámicamente la vista personalizada según los cambios en los datos del proyecto?
Sí, puede actualizar y regenerar la vista personalizada cada vez que cambien los datos subyacentes del proyecto.
### ¿Aspose.Tasks admite el desarrollo multiplataforma?
Aspose.Tasks para .NET se dirige principalmente a plataformas .NET, pero también hay versiones disponibles para Java y otras plataformas.