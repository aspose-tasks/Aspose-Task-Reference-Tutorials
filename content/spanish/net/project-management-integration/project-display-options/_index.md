---
title: Configurar las opciones de visualización de MS Project en Aspose.Tasks
linktitle: Configurar las opciones de visualización del proyecto en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a configurar las opciones de visualización de MS Project mediante programación utilizando Aspose.Tasks para .NET. Personaliza la apariencia de tu proyecto sin esfuerzo.
type: docs
weight: 17
url: /es/net/project-management-integration/project-display-options/
---
## Introducción
Microsoft Project ofrece una gran cantidad de opciones de visualización para personalizar la apariencia de su proyecto. Aspose.Tasks para .NET proporciona un marco sólido para manipular estas opciones mediante programación. En este tutorial, exploraremos cómo configurar las opciones de visualización de MS Project usando Aspose.Tasks.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener lo siguiente:
1.  Aspose.Tasks para .NET: descargue e instale la biblioteca desde[aquí](https://releases.aspose.com/tasks/net/).
2. Archivo de Microsoft Project: tenga un archivo de MS Project válido (.mpp) listo para aplicar las opciones de visualización.
3. Conocimientos básicos de C#: se requiere familiaridad con el lenguaje de programación C#.

## Importando espacios de nombres
En primer lugar, asegúrese de importar los espacios de nombres necesarios en su código C#:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Paso 1: cargue el archivo del proyecto
 Cargue el archivo de MS Project usando el`Project` clase proporcionada por Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Paso 2: configurar las opciones de visualización
Ahora, configuremos varias opciones de visualización disponibles en MS Project:
### Deshabilitar las advertencias de programación de tareas
Para deshabilitar las advertencias por conflictos de programación con tareas programadas manualmente (disponible para Project 2010 y versiones posteriores):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Agregar espacio antes de la etiqueta
Configure para agregar un espacio antes del valor numérico y la abreviatura de hora:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Configurar la visualización de etiquetas para unidades de tiempo
Personalice cómo se muestran las diferentes unidades de tiempo:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Mostrar tarea de resumen del proyecto
Muestra información resumida sobre todo el proyecto en una sola fila:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Habilitar sugerencias de programación de tareas
Permitir mostrar sugerencias para conflictos de programación con tareas programadas manualmente:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Subrayar hipervínculos
Establecer para subrayar hipervínculos dentro del proyecto:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Paso 3: guarde el proyecto
Finalmente, guarde el proyecto con las opciones de visualización aplicadas:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Conclusión
En este tutorial, aprendimos cómo configurar las opciones de visualización de MS Project usando Aspose.Tasks para .NET. Con estas capacidades, puede personalizar de manera eficiente la apariencia de los archivos de su proyecto mediante programación.
## Preguntas frecuentes
### P: ¿Puedo aplicar estas opciones de visualización solo a tareas específicas?
R: Sí, puede aplicar selectivamente opciones de visualización a tareas individuales utilizando la API Aspose.Tasks.
### P: ¿Estas opciones de visualización afectan los datos subyacentes del proyecto?
R: No, estas opciones sólo modifican la representación visual del proyecto y no alteran los datos subyacentes.
### P: ¿Estas opciones de visualización son compatibles con todas las versiones de Microsoft Project?
R: No, algunas opciones pueden ser específicas de determinadas versiones de MS Project. Consulte la documentación para obtener detalles de compatibilidad.
### P: ¿Puedo revertir las opciones de visualización a la configuración predeterminada?
R: Sí, puede restablecer las opciones de visualización a sus valores predeterminados utilizando la API Aspose.Tasks.
### P: ¿Existe alguna limitación para personalizar las opciones de visualización mediante programación?
R: Si bien Aspose.Tasks proporciona amplias capacidades de personalización, es posible que no se pueda acceder a ciertas opciones de visualización mediante programación debido a limitaciones en el formato de archivo de MS Project.