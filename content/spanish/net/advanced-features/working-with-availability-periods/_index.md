---
title: Trabajar con períodos de disponibilidad en Aspose.Tasks
linktitle: Trabajar con períodos de disponibilidad en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda cómo administrar eficientemente los períodos de disponibilidad de recursos usando Aspose.Tasks para .NET. Este tutorial proporciona una guía paso a paso para trabajar con períodos de disponibilidad en sus proyectos .NET.
type: docs
weight: 17
url: /es/net/advanced-features/working-with-availability-periods/
---
## Introducción

En este tutorial, exploraremos cómo trabajar con períodos de disponibilidad en Aspose.Tasks para .NET. Los períodos de disponibilidad son cruciales para gestionar los recursos de manera eficiente en escenarios de gestión de proyectos. Le guiaremos a través del proceso paso a paso.

## Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. Visual Studio: instale Visual Studio o cualquier otro IDE preferido para el desarrollo de .NET.
2.  Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/tasks/net/).
3. Comprensión básica de la programación C#: será útil estar familiarizado con los conceptos básicos del lenguaje de programación C#.

## Importar espacios de nombres

Antes de profundizar en el código, asegúrese de importar los espacios de nombres necesarios:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Dividamos el código de ejemplo en varios pasos:

## Paso 1: crear una nueva instancia de proyecto

```csharp
var project = new Project();
```

Esta línea inicializa una nueva instancia de la clase Proyecto, que representa un proyecto en Aspose.Tasks.

## Paso 2: agregar un recurso

```csharp
var resource = project.Resources.Add("Work Resource");
```

Aquí, agregamos un nuevo recurso al proyecto con el nombre "Recurso de trabajo".

## Paso 3: definir los períodos de disponibilidad

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 llamamos al`GetPeriods()` Método para recuperar una colección de períodos de disponibilidad.

## Paso 4: agregar períodos de disponibilidad al recurso

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Repetimos la colección de períodos de disponibilidad obtenidos en el paso anterior y los agregamos al recurso.

## Paso 5: Mostrar detalles del período de disponibilidad

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Finalmente, recorremos los períodos de disponibilidad asociados con el recurso e imprimimos sus detalles, incluida la fecha de inicio, la fecha de finalización y las unidades disponibles.

## Conclusión

En este tutorial, aprendimos cómo trabajar con períodos de disponibilidad en Aspose.Tasks para .NET. Si sigue la guía paso a paso, podrá gestionar de manera eficiente la disponibilidad de recursos en sus aplicaciones de gestión de proyectos.

## Preguntas frecuentes

### P1: ¿Puedo utilizar Aspose.Tasks para .NET en proyectos comerciales?

 R1: Sí, Aspose.Tasks para .NET se puede utilizar en proyectos comerciales. Puedes comprar una licencia[aquí](https://purchase.aspose.com/buy).

### P2: ¿Hay una prueba gratuita disponible para Aspose.Tasks para .NET?

 R2: Sí, puede obtener una prueba gratuita de Aspose.Tasks para .NET[aquí](https://releases.aspose.com/).

### P3: ¿Dónde puedo encontrar documentación para Aspose.Tasks para .NET?

 A3: Puedes encontrar la documentación.[aquí](https://reference.aspose.com/tasks/net/).

### P4: ¿Cómo puedo obtener soporte para Aspose.Tasks para .NET?

 R4: Puede obtener soporte en el foro de la comunidad.[aquí](https://forum.aspose.com/c/tasks/15).

### P5: ¿Ofrecen licencias temporales de Aspose.Tasks para .NET?

 R5: Sí, hay licencias temporales disponibles[aquí](https://purchase.aspose.com/temporary-license/).