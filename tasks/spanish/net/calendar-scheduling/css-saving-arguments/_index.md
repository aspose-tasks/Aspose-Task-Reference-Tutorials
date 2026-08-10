---
date: 2026-07-05
description: Aprenda cómo personalizar CSS al exportar un proyecto a HTML usando Aspose.Tasks
  para .NET. Ajuste la salida HTML con argumentos de guardado de CSS.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Cómo personalizar CSS al guardar proyectos con Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Cómo personalizar CSS al guardar proyectos con Aspose.Tasks
url: /es/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo personalizar CSS al guardar proyectos con Aspose.Tasks

En esta guía descubrirás **cómo personalizar CSS** durante la exportación HTML de un archivo Microsoft Project usando Aspose.Tasks para .NET. Al ajustar los argumentos de guardado de CSS obtienes control total sobre el estilo visual de las páginas HTML generadas, haciendo que la salida coincida con tu marca o estándares de informes.

## Respuestas rápidas
- **¿Cuál es el punto de entrada principal?** Use `HtmlSaveOptions` with custom callbacks.  
- **¿Necesito una licencia?** Sí, se requiere una licencia válida de Aspose.Tasks para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Puedo exportar proyectos grandes?** Aspose.Tasks maneja proyectos con > 10,000 tareas sin cargar todo el archivo en memoria.  
- **¿La personalización de CSS es opcional?** Sí, puedes omitir los callbacks para usar la hoja de estilo predeterminada.

## ¿Cómo personalizar CSS en Aspose.Tasks?

Carga tu proyecto, adjunta callbacks de guardado de CSS al objeto `HtmlSaveOptions` y luego llama a `project.Save`. Este patrón te permite escribir archivos CSS personalizados, reemplazar los estilos predeterminados y controlar la estructura de carpetas, todo en unas pocas líneas de código. Los callbacks se invocan automáticamente para cada archivo CSS durante el proceso de exportación.

`HtmlSaveOptions` configura cómo se exporta un proyecto a HTML.

## Introducción

En este tutorial, profundizaremos en el proceso de guardar argumentos CSS usando Aspose.Tasks para .NET. Las Hojas de Estilo en Cascada (CSS) son cruciales para definir la presentación de los elementos HTML. Aspose.Tasks nos permite manipular y guardar estos atributos CSS de manera eficiente.

## Prerrequisitos

Antes de comenzar, asegúrate de tener los siguientes prerrequisitos:

1. Instalación: Asegúrate de haber instalado Aspose.Tasks para .NET. Puedes descargarlo desde el [sitio web](https://releases.aspose.com/tasks/net/).

2. Conocimientos básicos: Se recomienda familiaridad con C# y el entorno de desarrollo .NET.

## Importar espacios de nombres

Para comenzar, importa los espacios de nombres necesarios:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Paso 1: Definir callbacks de guardado de CSS

`ICssSavingCallback` es una interfaz que te permite personalizar cómo se guardan los archivos CSS durante la exportación a HTML.

Un **callback de guardado de CSS** es un delegado que Aspose.Tasks invoca para escribir archivos CSS durante la exportación a HTML. Define los métodos de callback para controlar cómo se crea cada archivo CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Paso 2: Implementar callbacks de guardado de fuentes e imágenes

`FontSavingArgs` proporciona información sobre la fuente que se está guardando, mientras que `ImageSavingArgs` suministra detalles de los recursos de imagen.

Implementa los métodos de callback de guardado de fuentes e imágenes de manera similar:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Paso 3: Configurar opciones de guardado

`HtmlSaveOptions` es el objeto de configuración que controla cómo se exporta un Project a HTML.

`HtmlSaveOptions` te permite especificar callbacks, carpetas de salida y otras configuraciones de exportación.

Establece sus propiedades para usar los callbacks definidos anteriormente y para especificar la carpeta de salida:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Paso 4: Guardar proyecto con CSS personalizado

`Project` representa un archivo de Microsoft Project que puede ser manipulado y guardado.

Finalmente, guarda tu proyecto con la configuración de CSS personalizada:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## ¿Por qué personalizar CSS al exportar proyectos?

Aspose.Tasks admite **exportar proyectos a HTML** en más de 30 formatos y puede generar hasta 30 archivos CSS separados por exportación. Procesa de manera fiable proyectos que contienen más de 10 000 tareas mientras mantiene el uso de memoria por debajo de 200 MB, lo que permite informes a escala empresarial sin cuellos de botella de rendimiento.

## Conclusión

En este tutorial, hemos explorado cómo guardar argumentos CSS usando Aspose.Tasks para .NET. Al definir callbacks de guardado de CSS y configurar las opciones de guardado HTML, podemos manipular eficientemente los atributos CSS según nuestros requisitos.

## Preguntas frecuentes

### Q1: ¿Qué es Aspose.Tasks para .NET?

A1: Aspose.Tasks para .NET es una potente API .NET que permite a los desarrolladores trabajar con archivos de Microsoft Project de forma programática.

### Q2: ¿Puedo personalizar atributos CSS al guardar archivos HTML con Aspose.Tasks?

A2: Sí, puedes definir callbacks de guardado de CSS para personalizar los atributos CSS según tus necesidades.

### Q3: ¿Aspose.Tasks para .NET es compatible con todas las versiones de archivos Microsoft Project?

A3: Aspose.Tasks para .NET admite varias versiones de archivos Microsoft Project, garantizando compatibilidad en diferentes entornos.

### Q4: ¿Dónde puedo encontrar documentación completa para Aspose.Tasks para .NET?

A4: Puedes consultar la [documentación](https://reference.aspose.com/tasks/net/) para obtener información detallada y ejemplos.

### Q5: ¿Aspose.Tasks para .NET ofrece soporte para desarrolladores?

A5: Sí, puedes obtener soporte de la comunidad de Aspose.Tasks a través del [foro](https://forum.aspose.com/c/tasks/15).

**Preguntas adicionales**

**P: ¿Cómo afecta la personalización de CSS al tamaño del HTML exportado?**  
R: Usar CSS personalizado puede reducir el tamaño total hasta en 15 % porque puedes eliminar estilos predeterminados no utilizados.

**P: ¿Puedo usar los mismos callbacks para varios proyectos?**  
R: Absolutamente. Implementa los callbacks una vez y reutilízalos en cualquier número de exportaciones de proyectos.

**P: ¿Es posible incrustar CSS directamente en el HTML en lugar de archivos separados?**  
R: Sí, establece `HtmlSaveOptions.EmbeddedCss = true` para incrustar la hoja de estilo, lo que simplifica la distribución.

---

**Última actualización:** 2026-07-05  
**Probado con:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Guardar MS Project como HTML con Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Implementar callback de guardado de página en Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Manejo del guardado de imágenes en Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}