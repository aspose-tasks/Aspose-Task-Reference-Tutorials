---
date: 2026-04-06
description: Aprenda a eliminar todas las líneas base y a gestionar colecciones de
  líneas base en Aspose.Tasks para .NET con ejemplos de código paso a paso.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Eliminar todas las líneas base con la colección de líneas base de Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Eliminar todas las líneas base con la colección de líneas base de Aspose.Tasks
url: /es/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Eliminar todas las líneas base con la colección Baseline de Aspose.Tasks

## Introducción

Aspose.Tasks para .NET le permite manipular archivos de Microsoft Project directamente desde sus aplicaciones .NET. Una de las características más potentes es la capacidad de **eliminar todas las líneas base** para un recurso, lo cual es esencial cuando necesita restablecer los datos de seguimiento de un proyecto o iniciar un nuevo período de línea base. En este tutorial recorreremos todo el proceso —desde cargar un archivo de proyecto hasta eliminar cada línea base asociada a un recurso específico— usando explicaciones claras y conversacionales y código C# listo para ejecutar.

## Respuestas rápidas
- **¿Qué hace “eliminar todas las líneas base”?** Elimina cada registro de línea base almacenado para un recurso seleccionado, borrando los datos históricos de costo y trabajo.  
- **¿Por qué necesitaría esto?** Para restablecer el seguimiento después de un cambio importante en el proyecto o cuando las líneas base originales ya no son relevantes.  
- **¿Qué biblioteca proporciona esta capacidad?** Aspose.Tasks para .NET.  
- **¿Necesito una licencia?** Se requiere una licencia válida de Aspose.Tasks para uso en producción; hay una prueba gratuita disponible.  
- **¿El código es compatible con .NET 6+?** Sí, la API funciona con .NET Framework 4.5+, .NET Core 3.1+ y .NET 5/6.

## ¿Qué es una línea base y por qué eliminar todas las líneas base?

Una línea base captura el plan original de costo, trabajo y cronograma en un momento específico. A lo largo de la vida de un proyecto puede crear varias líneas base (Línea base 1, Línea base 2, etc.) para comparar el progreso real con diferentes instantáneas de planificación. Sin embargo, existen escenarios —como un re‑alcance del proyecto o un nuevo comienzo— donde mantener esas líneas base históricas genera confusión. Eliminar todas las líneas base le brinda una hoja limpia, permitiéndole establecer nuevas líneas base que reflejen la realidad actual.

## Requisitos previos

Antes de sumergirnos en el código, asegúrese de contar con:

1. **Visual Studio** – cualquier edición reciente (Community, Professional o Enterprise).  
2. **Aspose.Tasks para .NET** – descárguelo desde el [enlace de descarga](https://releases.aspose.com/tasks/net/).  
3. **Conocimientos básicos de C#** – debe sentirse cómodo con variables, bucles y salida a consola.  
4. **Un archivo Microsoft Project** (`.mpp`) – se usará un archivo de ejemplo llamado *WorkWithBaselineCollection.mpp* en los ejemplos.

## Importar espacios de nombres

Primero, incluya los espacios de nombres necesarios para que el compilador sepa dónde encontrar las clases que utilizaremos.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Paso 1: Cargar el archivo de proyecto

Comenzamos cargando un archivo de Project existente. Ajuste `DataDir` para que apunte a la carpeta que contiene su archivo `.mpp`.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Paso 2: Obtener el recurso objetivo

Para la demostración obtenemos el recurso con UID = 1. En un escenario real, localizaría el recurso por nombre u otro identificador.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Paso 3: Mostrar la información de líneas base existentes

Antes de eliminar cualquier cosa, es útil ver qué líneas base están actualmente asociadas al recurso. Esto le brinda confianza de que está eliminando los datos correctos.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Paso 4: Recorrer todas las líneas base

Aquí recorremos cada línea base, imprimiendo métricas clave como costo, trabajo y valor ganado (BCWP/BCWS). Este paso es opcional pero útil para registros o auditorías.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Eliminar todas las líneas base

Ahora realizamos la acción principal: **eliminar todas las líneas base** para el recurso seleccionado. Primero copiamos la colección a una lista para evitar modificar la colección mientras iteramos, luego eliminamos cada línea base una por una.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Después de que este bloque se ejecute, `resource.Baselines.Count` será `0`, confirmando que todos los registros de líneas base han sido eliminados.

## Problemas comunes y consejos

- **NullReferenceException** – Asegúrese de que el archivo de proyecto realmente contenga el recurso que está apuntando; de lo contrario `GetByUid` devolverá `null`.  
- **Licenciamiento** – Sin una licencia válida de Aspose.Tasks verá una marca de agua en la salida y funcionalidad limitada.  
- **Rendimiento** – Para proyectos muy grandes, considere iterar con `Parallel.ForEach` para acelerar el proceso de eliminación, pero recuerde que la colección subyacente no es segura para hilos.

## Preguntas frecuentes

**P: ¿Puede Aspose.Tasks manejar archivos de proyecto grandes?**  
**R:** Sí, Aspose.Tasks está optimizado para el rendimiento y puede procesar archivos `.mpp` de varios gigabytes de manera eficiente.

**P: ¿La biblioteca es compatible con todas las versiones de Microsoft Project?**  
**R:** Aspose.Tasks es compatible con Project 2000 hasta Project 2024, cubriendo tanto los formatos `.mpp` antiguos como los archivos basados en XML más recientes.

**P: ¿Puedo personalizar las líneas base antes de eliminarlas?**  
**R:** Por supuesto. Puede leer o modificar cualquier propiedad de la línea base (costo, trabajo, fechas) antes de decidir eliminarla.

**P: ¿Aspose.Tasks funciona en plataformas en la nube?**  
**R:** Sí, la API se ejecuta en cualquier entorno compatible con .NET, incluidos Azure App Service, AWS Lambda (a través de .NET Core) y contenedores Docker.

**P: ¿Dónde puedo preguntar a la comunidad para obtener ayuda?**  
**R:** Visite el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para conectarse con otros desarrolladores y el personal de Aspose.

## Conclusión

En esta guía demostramos cómo **eliminar todas las líneas base** de un recurso usando Aspose.Tasks para .NET. Siguiendo el código paso a paso, puede restablecer los datos de líneas base, mantener limpio el seguimiento de su proyecto y preparar su cronograma para un nuevo ciclo de planificación. Siéntase libre de experimentar creando nuevas líneas base después de la eliminación para ver cómo la biblioteca actualiza el archivo de proyecto.

---

**Última actualización:** 2026-04-06  
**Probado con:** Aspose.Tasks 24.12 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}