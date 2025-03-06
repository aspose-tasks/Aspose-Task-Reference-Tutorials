---
title: Dominar las opciones de guardado de MS Project para Aspose.Tasks
linktitle: Opciones generales de guardado para Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a guardar archivos de MS Project de manera eficiente usando Aspose.Tasks para .NET. Personalice las opciones de salida sin esfuerzo para sus proyectos.
weight: 17
url: /es/net/saving-options/general-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominar las opciones de guardado de MS Project para Aspose.Tasks

## Introducción
Aspose.Tasks para .NET ofrece potentes funciones para manipular archivos de Microsoft Project mediante programación. En este tutorial, profundizaremos en las complejidades de guardar archivos de MS Project usando varias opciones proporcionadas por Aspose.Tasks. Específicamente, nos centraremos en las opciones generales de guardado disponibles para Aspose.Tasks, lo que le permitirá adaptar la salida a sus requisitos específicos.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1.  Instalación de Aspose.Tasks para .NET: Descargue e instale Aspose.Tasks para .NET desde[enlace de descarga](https://releases.aspose.com/tasks/net/).
2. Comprensión básica de .NET Framework: es beneficiosa la familiaridad con los conceptos de programación de .NET.

## Importando espacios de nombres
Antes de profundizar en el código, asegúrese de importar los espacios de nombres necesarios:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Paso 1: cargue el archivo del proyecto
En primer lugar, debe cargar el archivo de MS Project usando Aspose.Tasks:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## Paso 2: definir opciones de guardar
 Defina las opciones de guardado según sus requisitos. En este ejemplo, estamos usando`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Paso 3: personalizar las columnas de vista
Puede personalizar las columnas de la vista, como el diagrama de Gantt, la vista de recursos y la vista de tareas. A continuación se explica cómo agregar columnas a cada uno:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Paso 4: guarde el proyecto con opciones
Finalmente, guarde el proyecto con las opciones especificadas:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Conclusión
Dominar las opciones generales de guardado de MS Project con Aspose.Tasks para .NET le permite personalizar de manera eficiente el formato de salida de acuerdo con las necesidades de su proyecto.
## Preguntas frecuentes
### P: ¿Aspose.Tasks es compatible con diferentes versiones de archivos de MS Project?
R: Sí, Aspose.Tasks admite varias versiones de archivos de MS Project, lo que garantiza la compatibilidad entre diferentes entornos.
### P: ¿Puedo probar Aspose.Tasks antes de comprarlo?
 R: Sí, puedes explorar Aspose.Tasks con una prueba gratuita disponible[aquí](https://releases.aspose.com/).
### P: ¿Dónde puedo encontrar documentación para Aspose.Tasks?
 R: Puede encontrar documentación detallada[aquí](https://reference.aspose.com/tasks/net/), que proporciona orientación completa sobre el uso de las funciones de Aspose.Tasks.
### P: ¿Cómo puedo obtener licencias temporales para Aspose.Tasks?
 R: Las licencias temporales están disponibles para fines de evaluación.[aquí](https://purchase.aspose.com/temporary-license/).
### P: ¿Dónde puedo buscar ayuda para consultas relacionadas con Aspose.Tasks?
 R: Puedes unirte al foro de la comunidad Aspose.Tasks[aquí](https://forum.aspose.com/c/tasks/15)para obtener ayuda de expertos y compañeros desarrolladores.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
