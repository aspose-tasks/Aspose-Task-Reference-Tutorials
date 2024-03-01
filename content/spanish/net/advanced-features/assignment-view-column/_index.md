---
title: Columna de vista de asignación personalizada en Aspose.Tasks
linktitle: Columna de vista de asignación personalizada en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a agregar columnas de vista de tareas personalizadas en Aspose.Tasks para .NET para mejorar las capacidades de gestión de proyectos.
type: docs
weight: 16
url: /es/net/advanced-features/assignment-view-column/
---
## Introducción

En este tutorial, exploraremos cómo agregar columnas personalizadas para vistas de tareas usando Aspose.Tasks para .NET. Las columnas personalizadas brindan flexibilidad y le permiten mostrar información adicional relevante para sus necesidades de gestión de proyectos.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Conocimientos básicos del lenguaje de programación C#.
2.  Aspose.Tasks para la biblioteca .NET instalada. Si no, puedes descargarlo.[aquí](https://releases.aspose.com/tasks/net/).
3. Un entorno de desarrollo integrado (IDE) como Visual Studio.

## Importar espacios de nombres

Primero, importemos los espacios de nombres necesarios para acceder a las clases y métodos necesarios para crear columnas de vista de asignación personalizadas:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Paso 1: cargar el proyecto

 Para comenzar, cargue el archivo de su proyecto usando el`Project` clase:

```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Paso 2: crear opciones para guardar la hoja de cálculo

 A continuación, cree una instancia de`Spreadsheet2003SaveOptions` lo que nos permite personalizar las columnas de la vista de tareas:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Paso 3: definir una columna personalizada

 Ahora, defina su columna personalizada creando una instancia de`AssignmentViewColumn`. Esta clase requiere el nombre de la columna, el ancho y una función delegada para convertir los datos de la tarea en texto de columna:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Paso 4: agregar una columna personalizada a las opciones

Agregue la columna personalizada a la colección de columnas de la vista de asignación de las opciones de guardar:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Paso 5: iterar a través de las tareas

Repita cada asignación de recursos en el proyecto y muestre el texto de la columna personalizada:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## Paso 6: guarde el proyecto con columnas personalizadas

Finalmente, guarde el proyecto con las columnas de la vista de asignación personalizada:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Conclusión

En este tutorial, aprendimos cómo agregar columnas de vista de asignación personalizadas usando Aspose.Tasks para .NET. Las columnas personalizadas ofrecen flexibilidad para mostrar información adicional adaptada a los requisitos de su proyecto, mejorando las capacidades de gestión de proyectos.

## Preguntas frecuentes

### P1: ¿Puedo agregar varias columnas personalizadas a la vista de tareas?

 R1: Sí, puede agregar varias columnas personalizadas creando instancias adicionales de`AssignmentViewColumn` y agregándolos al`Columns` recopilación.

### P2: ¿Hay convertidores predefinidos disponibles para campos de asignación comunes?

R2: Sí, Aspose.Tasks proporciona convertidores predefinidos para campos de asignación comunes, lo que facilita la extracción de datos para columnas personalizadas.

### P3: ¿Puedo personalizar la apariencia de columnas personalizadas, como dar formato al texto o aplicar estilos?

R3: Sí, puede personalizar la apariencia de las columnas personalizadas modificando propiedades como el ancho, la fuente y la alineación.

### P4: ¿Es posible eliminar columnas predeterminadas de la vista de tareas?

 R4: Sí, puede eliminar columnas predeterminadas excluyéndolas del`Columns` colección o estableciendo su ancho en cero.

### P5: ¿Aspose.Tasks admite la exportación de proyectos a otros formatos además de hojas de cálculo con columnas personalizadas?

R5: Sí, Aspose.Tasks admite la exportación de proyectos a varios formatos, como PDF, HTML y XML, lo que permite opciones versátiles de informes de proyectos.