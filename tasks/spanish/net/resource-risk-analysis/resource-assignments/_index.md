---
title: Manejo de asignaciones de recursos de MS Project en Aspose.Tasks
linktitle: Manejo de asignaciones de recursos en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a manejar las asignaciones de recursos de MS Project de manera eficiente usando Aspose.Tasks para .NET. Este completo proporciona orientación paso a paso para los desarrolladores.
type: docs
weight: 11
url: /es/net/resource-risk-analysis/resource-assignments/
---
## Introducción
En este tutorial, profundizaremos en cómo manejar las asignaciones de recursos de Microsoft Project de manera eficiente usando Aspose.Tasks para .NET. Aspose.Tasks es una potente API que permite a los desarrolladores manipular archivos de Microsoft Project mediante programación. Si sigue estos pasos, aprenderá cómo administrar las asignaciones de recursos de manera efectiva dentro de sus aplicaciones .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

## Importar espacios de nombres
En primer lugar, debe importar los espacios de nombres necesarios para utilizar las funcionalidades de Aspose.Tasks en su proyecto .NET. Esto incluye:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
Ahora dividamos el ejemplo proporcionado en varios pasos para una comprensión integral de cómo manejar las asignaciones de recursos de MS Project usando Aspose.Tasks.
## Paso 1: configurar la configuración del proyecto y del calendario
Para comenzar, cree una nueva instancia de Proyecto y configure la configuración del calendario del proyecto:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## Paso 2: agregar una tarea al proyecto
A continuación, agregue una nueva tarea a la tarea raíz del proyecto:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## Paso 3: crear una asignación de recursos y generar datos en fases temporales
Ahora, cree una nueva asignación de recursos para la tarea y genere datos en fases temporales:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## Paso 4: dividir la tarea
Divida la tarea en varias partes proporcionando fechas de inicio y finalización:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## Paso 5: Establecer el contorno de trabajo
Establezca el tipo de contorno de trabajo para la tarea:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## Paso 6: guarde el proyecto
Finalmente, guarde el archivo del proyecto con los cambios realizados:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Conclusión
En conclusión, manejar las asignaciones de recursos de Microsoft Project utilizando Aspose.Tasks para .NET es un proceso sencillo. Si sigue los pasos descritos en este tutorial, podrá administrar de manera eficiente las asignaciones de recursos dentro de sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puede Aspose.Tasks manejar estructuras de proyectos complejas?
Sí, Aspose.Tasks proporciona funcionalidades integrales para manejar estructuras de proyectos complejas de manera eficiente.
### ¿Aspose.Tasks es compatible con diferentes versiones de Microsoft Project?
Sí, Aspose.Tasks admite varias versiones de Microsoft Project, lo que garantiza la compatibilidad en diferentes entornos.
### ¿Puedo personalizar las asignaciones de recursos según requisitos específicos?
Por supuesto, Aspose.Tasks ofrece amplias opciones de personalización para asignaciones de recursos para satisfacer las necesidades específicas del proyecto.
### ¿Aspose.Tasks admite la exportación de datos del proyecto a otros formatos?
Sí, Aspose.Tasks permite exportar datos del proyecto a varios formatos como XML, PDF y HTML, entre otros.
### ¿Hay soporte técnico disponible para los usuarios de Aspose.Tasks?
Sí, Aspose brinda soporte técnico dedicado a través de su foro y otros canales para ayudar a los usuarios con cualquier consulta o problema.