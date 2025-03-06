---
title: Personalice las columnas del diagrama de Gantt con Aspose.Tasks
linktitle: Columnas del diagrama de Gantt en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a personalizar las columnas del diagrama de Gantt en Aspose.Tasks para .NET para mostrar información de tareas específicas de manera eficiente.
weight: 21
url: /es/net/tasks-project-management/gantt-chart-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Personalice las columnas del diagrama de Gantt con Aspose.Tasks

## Introducción
Los diagramas de Gantt son una herramienta fundamental en la gestión de proyectos, ya que proporcionan una representación visual de tareas, cronogramas y recursos. Aspose.Tasks para .NET ofrece potentes capacidades para manipular diagramas de Gantt, incluida la personalización de columnas para mostrar información de tareas específicas. En este tutorial, exploraremos cómo trabajar con columnas del diagrama de Gantt usando Aspose.Tasks para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1.  Instalación: Aspose.Tasks para .NET instalado en su sistema. Si no, descárgalo e instálalo desde[aquí](https://releases.aspose.com/tasks/net/).
2. Entorno de desarrollo .NET: conocimiento práctico de C# y el marco .NET.
3. Archivo de proyecto de muestra: tenga un archivo de Microsoft Project de muestra (`.mpp`) útil para experimentar. Si no tiene uno, puede crear un proyecto simple en MS Project y guardarlo.

## Importar espacios de nombres
Primero, necesita importar los espacios de nombres necesarios para trabajar con Aspose.Tasks para .NET:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Paso 1: cargue el archivo del proyecto
 Cargue el archivo del proyecto usando el`Project` clase proporcionada por Aspose.Tasks:
```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Paso 2: definir las columnas del diagrama de Gantt
Defina las columnas que desea mostrar en el diagrama de Gantt. Puede especificar campos integrados o crear campos personalizados:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## Paso 3: iterar sobre columnas
Itere sobre las columnas definidas para acceder a sus propiedades y mostrar información:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## Paso 4: guarde el diagrama de Gantt en CSV
Guarde el diagrama de Gantt con columnas definidas en un archivo CSV:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Si sigue estos pasos, podrá trabajar eficazmente con las columnas del diagrama de Gantt en Aspose.Tasks para .NET, lo que le permitirá personalizar y mostrar la información de las tareas según sea necesario.

## Conclusión
Dominar la manipulación de las columnas del diagrama de Gantt en Aspose.Tasks para .NET abre infinitas posibilidades para adaptar los elementos visuales de gestión de proyectos a sus necesidades específicas. Si sigue los pasos descritos en este tutorial, podrá manejar de manera eficiente la información de las tareas y mejorar la claridad y organización del proyecto.
## Preguntas frecuentes
### P: ¿Puedo crear columnas personalizadas en Aspose.Tasks para .NET?
R: Sí, puede definir columnas personalizadas para mostrar atributos de tareas específicos según los requisitos de su proyecto.
### P: ¿Aspose.Tasks para .NET es compatible con todas las versiones de archivos de Microsoft Project?
R: Aspose.Tasks para .NET admite varias versiones de archivos de Microsoft Project, lo que garantiza la compatibilidad entre diferentes entornos de proyectos.
### P: ¿Cómo puedo manejar estructuras de proyectos complejas con Aspose.Tasks para .NET?
R: Aspose.Tasks para .NET proporciona API y funciones integrales para administrar estructuras de proyectos complejas, ofreciendo flexibilidad y escalabilidad.
### P: ¿Existe alguna limitación en la cantidad de columnas que puedo agregar a un diagrama de Gantt?
R: Aspose.Tasks para .NET ofrece amplias opciones de personalización, lo que le permite agregar una cantidad significativa de columnas a los diagramas de Gantt sin limitaciones.
### P: ¿Dónde puedo encontrar soporte y recursos adicionales para Aspose.Tasks para .NET?
R: Puede explorar la documentación, los foros comunitarios y los canales de soporte proporcionados por Aspose.Tasks para .NET para acceder a recursos y asistencia integrales.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
