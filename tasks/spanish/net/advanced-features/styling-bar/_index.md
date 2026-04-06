---
date: 2026-04-06
description: Aprende a cambiar el estilo de las barras y personalizar los colores
  de las mismas en Aspose.Tasks para .NET para mejorar la visualización del proyecto.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Barra de estilo en Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cómo cambiar el estilo de barras en Aspose.Tasks
url: /es/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo cambiar el estilo de barras en Aspose.Tasks

## Introducción

Si necesitas **cómo cambiar la barra** de apariencia en un archivo Microsoft Project, Aspose.Tasks para .NET te brinda control total sobre los colores, formas y estilos de texto de las barras. Al personalizar los colores de las barras y otros atributos visuales, puedes hacer que los planes de proyecto sean mucho más fáciles de leer y estén más alineados con la identidad corporativa de tu organización. En este tutorial recorreremos un ejemplo completo, paso a paso, que muestra cómo cambiar el estilo de las barras, desde cargar un proyecto hasta exportarlo con las nuevas reglas visuales aplicadas.

## Respuestas rápidas
- **¿Qué puedo estilizar?** Barras, hitos y texto de tareas en diagramas de Gantt.  
- **¿Qué formato admite barras con estilo?** PDF, XLSX, HTML y MPP nativo cuando se guarda con `PdfSaveOptions`.  
- **¿Necesito una licencia?** Se requiere una licencia comercial para uso en producción; una prueba gratuita funciona para pruebas.  
- **¿Puedo aplicar varios estilos?** Sí – agrega tantos objetos `BarStyle` como necesites.  
- **¿Es compatible con .NET Core?** Absolutamente – funciona con .NET Framework y .NET Core/5/6+.

## ¿Qué es el estilo de barras en Aspose.Tasks?

El estilo de barras te permite definir reglas visuales que el motor de Aspose.Tasks aplica al renderizar diagramas de Gantt. Cada regla (un **BarStyle**) se dirige a un tipo de elemento específico—tareas, hitos o tareas resumen—y te permite establecer colores, formas e incluso texto personalizado.

## ¿Por qué personalizar los colores de las barras?

Personalizar los colores de las barras ayuda a los interesados a identificar instantáneamente rutas críticas, tareas retrasadas o hitos. También permite que coincidas con los esquemas de colores corporativos, haciendo que los informes se vean profesionales y alineados con la marca.

## Requisitos previos

1. **Aspose.Tasks for .NET** – descárgalo desde la [download page](https://releases.aspose.com/tasks/net/).  
2. Un entorno de desarrollo que soporte .NET (Framework 4.6+, .NET Core 3.1+ o posterior).  
3. Familiaridad básica con C# – los ejemplos usan código simple y autocontenido.

## Importar espacios de nombres

Primero, importa los espacios de nombres que contienen las clases que utilizaremos:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Paso 1: Cargar el proyecto

Carga un archivo MPP existente (o crea uno nuevo) para que tengas un objeto de proyecto con el que trabajar:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Paso 2: Configurar opciones de guardado

Crea una instancia de `PdfSaveOptions` e inicializa la colección `BarStyles` donde almacenaremos nuestros estilos personalizados:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Paso 3: Definir estilo de barra

Ahora construimos un objeto `BarStyle` y establecemos las propiedades que controlan cómo se ve la barra. Aquí es donde **personalizamos los colores de la barra** y las formas:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Paso 4: Personalizar convertidor de texto (Opcional)

Si deseas ajustar el texto que aparece en la barra, puedes asignar un convertidor personalizado. El ejemplo antepone a los nombres de tareas que no comienzan ya con “T”:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Paso 5: Añadir estilo de barra a las opciones

Añade el estilo completamente configurado a la colección `BarStyles` de las opciones de guardado:

```csharp
options.BarStyles.Add(style);
```

## Paso 6: Guardar el proyecto

Finalmente, exporta el proyecto. El PDF (u otro formato) renderizará el diagrama de Gantt usando el estilo de barra que definimos:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Problemas comunes y soluciones

| Problema | Razón | Solución |
|----------|-------|----------|
| **Estilo de barra no aplicado** | La colección `BarStyles` estaba vacía o no estaba adjunta a las opciones de guardado. | Asegúrate de añadir el `BarStyle` a `options.BarStyles` antes de llamar a `Save`. |
| **Los colores se ven diferentes en PDF** | La renderización del PDF puede usar un perfil de color diferente. | Utiliza valores estándar de `System.Drawing.Color` o define colores ARGB personalizados. |
| **El convertidor de texto lanza referencia nula** | La propiedad de tarea `Tsk.Name` es nula para algunas tareas. | Añade una verificación de nulo antes de acceder a `task.Get(Tsk.Name)`. |

## Preguntas frecuentes

### Q1: ¿Puedo aplicar varios estilos de barra a un solo proyecto?

A1: Sí, puedes definir y aplicar varios estilos de barra a diferentes tipos de tareas dentro del mismo proyecto.

### Q2: ¿Es posible cambiar dinámicamente los estilos de barra durante la ejecución?

A2: Sí, puedes modificar dinámicamente los estilos de barra basándote en ciertas condiciones o preferencias del usuario dentro de tu aplicación.

### Q3: ¿Aspose.Tasks admite la exportación de proyectos con barras con estilo a diferentes formatos de archivo?

A3: Sí, Aspose.Tasks admite la exportación de proyectos con barras con estilo a varios formatos como PDF, XLSX y HTML.

### Q4: ¿Existen estilos de barra predefinidos disponibles en Aspose.Tasks?

A4: Aunque Aspose.Tasks proporciona estilos de barra predeterminados, los desarrolladores también pueden crear estilos de barra personalizados adaptados a los requisitos de su proyecto.

### Q5: ¿Puedo obtener y modificar los estilos de barra existentes dentro de un proyecto usando la API?

A5: Sí, puedes obtener y modificar los estilos de barra existentes programáticamente usando la API de Aspose.Tasks para .NET.

## Preguntas frecuentes

**Q: ¿Cómo cambio el color de la barra para tareas regulares en lugar de hitos?**  
A: Establece `style.ItemType = BarItemType.Task;` y asigna `style.BarColor` al `Color` deseado.

**Q: ¿Puedo usar este enfoque para estilizar barras al exportar a HTML?**  
A: Sí. Usa `HtmlSaveOptions` y rellena su colección `BarStyles` de la misma manera.

**Q: ¿Hay un límite al número de estilos de barra que puedo definir?**  
A: Prácticamente no; puedes añadir tantos como necesites, pero ten en cuenta el rendimiento para colecciones muy grandes.

**Q: ¿Necesito llamar a `project.Calculate()` después de cambiar los estilos?**  
A: No, los estilos se aplican durante la operación de guardado; el recálculo solo es necesario para cambios de programación.

---

**Última actualización:** 2026-04-06  
**Probado con:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}