---
title: Dominar los datos del proyecto con Aspose.Tasks
linktitle: Trabajar con datos del proyecto en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a manipular datos de Microsoft Project usando Aspose.Tasks en .NET. Cree tareas, agregue recursos y guarde proyectos con facilidad.
type: docs
weight: 16
url: /es/net/project-management-integration/project-data/
---
## Introducción
En este tutorial, exploraremos cómo trabajar con datos de Microsoft Project utilizando la biblioteca Aspose.Tasks para .NET. Aspose.Tasks proporciona potentes funciones para manipular archivos de proyectos, incluida la creación de tareas, la adición de recursos, la configuración de propiedades y el guardado de proyectos en varios formatos.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1.  Instalación de la biblioteca Aspose.Tasks: descargue e instale la biblioteca Aspose.Tasks desde[aquí](https://releases.aspose.com/tasks/net/).
2. Entorno de desarrollo: asegúrese de tener configurado un entorno de desarrollo .NET.
3. Conocimientos básicos de C#: será beneficiosa la familiaridad con el lenguaje de programación C#.

## Importar espacios de nombres
Antes de trabajar con Aspose.Tasks, importe los espacios de nombres necesarios a su proyecto:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Paso 1: inicializar el objeto del proyecto
```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Esta línea inicializa una nueva instancia del`Project` clase, que representa un archivo de Microsoft Project.
## Paso 2: establecer las propiedades del proyecto
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Estas líneas demuestran cómo configurar propiedades del proyecto, como el formato de trabajo y el modo de creación de tareas.
## Paso 3: agregar tareas
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Aquí, se agrega una nueva tarea denominada "Tarea 1" a la tarea raíz del proyecto.
## Paso 4: configurar las propiedades de la tarea
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Estas líneas establecen la fecha de inicio, la duración y la fecha de finalización de la "Tarea 1".
## Paso 5: Agregar recursos
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
Esta parte demuestra cómo agregar un recurso de trabajo al proyecto.
## Paso 6: Asignar recursos a las tareas
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Estas líneas muestran cómo asignar el recurso de trabajo agregado previamente a la "Tarea 1" con fechas específicas de inicio, trabajo y finalización.
## Paso 7: Guardar proyecto
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Finalmente, el proyecto se guarda en formato de archivo XML de Microsoft Project.

## Conclusión
En este tutorial, aprendimos cómo trabajar con datos de Microsoft Project usando la biblioteca Aspose.Tasks en .NET. Siguiendo la guía paso a paso, puede manipular archivos de proyecto, agregar tareas, recursos, asignar recursos a tareas y guardar proyectos en varios formatos.
## Preguntas frecuentes
### P: ¿Puede Aspose.Tasks manejar estructuras de proyectos complejas?
R: Sí, Aspose.Tasks brinda soporte integral para estructuras de proyectos complejas, lo que le permite administrar tareas, recursos y asignaciones de manera eficiente.
### P: ¿Aspose.Tasks es compatible con diferentes versiones de Microsoft Project?
R: Aspose.Tasks admite una amplia gama de versiones de Microsoft Project, lo que garantiza la compatibilidad en diferentes entornos.
### P: ¿Puedo integrar Aspose.Tasks con otras bibliotecas .NET?
R: Por supuesto, Aspose.Tasks se integra perfectamente con otras bibliotecas .NET, brindando flexibilidad en sus proyectos de desarrollo.
### P: ¿Aspose.Tasks ofrece soporte para algoritmos de programación de proyectos?
R: Sí, Aspose.Tasks incluye algoritmos de programación avanzados para ayudarlo a optimizar los cronogramas del proyecto y la utilización de recursos.
### P: ¿Existe un foro comunitario para usuarios de Aspose.Tasks?
 R: Sí, puede encontrar recursos útiles e interactuar con otros usuarios de Aspose.Tasks en[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).