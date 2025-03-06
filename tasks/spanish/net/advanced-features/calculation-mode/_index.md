---
title: Modo de cálculo en Aspose.Tasks
linktitle: Modo de cálculo en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar los modos de cálculo de manera efectiva en Aspose.Tasks para .NET para optimizar la programación de proyectos y las dependencias de tareas.
weight: 29
url: /es/net/advanced-features/calculation-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modo de cálculo en Aspose.Tasks

## Introducción

Aspose.Tasks para .NET es una potente API que permite a los desarrolladores trabajar con archivos de Microsoft Project mediante programación en sus aplicaciones .NET. Un aspecto crucial de trabajar con archivos de proyecto es la gestión de los modos de cálculo, que dictan cómo se calculan y actualizan las tareas y los cronogramas del proyecto. En este tutorial, profundizaremos en los diversos modos de cálculo admitidos por Aspose.Tasks para .NET y demostraremos cómo usarlos de manera efectiva.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Visual Studio: asegúrese de tener Visual Studio instalado en su sistema.
2.  Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/tasks/net/).
3. Comprensión básica de la programación en C#: familiarícese con los conceptos de programación en C#.

## Importar espacios de nombres

Antes de comenzar a trabajar con Aspose.Tasks para .NET, importemos los espacios de nombres necesarios:

```csharp
using Aspose.Tasks;
using System;


```

## Aplicar el modo de cálculo automático

### Paso 1: crear una nueva instancia de proyecto

 Inicializar un nuevo`Project` objeto y establecer su`CalculationMode` propiedad a`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Paso 2: establezca la fecha de inicio del proyecto y agregue tareas

Defina la fecha de inicio del proyecto y agréguele tareas.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Paso 3: vincular tareas

Establecer dependencias entre tareas.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Paso 4: verificar las fechas recalculadas

Compruebe si las fechas se han recalculado automáticamente.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Agregue más verificaciones según sea necesario
```

## Aplicar el modo de cálculo manual

### Paso 1: crear una nueva instancia de proyecto

 Inicializar un nuevo`Project` objeto y establecer su`CalculationMode` propiedad a`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Paso 2: establezca la fecha de inicio del proyecto y agregue tareas

Defina la fecha de inicio del proyecto y agréguele tareas.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Paso 3: verificar las propiedades de la tarea

Compruebe si las propiedades de la tarea están configuradas correctamente en modo manual.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Agregue más verificaciones según sea necesario
```

### Paso 4: Vincular tareas y verificar fechas

Vincula tareas y comprueba si sus fechas no se recalculan.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Aplicar el modo de cálculo Ninguno

### Paso 1: crear una nueva instancia de proyecto

 Inicializar un nuevo`Project` objeto y establecer su`CalculationMode` propiedad a`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Paso 2: agrega una nueva tarea

Agregue una nueva tarea al proyecto.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Paso 3: verificar las propiedades de la tarea

Compruebe si las propiedades de la tarea no se calculan automáticamente.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Agregue más verificaciones según sea necesario
```

## Conclusión

En este tutorial, exploramos los modos de cálculo disponibles en Aspose.Tasks para .NET y aprendimos cómo aplicarlos en escenarios prácticos. Ya sea que necesite un modo de cálculo automático, manual o sin cálculo, Aspose.Tasks brinda la flexibilidad para adaptarse a los requisitos de su proyecto.

## Preguntas frecuentes

### P1: ¿Puedo cambiar el modo de cálculo dinámicamente durante el tiempo de ejecución?

R1: Sí, puede cambiar el modo de cálculo de un proyecto en cualquier momento durante el tiempo de ejecución modificando el`CalculationMode` propiedad.

### P2: ¿Aspose.Tasks admite otros formatos de archivos de gestión de proyectos además de Microsoft Project?

R2: Aspose.Tasks se centra principalmente en los formatos de archivo de Microsoft Project, pero también admite otros formatos como Primavera P6 XML, Primavera DB y Asta Powerproject XML.

### P3: ¿Aspose.Tasks es adecuado para proyectos tanto de pequeña escala como de nivel empresarial?

R3: ¡Absolutamente! Aspose.Tasks está diseñado para satisfacer las necesidades de proyectos tanto de pequeña escala como de nivel empresarial con sus funciones integrales y API sólidas.

### P4: ¿Puedo integrar Aspose.Tasks con otras bibliotecas y marcos .NET?

R4: Sí, puede integrar Aspose.Tasks sin problemas con otras bibliotecas y marcos .NET para mejorar la funcionalidad de sus aplicaciones.

### P5: ¿Existe un foro comunitario o un canal de soporte disponible para los usuarios de Aspose.Tasks?

 R5: Sí, puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoyo y debates de la comunidad.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
