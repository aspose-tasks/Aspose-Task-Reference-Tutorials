---
date: 2026-03-16
description: Aprenda a implementar la devolución de llamada de guardado de página
  en Aspose.Tasks para .NET, lo que permite un manejo personalizado de los flujos
  de salida de documentos multipágina.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Implementar la devolución de llamada de guardado de página en Aspose.Tasks
url: /es/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Implementar la devolución de llamada de guardado de página en Aspose.Tasks

## Introducción

## Respuestas rápidas
- **¿Qué hace la devolución de llamada de guardado de página?** Captura cada página renderizada en un flujo separado para que puedas manejarlas individualmente.  
- **¿A qué formato puedo exportar?** Cualquier formato compatible con `ImageSaveOptions`, por ejemplo, PNG, JPEG, PDF.  
- **¿Necesito una licencia?** Se requiere una licencia válida de Aspose.Tasks para uso en producción.  
- **¿Puedo usar esto con .NET Core?** Sí, Aspose.Tasks soporta completamente .NET Core y .NET 5/6+.  
- **¿La devolución de llamada es segura para subprocesos?** La devolución de llamada se ejecuta en el mismo subproceso que realiza el renderizado, por lo que se aplican las reglas normales de seguridad de subprocesos.

## ¿Qué es **implement page saving callback**?
El patrón **implement page saving callback** le permite insertar lógica personalizada en la canalización de guardado de Aspose.Tasks. En lugar de escribir directamente a un archivo, recibe un objeto `Stream` para cada página, lo que le permite almacenarlo en memoria, subirlo a un almacenamiento en la nube o aplicar procesamiento adicional.

## ¿Por qué exportar el proyecto como PNG con una devolución de llamada?
Exportar un proyecto como PNG le brinda una imagen rasterizada de cada página del diagrama de Gantt, lo cual es ideal para informes, correos electrónicos o incrustar en páginas web. Usar una devolución de llamada le permite mantener cada página en un `MemoryStream` separado sin crear archivos temporales en el disco.

## Requisitos previos

1. **Conocimientos de C#** – familiaridad básica con clases, interfaces y flujos.  
2. **Aspose.Tasks para .NET** – descargue e instale desde [aquí](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider o cualquier editor compatible con .NET.

## Importar espacios de nombres

Para comenzar, importe los espacios de nombres requeridos:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Paso 1: Crear un objeto Project

Cargue un archivo MPP existente en una instancia de `Project`:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Paso 2: Configurar Image Save Options

Configure `ImageSaveOptions` para salida PNG y adjunte la devolución de llamada personalizada:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Consejo profesional:** Configurar `RenderToSinglePage = false` garantiza que cada página del diagrama de Gantt se renderice por separado, lo cual es esencial para que la devolución de llamada reciba flujos distintos.

## Paso 3: Guardar el proyecto con devolución de llamada

Invoca el método `Save`, pasando `Stream.Null` porque los flujos reales son suministrados por la devolución de llamada:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Paso 4: Procesar los flujos de páginas guardadas

Después de que la operación de guardado se complete, la devolución de llamada contiene una colección de objetos `MemoryStream`, uno por página. Ahora puede iterar sobre ellos:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Paso 5: Implementar una devolución de llamada personalizada de guardado de página

Cree una clase sellada que implemente `IPageSavingCallback`. Esta clase captura el flujo de cada página y lo almacena en una lista para su uso posterior.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Problemas comunes y solución de problemas

| Problema | Razón | Solución |
|----------|-------|----------|
| **No se devuelven páginas** | `RenderToSinglePage` dejado como `true`. | Establezca `RenderToSinglePage = false` para generar páginas separadas. |
| **Los flujos están vacíos** | `KeepStreamOpen` configurado a `true` sin liberar después. | Manténgalo en `false` (valor predeterminado) y permita que la devolución de llamada cierre los flujos automáticamente. |
| **Errores de falta de memoria** | Proyectos muy grandes generan muchos PNG de alta resolución. | Procese los flujos uno por uno o aumente los límites de memoria de la VM. |

## Preguntas frecuentes

**Q1: ¿Qué es una devolución de llamada de guardado de página en Aspose.Tasks?**  
R: Una devolución de llamada de guardado de página le permite interceptar el proceso de guardado para cada página de un documento multipágina, proporcionando un `Stream` personalizado para esa página.

**Q2: ¿Puedo usar diferentes formatos para guardar páginas usando esta devolución de llamada?**  
R: Sí. Cambiando `SaveFileFormat` puede exportar a PNG, JPEG, PDF, SVG, etc.

**Q3: ¿Aspose.Tasks es compatible con .NET Core?**  
R: Absolutamente. Aspose.Tasks soporta .NET Core, .NET 5 y .NET 6.

**Q4: ¿Cómo puedo manejar errores durante el proceso de guardado de página?**  
R: Envuelva la lógica de la devolución de llamada en bloques try/catch y registre las excepciones. El método `OnFinish` es un buen lugar para la limpieza final.

**Q5: ¿Dónde puedo encontrar más recursos y soporte para Aspose.Tasks?**  
R: Puede visitar el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener ayuda, acceder a la documentación [aquí](https://reference.aspose.com/tasks/net/), o explorar características adicionales y opciones de licencia en el [sitio web de Aspose.Tasks](https://purchase.aspose.com/buy).

---

**Última actualización:** 2026-03-16  
**Probado con:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}