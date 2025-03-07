---
title: Argumentos de guardado de CSS en Aspose.Tasks
linktitle: Argumentos de guardado de CSS en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a guardar argumentos CSS en Aspose.Tasks para .NET para personalizar la salida HTML. Mejore la presentación con configuraciones CSS personalizadas.
weight: 20
url: /es/net/calendar-scheduling/css-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Argumentos de guardado de CSS en Aspose.Tasks

## Introducción

En este tutorial, profundizaremos en el proceso de guardar argumentos CSS usando Aspose.Tasks para .NET. Las hojas de estilo en cascada (CSS) son cruciales para definir la presentación de elementos HTML. Aspose.Tasks nos permite manipular y guardar estos atributos CSS de manera eficiente.

## Requisitos previos

Antes de comenzar, asegúrese de tener implementados los siguientes requisitos previos:

1.  Instalación: asegúrese de haber instalado Aspose.Tasks para .NET. Puedes descargarlo desde el[sitio web](https://releases.aspose.com/tasks/net/).

2. Conocimientos básicos: se recomienda estar familiarizado con el entorno de desarrollo C# y .NET.

## Importar espacios de nombres

Para comenzar, importe los espacios de nombres necesarios:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## Paso 1: Definir devoluciones de llamada para guardar CSS

En primer lugar, definimos los métodos de devolución de llamada para guardar CSS para manejar el guardado de archivos CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implemente su lógica de guardado de CSS aquí
    }
}
```

## Paso 2: implementar devoluciones de llamada para guardar fuentes e imágenes

A continuación, implemente los métodos de devolución de llamada para guardar fuentes e imágenes de manera similar:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implemente su lógica para guardar fuentes aquí
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implemente su lógica para guardar imágenes aquí
}
```

## Paso 3: configurar las opciones de guardar

Ahora, configure las opciones de guardado de HTML para utilizar las devoluciones de llamada implementadas:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //Configurar opciones de guardado de HTML
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Paso 4: guarde el proyecto con CSS personalizado

Finalmente, guarde su proyecto con la configuración CSS personalizada:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Conclusión

En este tutorial, exploramos cómo guardar argumentos CSS usando Aspose.Tasks para .NET. Al definir las devoluciones de llamada de guardado de CSS y configurar las opciones de guardado de HTML, podemos manipular eficientemente los atributos de CSS de acuerdo con nuestros requisitos.

## Preguntas frecuentes

### P1: ¿Qué es Aspose.Tasks para .NET?

R1: Aspose.Tasks para .NET es una potente API de .NET que permite a los desarrolladores trabajar con archivos de Microsoft Project mediante programación.

### P2: ¿Puedo personalizar los atributos CSS al guardar archivos HTML con Aspose.Tasks?

R2: Sí, puede definir devoluciones de llamadas para guardar CSS para personalizar los atributos CSS según sus necesidades.

### P3: ¿Aspose.Tasks para .NET es compatible con todas las versiones de archivos de Microsoft Project?

R3: Aspose.Tasks para .NET admite varias versiones de archivos de Microsoft Project, lo que garantiza la compatibilidad entre diferentes entornos.

### P4: ¿Dónde puedo encontrar documentación completa sobre Aspose.Tasks para .NET?

A4: Puede consultar el[documentación](https://reference.aspose.com/tasks/net/) para obtener información detallada y ejemplos.

### P5: ¿Aspose.Tasks para .NET ofrece soporte para desarrolladores?

 R5: Sí, puede obtener soporte de la comunidad Aspose.Tasks a través de[foro](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
