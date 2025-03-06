---
title: Configuración de niveles de escala de tiempo del diagrama de Gantt en Aspose.Tasks
linktitle: Configuración de niveles de escala de tiempo en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore Aspose.Tasks para .NET para configurar niveles de escala de tiempo en su vista de diagrama de Gantt para una visualización precisa de la línea de tiempo del proyecto. #Aspose.Tareas #Proyecto MS
weight: 16
url: /es/net/text-view-configuration/timescale-tiers/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuración de niveles de escala de tiempo del diagrama de Gantt en Aspose.Tasks

## Introducción
En el panorama dinámico de la gestión de proyectos, la visualización efectiva es crucial para comprender los cronogramas y los plazos. Aspose.Tasks para .NET proporciona un potente conjunto de herramientas y, en este tutorial, exploraremos cómo configurar niveles de escala de tiempo para una representación óptima en la vista del diagrama de Gantt. Siga estas instrucciones paso a paso para mejorar la visualización de su proyecto.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener lo siguiente:
- Conocimientos básicos de C# y .NET.
-  Aspose.Tasks para la biblioteca .NET instalada. Puedes descargarlo[aquí](https://releases.aspose.com/tasks/net/).
- Un entorno de desarrollo configurado para el desarrollo de aplicaciones .NET.
## Importar espacios de nombres
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Ahora, analicemos cada paso del ejemplo proporcionado.
## Paso 1: inicializar el proyecto y agregar enlaces de tareas
```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Aquí, creamos un proyecto y establecemos vínculos de tareas entre la "Tarea 1" y la "Tarea 2".
## Paso 2: configurar la vista del diagrama de Gantt
```csharp
var view = (GanttChartView)project.DefaultView;
```
Acceda a la vista del diagrama de Gantt para personalizarla.
## Paso 3: Ajustar el nivel de escala de tiempo medio
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Personalice el nivel de escala de tiempo medio para mostrar semanas con etiquetas y alineación específicas.
## Paso 4: agregar el nivel de escala de tiempo superior
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Agregue un nivel de escala de tiempo superior para representar meses.
## Paso 5: personalice las fechas del nivel medio
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Personalice las etiquetas del mes para una mejor visualización.
## Paso 6: Establecer la escala de tiempo del proyecto
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Defina la escala de tiempo del proyecto para controlar el cronograma general.
## Paso 7: guarde el proyecto con una escala de tiempo personalizada
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Guarde el proyecto con la configuración de escala de tiempo definida.
## Conclusión
En conclusión, configurar niveles de escala de tiempo en Aspose.Tasks para .NET permite una representación más personalizada y visualmente atractiva de las líneas de tiempo del proyecto. Estos pasos le permiten crear una vista de diagrama de Gantt que satisfaga con precisión sus necesidades de gestión de proyectos.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Tasks con otras bibliotecas .NET?
Sí, Aspose.Tasks se integra perfectamente con otras bibliotecas .NET, ofreciendo flexibilidad en su pila de desarrollo.
### ¿Hay una licencia temporal disponible para fines de prueba?
 Sí, puedes obtener una licencia temporal.[aquí](https://purchase.aspose.com/temporary-license/) Para evaluar.
### ¿Existen opciones de personalización adicionales para la vista del diagrama de Gantt?
Por supuesto, Aspose.Tasks ofrece amplias opciones de personalización para la vista del diagrama de Gantt para adaptarse a diversos requisitos del proyecto.
### ¿Puedo renderizar escalas de tiempo en diferentes formatos?
Ciertamente, puede explorar varios formatos y estilos para que la representación de escala de tiempo se adapte mejor al contexto de su proyecto.
### ¿Existe un foro comunitario para soporte de Aspose.Tasks?
 Sí, visita el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoyo y debates de la comunidad.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
