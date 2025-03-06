---
title: Usando el algoritmo de árbol en Aspose.Tasks
linktitle: Usando el algoritmo de árbol en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a manipular eficazmente las jerarquías de tareas en sus proyectos .NET utilizando el algoritmo de árbol de Aspose.Tasks.
type: docs
weight: 13
url: /es/net/advanced-concepts/tree-algorithm/
---
## Introducción

Aspose.Tasks para .NET proporciona potentes funcionalidades para trabajar con tareas, recursos y cronogramas de gestión de proyectos. Una de esas características es el algoritmo de árbol, que permite a los usuarios manipular jerarquías de tareas de manera eficiente. En este tutorial, exploraremos cómo utilizar el algoritmo de árbol en Aspose.Tasks para .NET para recopilar trabajo común y actualizar valores de trabajo dentro de un proyecto.

## Requisitos previos

Antes de comenzar, asegúrese de contar con los siguientes requisitos previos:

1. Visual Studio: asegúrese de tener Visual Studio instalado en su sistema.
2.  Aspose.Tasks para .NET: Descargue e instale Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/tasks/net/).
3. Comprensión básica de C#: se requiere familiaridad con el lenguaje de programación C# para seguir los ejemplos.

## Importar espacios de nombres

En su proyecto C#, importe los espacios de nombres necesarios para trabajar con las funcionalidades de Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Ahora, dividamos cada ejemplo en varios pasos:

## Paso 1: cargar el archivo del proyecto

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Cargue el archivo del proyecto en la memoria usando el`Project` clase.

## Paso 2: definir la jerarquía de tareas

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Defina la jerarquía de tareas agregando tareas principales y secundarias.

## Paso 3: establecer las propiedades de la tarea

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Establezca propiedades como la fecha de inicio, la duración y la fecha de finalización de las tareas.

## Paso 4: agregar recurso

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Agregue recursos al proyecto y asígnelos a tareas según sea necesario.

## Paso 5: aplicar el algoritmo de árbol

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Inicializar el`WorkAccumulator` clase y aplicar el algoritmo de árbol para reunir trabajo común.

## Paso 6: Actualizar el trabajo de la tarea

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Actualice los valores de trabajo para las tareas según la información recopilada.

## Conclusión

En este tutorial, aprendimos cómo utilizar el algoritmo de árbol en Aspose.Tasks para .NET para manipular jerarquías de tareas de manera efectiva. Siguiendo la guía paso a paso, podrá administrar de manera eficiente las tareas y recursos dentro de sus proyectos.

## Preguntas frecuentes

### P1: ¿Qué es Aspose.Tasks para .NET?

R1: Aspose.Tasks para .NET es una potente API que permite a los desarrolladores manipular archivos de Microsoft Project mediante programación utilizando C#.

### P2: ¿Puedo descargar una prueba gratuita de Aspose.Tasks para .NET?

 R2: Sí, puede descargar una prueba gratuita de Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/).

### P3: ¿Dónde puedo encontrar documentación para Aspose.Tasks para .NET?

 R3: Puede encontrar la documentación de Aspose.Tasks para .NET[aquí](https://reference.aspose.com/tasks/net/).

### P4: ¿Cómo puedo obtener soporte para Aspose.Tasks para .NET?

 R4: Para obtener soporte relacionado con Aspose.Tasks para .NET, puede visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P5: ¿Existe una licencia temporal disponible para realizar pruebas?

 R5: Sí, puede obtener una licencia temporal para realizar pruebas en[aquí](https://purchase.aspose.com/temporary-license/).