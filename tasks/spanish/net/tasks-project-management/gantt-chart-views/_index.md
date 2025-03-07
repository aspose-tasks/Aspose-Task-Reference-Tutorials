---
title: Dominar las vistas del diagrama de Gantt en Aspose.Tasks
linktitle: Vistas de diagrama de Gantt en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a personalizar las vistas de diagramas de Gantt en archivos de Microsoft Project usando Aspose.Tasks para .NET. Guía paso a paso para una gestión eficiente de proyectos.
weight: 22
url: /es/net/tasks-project-management/gantt-chart-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominar las vistas del diagrama de Gantt en Aspose.Tasks

## Introducción
Los diagramas de Gantt son herramientas poderosas que se utilizan en la gestión de proyectos para visualizar tareas, cronogramas y dependencias. Aspose.Tasks para .NET proporciona capacidades sólidas para trabajar con vistas de diagramas de Gantt en archivos de Microsoft Project. En este tutorial, exploraremos cómo utilizar Aspose.Tasks para manipular vistas de diagramas de Gantt, personalizar su apariencia y guardarlas como archivos PDF.
## Requisitos previos
Antes de continuar, asegúrese de cumplir con los siguientes requisitos previos:
### 1. Instalación de Aspose.Tasks para .NET
 Asegúrese de haber instalado Aspose.Tasks para .NET. Puedes descargar la biblioteca desde[aquí](https://releases.aspose.com/tasks/net/) y siga las instrucciones de instalación proporcionadas en la documentación.[aquí](https://reference.aspose.com/tasks/net/).
### 2. Archivo de proyecto de Microsoft
Prepare un archivo de Microsoft Project (`Project2.mpp`) que utilizará para trabajar con vistas de diagramas de Gantt.
### 3. Conocimientos básicos de C# y .NET Framework
Este tutorial supone que tiene conocimientos básicos del lenguaje de programación C# y del marco .NET.
## Importar espacios de nombres
Antes de comenzar a trabajar con vistas de diagramas de Gantt en Aspose.Tasks, debe importar los espacios de nombres necesarios a su código C#. Así es como puedes hacerlo:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

Dividamos el código de ejemplo proporcionado en varios pasos y expliquemos cada paso en detalle:
## Paso 1: cargue el archivo del proyecto
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Este paso implica cargar el archivo de Microsoft Project (`Project2.mpp` ) en una instancia del`Project` clase.
## Paso 2: establecer la fecha del estado
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Aquí, establecemos la fecha de estado del proyecto en su fecha de inicio.
## Paso 3: acceda a la vista del diagrama de Gantt
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Accedemos a la vista del diagrama de Gantt desde el proyecto. Aspose.Tasks permite acceder a vistas como diagrama de Gantt, diagrama de red y uso de tareas.
## Paso 4: Personaliza la vista del diagrama de Gantt
Ahora, personalicemos varios aspectos de la vista del diagrama de Gantt:
### Establecer redondeo de barras
```csharp
view.BarRounding = false;
```
Esto establece si las barras del diagrama de Gantt se redondearán al día más cercano.
### Establecer tamaño de barra
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
Esto determina la altura de las barras de Gantt en el gráfico.
### Ocultar barras acumulativas
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Especifica si las barras desplegables se ocultarán al expandir las tareas de resumen.
### Establecer color de tiempo no laborable
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Define el color del tiempo no laborable en el diagrama de Gantt.
### Barras de Gantt enrollables
```csharp
view.RollUpGanttBars = true;
```
Especifica si las barras del diagrama de Gantt deben acumularse.
### Mostrar divisiones de barra
```csharp
view.ShowBarSplits = true;
```
Determina si se deben mostrar las divisiones de tareas en el diagrama de Gantt.
### Mostrar dibujos
```csharp
view.ShowDrawings = true;
```
Especifica si se deben mostrar los dibujos en el diagrama de Gantt.
### Porcentaje de tamaño de escala de tiempo
```csharp
view.TimescaleSizePercentage = 10;
```
Establece un porcentaje para ajustar el espacio entre unidades en el nivel de escala de tiempo.
## Paso 5: guarde la vista del diagrama de Gantt como PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Finalmente, guardamos la vista del diagrama de Gantt personalizado como un archivo PDF.
## Conclusión
En este tutorial, aprendimos cómo trabajar con vistas de diagramas de Gantt en Aspose.Tasks para .NET. Si sigue los pasos proporcionados, podrá manipular y personalizar eficientemente los diagramas de Gantt según los requisitos de su proyecto.
## Preguntas frecuentes
### P: ¿Puedo personalizar aún más la apariencia de las barras del diagrama de Gantt?
R: Sí, Aspose.Tasks ofrece amplias opciones para personalizar la apariencia de las barras del diagrama de Gantt, incluidos colores, formas y tamaños.
### P: ¿Aspose.Tasks es compatible con diferentes versiones de archivos de Microsoft Project?
R: Sí, Aspose.Tasks admite varias versiones de archivos de Microsoft Project, incluidos los formatos MPP, MPT y XML.
### P: ¿Puedo exportar vistas de diagramas de Gantt a formatos distintos de PDF?
R: Por supuesto, Aspose.Tasks admite la exportación de vistas de diagramas de Gantt a múltiples formatos, incluidos PNG, JPEG y XPS.
### P: ¿Aspose.Tasks ofrece soporte para algoritmos complejos de programación de proyectos?
R: Sí, Aspose.Tasks proporciona algoritmos de programación avanzados para manejar cronogramas de proyectos complejos de manera efectiva.
### P: ¿Existe un foro comunitario donde pueda buscar ayuda o compartir mis experiencias con Aspose.Tasks?
 R: Sí, puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para interactuar con otros usuarios, hacer preguntas y encontrar soluciones a sus consultas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
