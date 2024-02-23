---
title: Colección de períodos de disponibilidad en Aspose.Tasks
linktitle: Colección de períodos de disponibilidad en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar los períodos de disponibilidad de los recursos en Aspose.Tasks para .NET. Este tutorial paso a paso lo guía para agregar, actualizar y eliminar períodos de disponibilidad, lo que garantiza una planificación eficaz de los recursos del proyecto.
type: docs
weight: 18
url: /es/net/advanced-features/availability-period-collection/
---
## Introducción

En este tutorial, exploraremos cómo trabajar con la colección del período de disponibilidad de un recurso en Aspose.Tasks para .NET. Gestionar los períodos de disponibilidad es crucial para la gestión de proyectos, ya que nos permite definir cuándo están disponibles los recursos para las tareas dentro de un proyecto.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Visual Studio: asegúrese de tener Visual Studio instalado en su sistema.
2.  Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/tasks/net/).
3. Comprensión básica: familiaridad con C# y .NET framework.

## Importar espacios de nombres

Primero, necesitamos importar los espacios de nombres necesarios a nuestro proyecto:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Dividamos el código de ejemplo en varios pasos y comprendamos cada parte:

## Paso 1: inicializar el proyecto y el recurso

```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Aquí, cargamos un archivo de proyecto y obtenemos un recurso específico por su ID.

## Paso 2: borrar los períodos de disponibilidad existentes

```csharp
resource.AvailabilityPeriods.Clear();
```

Limpiamos cualquier período de disponibilidad existente asociado con el recurso.

## Paso 3: agregar períodos de disponibilidad

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Recorremos una colección de períodos de disponibilidad y los agregamos al recurso.

## Paso 4: Inserte un nuevo período de disponibilidad

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Creamos un nuevo período de disponibilidad para el año 2013 y lo insertamos en la colección.

## Paso 5: Mostrar los períodos de disponibilidad

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Imprimimos el recuento y los detalles de cada período de disponibilidad asociado al recurso.

## Paso 6: copiar los períodos de disponibilidad a otro recurso

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Copiamos los periodos de disponibilidad de un recurso a otro.

## Paso 7: actualizar y eliminar períodos de disponibilidad

```csharp
// Actualizar unidades disponibles para un período específico
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Eliminar un período específico
otherResource.AvailabilityPeriods.Remove(period2013);
```

Actualizamos las unidades disponibles para un período y eliminamos períodos específicos de la colección.

## Conclusión

En este tutorial, aprendimos cómo trabajar con colecciones de períodos de disponibilidad en Aspose.Tasks para .NET. Gestionar la disponibilidad de recursos es esencial para una planificación y ejecución efectiva de proyectos.

## Preguntas frecuentes

### P1: ¿Puedo agregar campos personalizados a los períodos de disponibilidad?

R1: No, los períodos de disponibilidad en Aspose.Tasks para .NET no admiten campos personalizados.

### P2: ¿Los períodos de disponibilidad están vinculados a tareas específicas?

R2: No, los períodos de disponibilidad están asociados a los recursos y definen cuándo están disponibles para las tareas en general.

### P3: ¿Puedo importar períodos de disponibilidad de fuentes externas?

R3: Sí, puede importar períodos de disponibilidad de varias fuentes de datos utilizando Aspose.Tasks para las API de .NET.

### P4: ¿Cómo manejo los períodos de disponibilidad superpuestos?

R4: Aspose.Tasks para .NET no proporciona mecanismos integrados para manejar períodos superpuestos. Es posible que necesite implementar una lógica personalizada para gestionar dichos escenarios.

### P5: ¿Existe un límite en la cantidad de períodos de disponibilidad que puede tener un recurso?

R5: No existe un límite predefinido para la cantidad de períodos de disponibilidad que puede tener un recurso, pero el rendimiento puede degradarse con una gran cantidad de períodos.