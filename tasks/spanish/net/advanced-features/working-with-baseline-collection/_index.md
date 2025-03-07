---
title: Trabajar con la colección Baseline en Aspose.Tasks
linktitle: Trabajar con la colección Baseline en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar líneas de base en Aspose.Tasks para .NET de manera eficiente. Siga nuestro tutorial completo para obtener orientación paso a paso.
weight: 20
url: /es/net/advanced-features/working-with-baseline-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Trabajar con la colección Baseline en Aspose.Tasks

## Introducción

Aspose.Tasks para .NET es una poderosa biblioteca que permite a los desarrolladores trabajar con archivos de Microsoft Project en sus aplicaciones .NET sin problemas. Entre sus muchas características, proporciona un soporte sólido para gestionar líneas base dentro de proyectos. Las líneas de base son esenciales para la gestión de proyectos, ya que le permiten comparar el plan original del proyecto con el estado actual, lo que permite un mejor seguimiento y análisis del progreso del proyecto.

## Requisitos previos

Antes de sumergirnos en el trabajo con colecciones de referencia en Aspose.Tasks, asegúrese de tener implementados los siguientes requisitos previos:

1. Visual Studio: instale Visual Studio IDE en su sistema.
2.  Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks para .NET desde[enlace de descarga](https://releases.aspose.com/tasks/net/).
3. Comprensión básica de C#: familiarícese con el lenguaje de programación C#.
4. Archivo de Microsoft Project: tenga un archivo de Microsoft Project (.mpp) listo para realizar pruebas.

## Importar espacios de nombres

Para comenzar a trabajar con colecciones de referencia en Aspose.Tasks, debe importar los siguientes espacios de nombres:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Ahora, dividamos cada ejemplo en varios pasos:

## Paso 1: cargar el archivo del proyecto

Primero, cargue el archivo de Microsoft Project usando Aspose.Tasks:

```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Paso 2: obtenga recursos

A continuación, recupere el recurso deseado del proyecto:

```csharp
var resource = project.Resources.GetByUid(1);
```

## Paso 3: Mostrar información de referencia

Ahora, muestre información sobre las líneas base asociadas con el recurso:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Paso 4: iterar a través de las líneas de base

Repita cada línea de base asociada con el recurso e imprima información relevante:

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

## Paso 5: eliminar las líneas de base

Elimine todas las líneas base asociadas con el recurso:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## Conclusión

En este tutorial, exploramos cómo trabajar con colecciones de referencia en Aspose.Tasks para .NET. Si sigue la guía paso a paso, podrá gestionar fácilmente las líneas base dentro de sus aplicaciones .NET, lo que permitirá un seguimiento y análisis eficaces del proyecto.

## Preguntas frecuentes

### P1: ¿Puede Aspose.Tasks manejar archivos de proyectos grandes?

R1: Sí, Aspose.Tasks está optimizado para manejar archivos de proyectos grandes de manera eficiente, lo que garantiza un rendimiento fluido.

### P2: ¿Aspose.Tasks es compatible con todas las versiones de Microsoft Project?

R2: Aspose.Tasks admite varias versiones de Microsoft Project, lo que garantiza la compatibilidad entre diferentes entornos.

### P3: ¿Puedo personalizar las líneas base en Aspose.Tasks?

R3: Sí, puede personalizar las líneas base según los requisitos de su proyecto utilizando Aspose.Tasks para .NET.

### P4: ¿Aspose.Tasks ofrece soporte para plataformas en la nube?

R4: Sí, Aspose.Tasks brinda soporte para la integración con plataformas de nube populares, ofreciendo flexibilidad en la implementación.

### P5: ¿Existe un foro comunitario para que los usuarios de Aspose.Tasks busquen ayuda y compartan conocimientos?

 R5: Sí, puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para interactuar con la comunidad y obtener ayuda de expertos.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
