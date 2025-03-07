---
title: Configure las opciones de MS Project XLSX en Aspose.Tasks para .NET
linktitle: Configuración de opciones XLSX en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a configurar las opciones de MS Project XLSX en Aspose.Tasks para .NET. Personalice columnas, codificación y más sin esfuerzo.
weight: 11
url: /es/net/file-format-options/configuring-xlsx-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configure las opciones de MS Project XLSX en Aspose.Tasks para .NET

## Introducción
Microsoft Project (MS Project) es una poderosa herramienta para la gestión de proyectos y Aspose.Tasks para .NET proporciona una integración perfecta para trabajar con archivos de MS Project mediante programación. En este tutorial, recorreremos el proceso de configuración de las opciones de MS Project XLSX usando Aspose.Tasks para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
### 1. Aspose.Tasks para .NET instalado
 Asegúrese de tener Aspose.Tasks para .NET instalado en su entorno de desarrollo. Si no, puedes descargarlo desde[Página de descarga de Aspose.Tasks para .NET](https://releases.aspose.com/tasks/net/).
### 2. Comprensión básica de C# y .NET Framework
Se requiere familiaridad con el lenguaje de programación C# y el marco .NET para seguir este tutorial.
### 3. Archivo de proyecto de Microsoft
Tenga listo un archivo de Microsoft Project (MPP) que desee configurar y guardar como un archivo XLSX.

## Importando espacios de nombres
Para comenzar, importe los espacios de nombres necesarios:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Paso 1: cargar el proyecto
```csharp
var project = new Project("YourProjectFile.mpp");
```
Cargue el archivo de Microsoft Project que desea configurar.
## Paso 2: definir XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Crear una instancia de`XlsxOptions` para configurar los ajustes para guardar como XLSX.
## Paso 3: agregar columnas del diagrama de Gantt
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Agregue las columnas deseadas del diagrama de Gantt a las opciones.
## Paso 4: Agregar columnas de vista de recursos
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Incluya las columnas deseadas para la vista de recursos en las opciones.
## Paso 5: Agregar columnas de vista de tareas
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Agregue las columnas deseadas para la vista de tareas en las opciones.
## Paso 6: configurar la codificación
```csharp
options.Encoding = Encoding.Unicode;
```
Establezca la codificación para el archivo de salida.
## Paso 7: guarde el proyecto como XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
Guarde el proyecto con las opciones configuradas como un archivo XLSX.

## Conclusión
En este tutorial, aprendimos cómo configurar las opciones de MS Project XLSX usando Aspose.Tasks para .NET. Si sigue estos pasos, puede personalizar el formato de salida según sus requisitos, mejorando la flexibilidad y usabilidad de su flujo de trabajo de gestión de proyectos.
## Preguntas frecuentes

### P: ¿Puedo configurar diferentes columnas para el diagrama de Gantt, la vista de recursos y la vista de tareas por separado?

R: Sí, puede personalizar las columnas de forma independiente para cada vista utilizando Aspose.Tasks para .NET.

### P: ¿Existe una versión de prueba disponible antes de comprar Aspose.Tasks para .NET?

 R: Sí, puedes descargar una prueba gratuita desde[Página de lanzamientos de Aspose.Tasks para .NET](https://releases.aspose.com/).

### P: ¿Cómo puedo obtener soporte si encuentro algún problema o tengo preguntas durante la implementación?

 R: Puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener ayuda de la comunidad y del equipo de soporte de Aspose.

### P: ¿Puedo generar archivos XLSX con Aspose.Tasks para .NET en plataformas que no sean Windows?

R: Aspose.Tasks para .NET está diseñado principalmente para plataformas Windows, pero puede explorar opciones de compatibilidad para otras plataformas.

### P: ¿Hay opciones de licencia temporal disponibles para fines de prueba?

 R: Sí, puede obtener una licencia temporal del[Página de licencia temporal de Aspose.Tasks](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
