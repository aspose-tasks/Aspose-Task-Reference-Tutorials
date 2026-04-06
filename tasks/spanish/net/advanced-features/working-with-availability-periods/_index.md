---
date: 2026-04-06
description: Aprenda cómo agregar un recurso al proyecto y establecer períodos de
  disponibilidad del recurso usando Aspose.Tasks para .NET. Guía paso a paso para
  gestionar los calendarios de recursos.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Trabajando con períodos de disponibilidad en Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Agregar recurso al proyecto y establecer disponibilidad en Aspose.Tasks
url: /es/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Añadir recurso al proyecto y establecer disponibilidad en Aspose.Tasks

## Introducción

En este tutorial aprenderás **cómo añadir un recurso al proyecto** y luego definir sus períodos de disponibilidad usando la biblioteca Aspose.Tasks .NET. Gestionar los calendarios de recursos es esencial para horarios de proyecto realistas, y los pasos a continuación te guiarán a través de todo el proceso—desde crear una instancia de proyecto hasta imprimir los detalles de cada período.

## Respuestas rápidas
- **¿Cuál es el objetivo principal?** Añadir un recurso a un proyecto y configurar sus períodos de disponibilidad.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks para .NET.  
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia comercial.  
- **¿Versiones de .NET compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Tiempo de implementación?** Normalmente menos de 15 minutos para escenarios básicos.

## ¿Qué es “añadir recurso al proyecto”?

Añadir un recurso a un proyecto crea un marcador de posición para una persona, equipo o material que puede asignarse a tareas. Una vez que el recurso existe, puedes **establecer la disponibilidad del recurso**, definir su calendario de trabajo y permitir que el planificador respete esas restricciones.

## ¿Por qué configurar el horario de trabajo y los períodos de disponibilidad?

- **Planificación precisa:** Las tareas se programan solo cuando el recurso está realmente libre.  
- **Control de costos:** Las unidades de disponibilidad reflejan el esfuerzo a tiempo parcial, ayudándote a calcular correctamente los costos laborales.  
- **Nivelación de recursos:** El motor puede nivelar automáticamente las sobreasignaciones cuando conoce el calendario de cada recurso.

## Requisitos previos

1. Visual Studio (o cualquier IDE compatible con .NET).  
2. Aspose.Tasks para .NET – descargar desde [aquí](https://releases.aspose.com/tasks/net/).  
3. Conocimientos básicos de C#.

## Importar espacios de nombres

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## ¿Cómo añadir recurso al proyecto?

### Paso 1: Crear una nueva instancia `Project`

```csharp
var project = new Project();
```

Este objeto representa todo el archivo del proyecto en memoria.

### Paso 2: Añadir un recurso al proyecto

```csharp
var resource = project.Resources.Add("Work Resource");
```

La llamada crea un **recurso** llamado *Work Resource* que luego puedes adjuntar a tareas.

### Paso 3: Definir períodos de disponibilidad

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` es un método auxiliar (implementación no mostrada) que devuelve una colección de objetos `AvailabilityPeriod`. Cada período especifica una fecha de inicio, una fecha de fin y las unidades (porcentaje del esfuerzo a tiempo completo) en que el recurso está disponible.

### Paso 4: Añadir los períodos al recurso

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Aquí **establecemos la disponibilidad del recurso** recorriendo la colección y añadiendo cada período al calendario del recurso.

### Paso 5: Mostrar los detalles de disponibilidad

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

La salida de consola te permite verificar que los períodos se almacenaron correctamente.

## Errores comunes y consejos

- **Precisión de fechas:** `AvailableFrom` y `AvailableTo` son valores `DateTime`; asegúrate de establecerlos a medianoche si deseas períodos de día completo.  
- **Rango de unidades:** Los valores válidos son 0‑100 %; los valores fuera de este rango lanzarán una excepción.  
- **Períodos superpuestos:** Los períodos superpuestos se fusionan automáticamente, pero es más claro mantenerlos distintos.

## Preguntas frecuentes

### P1: ¿Puedo usar Aspose.Tasks para .NET en proyectos comerciales?
R1: Sí, Aspose.Tasks para .NET puede usarse en proyectos comerciales. Puedes comprar una licencia [aquí](https://purchase.aspose.com/buy).

### P2: ¿Hay una prueba gratuita disponible para Aspose.Tasks para .NET?
R2: Sí, puedes obtener una prueba gratuita de Aspose.Tasks para .NET [aquí](https://releases.aspose.com/).

### P3: ¿Dónde puedo encontrar la documentación de Aspose.Tasks para .NET?
R3: Puedes encontrar la documentación [aquí](https://reference.aspose.com/tasks/net/).

### P4: ¿Cómo puedo obtener soporte para Aspose.Tasks para .NET?
R4: Puedes obtener soporte del foro de la comunidad [aquí](https://forum.aspose.com/c/tasks/15).

### P5: ¿Ofrecen licencias temporales para Aspose.Tasks para .NET?
R5: Sí, las licencias temporales están disponibles [aquí](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2026-04-06  
**Probado con:** Aspose.Tasks para .NET (última versión estable)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}