---
date: 2026-03-05
description: Aprenda cómo guardar imágenes, generar HTML con imágenes y personalizar
  la exportación de imágenes usando Aspose.Tasks para .NET. Guía paso a paso para
  guardar el proyecto como HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Cómo guardar imágenes con Aspose.Tasks para .NET
url: /es/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo guardar imágenes con Aspose.Tasks para .NET

## Introducción

En este tutorial descubrirá **cómo guardar imágenes** de archivos Microsoft Project usando la API Aspose.Tasks para .NET. Ya sea que necesite incrustar gráficos en informes, generar páginas HTML que contengan visuales del proyecto, o simplemente exportar recursos diagramáticos, los pasos a continuación le guiarán a través de todo el proceso—desde configurar el objeto del proyecto hasta personalizar los callbacks de exportación de imágenes.

## Respuestas rápidas
- **¿Qué significa “cómo guardar imágenes” en Aspose.Tasks?**  
  Se refiere al uso de la interfaz `IImageSavingCallback` para controlar dónde y cómo se escriben los recursos visuales en el disco.
- **¿Puedo guardar un proyecto como HTML con imágenes incrustadas?**  
  Sí, usando `HtmlSaveOptions` junto con callbacks de guardado de imágenes puedes **guardar el proyecto como HTML** que incluye todas las imágenes generadas.
- **¿Necesito una licencia para exportar imágenes?**  
  Una licencia de evaluación temporal funciona para pruebas; se requiere una licencia completa para uso en producción.
- **¿Qué versiones de .NET son compatibles?**  
  Aspose.Tasks para .NET es compatible con .NET Framework 4.5+, .NET Core 3.1+ y .NET 5/6+.
- **¿Es posible personalizar la exportación de imágenes (formato, carpeta, nombre)?**  
  Absolutamente: el callback le brinda control total sobre el nombre de archivo, el formato y el destino.

## ¿Qué es “cómo guardar imágenes” en el contexto de Aspose.Tasks?
Guardar imágenes significa extraer elementos visuales (gráficos, barras de Gantt, gráficos de recursos) de un archivo Project y escribirlos en archivos de imagen (PNG, JPEG, etc.). Aspose.Tasks proporciona un mecanismo flexible de callbacks que le permite decidir la ubicación exacta, la convención de nombres e incluso el formato de la imagen.

## ¿Por qué usar Aspose.Tasks para guardar imágenes?
- **Control total programático** – no se requiere interacción manual de UI.  
- **Multiplataforma** – funciona en Windows, Linux y macOS a través de .NET Core.  
- **Renderizado de alta fidelidad** – las imágenes conservan la misma calidad que la vista original del proyecto.  
- **Generación fácil de HTML** – combine `HtmlSaveOptions` con callbacks de imágenes para **generar HTML con imágenes** automáticamente.

## Requisitos previos

Antes de comenzar, asegúrese de contar con lo siguiente:

1. Visual Studio instalado en su máquina de desarrollo.  
2. Aspose.Tasks para .NET descargado desde [aquí](https://releases.aspose.com/tasks/net/).  
3. Familiaridad básica con C# y la estructura de proyectos .NET.

## Importar espacios de nombres

Primero, incluya los espacios de nombres requeridos en su archivo fuente:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Paso 1: Crear un objeto Project

Cargue el archivo Microsoft Project con el que desea trabajar:

```csharp
var project = new Project("Project1.mpp");
```

## Paso 2: Definir opciones de guardado

Cree las opciones de guardado HTML que también contendrán nuestros callbacks de guardado de imágenes:

```csharp
var options = GetSaveOptions(1);
```

## Paso 3: Guardar el proyecto como HTML (guardar proyecto como html)

Ahora exporte el proyecto a un archivo HTML. Las imágenes referenciadas en el HTML serán generadas por el callback que definiremos a continuación:

```csharp
project.Save("document_out.html", options);
```

## Paso 4: Implementar el callback de guardado de imágenes (personalizar exportación de imágenes)

Implemente la interfaz `IImageSavingCallback`. Aquí es donde **personaliza el comportamiento de exportación de imágenes**:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## Paso 5: Guardar imágenes en el directorio especificado

Dentro del método `ImageSaving`, decida dónde se debe almacenar cada imagen. El ejemplo a continuación distingue los recursos PNG de otros formatos:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## Paso 6: Especificar opciones de guardado (incluyendo callbacks)

Configure los callbacks para fuentes, CSS e imágenes. Esto garantiza que cada elemento visual se maneje de forma consistente:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| Las imágenes no aparecen en el HTML generado | El callback no asigna una ruta de archivo válida | Asegúrese de que `args.Path` apunte a una carpeta con permisos de escritura y establezca `args.ImageStream` correctamente. |
| Los archivos PNG se guardan con extensión incorrecta | La lógica condicional solo verifica el sufijo “png” | Utilice `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` para una detección robusta. |
| Referencias HTML rotas después de mover los archivos | Las rutas relativas cambiaron después de mover la carpeta de salida | Mantenga las carpetas HTML e imágenes juntas o actualice `options.ImageFolder` en consecuencia. |

## Conclusión

Al seguir estos pasos ahora sabe **cómo guardar imágenes** de un archivo Project, **guardar el proyecto como HTML**, y **personalizar la exportación de imágenes** para adaptarse a la estructura de carpetas de su aplicación. Este enfoque le permite **generar HTML con imágenes** que pueden incrustarse en informes, portales de documentación o paneles web de forma fluida.

## Preguntas frecuentes

**Q1: ¿Puedo usar Aspose.Tasks para manipular archivos de proyecto en otros formatos además de HTML?**  
A1: Sí, Aspose.Tasks admite varios formatos como PDF, XLSX y MPP.

**Q2: ¿Aspose.Tasks ofrece soporte para integración con almacenamiento en la nube?**  
A2: Sí, Aspose.Tasks ofrece APIs para trabajar con servicios de almacenamiento en la nube populares como Amazon S3 y Google Drive.

**Q3: ¿Aspose.Tasks es compatible con .NET Core?**  
A3: Sí, Aspose.Tasks es compatible con .NET Core, lo que le permite desarrollar aplicaciones multiplataforma.

**Q4: ¿Puedo personalizar la apariencia de las imágenes guardadas?**  
A4: Sí, puede personalizar la apariencia de las imágenes modificando la lógica de guardado dentro de los métodos de callback.

**Q5: ¿Aspose.Tasks ofrece versiones de prueba para evaluación?**  
A5: Sí, puede obtener una prueba gratuita de Aspose.Tasks desde [aquí](https://releases.aspose.com/).

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}