---
title: Barra de estilo en Aspose.Tasks
linktitle: Barra de estilo en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a aplicar estilo a las barras en Aspose.Tasks para .NET para mejorar la visualización del proyecto.
type: docs
weight: 19
url: /es/net/advanced-features/styling-bar/
---
## Introducción

Diseñar barras en Aspose.Tasks es un aspecto esencial para crear planes de proyecto visualmente atractivos. Con la flexibilidad que ofrece la API Aspose.Tasks, los desarrolladores pueden personalizar varios aspectos de las barras, como el color, la forma y el estilo del texto, para mejorar la visualización del proyecto. En este tutorial, exploraremos cómo diseñar barras usando Aspose.Tasks para .NET, dividiendo cada ejemplo en pasos manejables.

## Requisitos previos

Antes de comenzar, asegúrese de tener implementados los siguientes requisitos previos:

1.  Biblioteca Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks para .NET desde[pagina de descarga](https://releases.aspose.com/tasks/net/).
2. Entorno de desarrollo: configure un entorno de desarrollo con soporte para .NET Framework.
3. Comprensión básica de C#: será beneficiosa la familiaridad con el lenguaje de programación C#.

## Importar espacios de nombres

En primer lugar, importemos los espacios de nombres necesarios para acceder a las clases y métodos de Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Paso 1: cargar el proyecto

Para comenzar, cargue el archivo del proyecto usando la API Aspose.Tasks:

```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Paso 2: configurar las opciones de guardar

Defina las opciones de guardado, especificando los estilos de barra que se aplicarán:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Paso 3: definir el estilo de la barra

Crea un nuevo estilo de barra y personaliza sus propiedades:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Establecer tipo de elemento de la barra
style.BarColor = Color.Green; // Establecer color de barra
style.BarShape = BarShape.HalfHeight; //Establecer forma de barra
style.StartShape = Shape.LeftBracket; // Establecer forma al principio de la barra.
style.StartShapeColor = Color.Aqua; // Establecer el color de la forma inicial.
style.EndShape = Shape.RightBracket; // Establecer forma al final de la barra.
style.EndShapeColor = Color.Aquamarine; // Establecer el color de la forma final.
style.TextStyle = new TextStyle(); // Establecer estilo de texto
style.TextStyle.BackgroundColor = Color.Black; // Establecer color de fondo para el texto
```

## Paso 4: Personaliza el convertidor de texto

Opcionalmente, personalice el convertidor de texto para modificar la representación del texto:

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

## Paso 5: agregue estilo de barra a las opciones

Agregue el estilo de barra configurado a las opciones de guardar:

```csharp
options.BarStyles.Add(style);
```

## Paso 6: guarde el proyecto

Finalmente, guarde el proyecto con los estilos de barra aplicados:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Conclusión

La personalización de estilos de barra en Aspose.Tasks para .NET brinda a los desarrolladores la capacidad de crear planes de proyecto visualmente atractivos. Si sigue los pasos descritos en este tutorial, puede aplicar estilos a las barras de manera eficiente para cumplir con los requisitos específicos de visualización del proyecto.

## Preguntas frecuentes

### P1: ¿Puedo aplicar varios estilos de barra a un solo proyecto?

R1: Sí, puedes definir y aplicar múltiples estilos de barra a diferentes tipos de tareas dentro del mismo proyecto.
   
### P2: ¿Es posible cambiar dinámicamente los estilos de barra durante el tiempo de ejecución?

R2: Sí, puede modificar dinámicamente los estilos de barra según ciertas condiciones o preferencias del usuario dentro de su aplicación.
   
### P3: ¿Aspose.Tasks admite la exportación de proyectos con barras con estilo a diferentes formatos de archivo?

R3: Sí, Aspose.Tasks admite la exportación de proyectos con barras con estilo a varios formatos, como PDF, XLSX y HTML.
   
### P4: ¿Hay estilos de barra predefinidos disponibles en Aspose.Tasks?

R4: Si bien Aspose.Tasks proporciona estilos de barra predeterminados, los desarrolladores también pueden crear estilos de barra personalizados adaptados a los requisitos de su proyecto.
   
### P5: ¿Puedo recuperar y modificar estilos de barra existentes dentro de un proyecto usando la API?

R5: Sí, puede recuperar y modificar estilos de barra existentes mediante programación utilizando Aspose.Tasks para .NET API.