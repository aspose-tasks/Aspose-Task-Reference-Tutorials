---
title: Tipo de cálculo en Aspose.Tasks
linktitle: Tipo de cálculo en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a personalizar los cálculos de valores en proyectos .NET con el tipo de cálculo en la biblioteca Aspose.Tasks.
weight: 30
url: /es/net/advanced-features/calculation-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tipo de cálculo en Aspose.Tasks

## Introducción

En este tutorial, exploraremos la función Tipo de cálculo en Aspose.Tasks para .NET. Aspose.Tasks es una poderosa biblioteca que permite a los desarrolladores .NET trabajar con archivos de Microsoft Project sin la necesidad de tener Microsoft Project instalado en sus sistemas. El tipo de cálculo nos permite definir cómo se calculan los valores para las tareas y las tareas de resumen dentro de un proyecto.

## Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. Conocimientos básicos de C# y .NET framework.
2. Visual Studio instalado en su sistema.
3.  Aspose.Tasks para la biblioteca .NET instalada. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/net/).
4.  Acceso a la documentación de Aspose.Tasks para .NET como referencia, disponible[aquí](https://reference.aspose.com/tasks/net/).

## Importar espacios de nombres

Antes de profundizar en el ejemplo, asegúrese de importar los espacios de nombres necesarios:

```csharp
using Aspose.Tasks;
using System;


```

## Paso 1: crear un nuevo proyecto

Primero, creemos un nuevo objeto de proyecto:

```csharp
var project = new Project();
```

## Paso 2: agregar una tarea

Ahora, agreguemos una tarea a nuestro proyecto:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Paso 3: Definir el tipo de cálculo para un atributo extendido

Crearemos una definición de atributo extendida con el Tipo de cálculo establecido en Fórmula:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Paso 4: Definir el tipo de cálculo para las filas de resumen

A continuación, crearemos otra definición de atributo extendido donde los valores para las tareas de resumen se calculan utilizando el tipo de resumen Promedio:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Conclusión

En este tutorial, exploramos cómo trabajar con el tipo de cálculo en Aspose.Tasks para .NET. Al definir tipos de cálculo para atributos extendidos, podemos personalizar cómo se calculan los valores para tareas y tareas resumidas dentro de un proyecto, brindando mayor flexibilidad y control.

## Preguntas frecuentes

### P1: ¿Qué es el tipo de cálculo en Aspose.Tasks?

A1: El tipo de cálculo en Aspose.Tasks determina cómo se calculan los valores para las tareas y las tareas de resumen dentro de un proyecto, ofreciendo opciones como Fórmula y Resumen.

### P2: ¿Cómo configuro el tipo de cálculo para un atributo extendido?

R2: Puede establecer el tipo de cálculo para un atributo extendido definiendo su propiedad Tipo de cálculo en consecuencia.

### P3: ¿Puedo personalizar el tipo de cálculo para las filas de resumen de un proyecto?

R3: Sí, Aspose.Tasks le permite especificar el tipo de cálculo para las filas de resumen, lo que le permite personalizar los cálculos de valores según sus requisitos.

### P4: ¿Existen diferentes tipos de resumen disponibles para los cálculos de tareas resumidas?

R4: Sí, Aspose.Tasks proporciona varios tipos de resumen, como promedio, suma y recuento, para calcular los valores de las tareas de resumen.

### P5: ¿Dónde puedo encontrar más recursos sobre Aspose.Tasks para .NET?

 R5: Puede explorar la documentación y los foros de soporte comunitario disponibles en[Aspose.Tareas para .NET](https://reference.aspose.com/tasks/net/) para orientación y asistencia integral.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
