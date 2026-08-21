---
date: 2026-03-19
description: Aprenda a agregar múltiples columnas personalizadas y a formatear el
  ancho de columna personalizada al exportar un proyecto a XML usando Aspose.Tasks
  para .NET.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Agregar múltiples columnas personalizadas a la vista de asignaciones en Aspose.Tasks
url: /es/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar varias columnas personalizadas a la vista de asignaciones en Aspose.Tasks

## Introducción

En este tutorial descubrirá **cómo agregar varias columnas personalizadas** a una vista de asignaciones con Aspose.Tasks para .NET. Las columnas personalizadas le permiten mostrar datos adicionales—como notas, costos o indicadores personalizados—directamente en los informes exportados. Al final de la guía podrá formatear el ancho de la columna personalizada, exportar el proyecto a XML y adaptar la vista para que coincida con sus necesidades de gestión de proyectos.

## Respuestas rápidas
- **¿Qué puedo lograr?** Mostrar cualquier dato de asignación en columnas personalizadas y controlar su apariencia.  
- **¿Qué formato lo soporta?** Exportar el proyecto a XML (u otros formatos) usando `Spreadsheet2003SaveOptions`.  
- **¿Necesito una licencia?** Sí, se requiere una licencia válida de Aspose.Tasks para uso en producción.  
- **¿Qué versiones de .NET funcionan?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Cuántas columnas puedo agregar?** Ilimitado – simplemente cree instancias adicionales de `AssignmentViewColumn`.

## ¿Qué son las columnas personalizadas múltiples?
Las columnas personalizadas múltiples son campos definidos por el usuario que aparecen junto a las columnas de asignación predeterminadas cuando un proyecto se guarda o exporta. Le brindan la flexibilidad de mostrar cualquier propiedad de un objeto `ResourceAssignment`, como notas personalizadas, códigos de costo o valores calculados.

## ¿Por qué agregar columnas personalizadas múltiples a la vista de asignaciones?
- **Informes mejorados:** Incluir información específica del proyecto que no está cubierta por las columnas incorporadas.  
- **Mejor toma de decisiones:** Los interesados pueden ver los datos exactos que necesitan sin tener que profundizar en archivos sin procesar.  
- **Formato consistente:** Controlar el ancho de la columna y la conversión de texto para una salida limpia y legible.  

## Requisitos previos

Antes de comenzar, asegúrese de tener:

1. Conocimientos básicos del lenguaje de programación C#.
2. Biblioteca Aspose.Tasks para .NET instalada. Si no la tiene, puede descargarla **[aquí](https://releases.aspose.com/tasks/net/)**.
3. Un entorno de desarrollo integrado (IDE) como Visual Studio.

## Guía paso a paso

### Paso 1: Importar espacios de nombres
Primero, importe los espacios de nombres que proporcionan las clases que necesitaremos para trabajar con proyectos y visualizaciones.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Paso 2: Cargar el proyecto
Cree una instancia de `Project` y cargue un archivo MPP existente.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Paso 3: Crear opciones de guardado de hoja de cálculo
Instancie `Spreadsheet2003SaveOptions` – este objeto nos permite personalizar la vista de asignaciones antes de exportar.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Paso 4: Definir columna personalizada
Cree un `AssignmentViewColumn` para cada dato que desee mostrar. A continuación agregamos una columna **Notes** con un ancho de 200 puntos.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Consejo:** Para agregar *múltiples* columnas personalizadas, repita este paso con diferentes nombres de campo y lógica de delegado, luego agregue cada instancia a `options.AssignmentView.Columns`.

### Paso 5: Agregar columna personalizada a las opciones
Agregue la columna (o columnas) a la colección `Columns` de la vista de asignaciones.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Paso 6: Recorrer asignaciones (Depuración opcional)
Puede iterar a través de las asignaciones para verificar que el texto de la columna personalizada se genere correctamente.

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

### Paso 7: Guardar el proyecto con columnas personalizadas
Finalmente, guarde el proyecto. El ejemplo guarda en XML, pero puede elegir cualquier formato compatible.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Cómo exportar el proyecto a XML con columnas personalizadas?
Cuando llama a `project.Save` con el `Spreadsheet2003SaveOptions` configurado, Aspose.Tasks escribe los datos del proyecto—incluidas todas las **columnas personalizadas múltiples**—en el archivo XML seleccionado. Esto facilita compartir información de proyecto enriquecida con otros sistemas o interesados.

## Formatear el ancho de la columna personalizada para mejor legibilidad
El segundo parámetro del constructor `AssignmentViewColumn` controla el ancho de la columna (medido en puntos). Ajuste este valor según la cantidad de texto que espere. Por ejemplo, un ancho de **300** funciona bien para notas largas, mientras que **100** es suficiente para indicadores cortos.

## Problemas comunes y soluciones
- **El texto de la columna aparece en blanco:** Asegúrese de que el delegado devuelva una cadena y que la propiedad subyacente de la asignación (p. ej., `Asn.NotesText`) esté poblada.  
- **Las columnas no son visibles en el archivo exportado:** Verifique que `options.AssignmentView.Columns` contenga sus columnas personalizadas antes de llamar a `Save`.  
- **El ancho parece ser ignorado:** Algunos formatos de exportación tienen sus propias reglas de diseño; XML respeta el ancho, pero PDF/HTML pueden necesitar estilos adicionales.  

## Preguntas frecuentes

### P1: ¿Puedo agregar múltiples columnas personalizadas a la vista de asignaciones?
**R:** Sí, simplemente cree objetos `AssignmentViewColumn` adicionales y agregue cada uno a `options.AssignmentView.Columns`.

### P2: ¿Hay convertidores predefinidos disponibles para campos de asignación comunes?
**R:** Sí, Aspose.Tasks proporciona convertidores incorporados para muchos campos estándar, lo que facilita extraer datos sin escribir delegados personalizados.

### P3: ¿Puedo personalizar la apariencia de las columnas personalizadas, como formatear texto o aplicar estilos?
**R:** Por supuesto. Además de establecer el ancho, puede modificar la fuente, alineación y otras propiedades visuales mediante las opciones de estilo de la columna.

### P4: ¿Es posible eliminar columnas predeterminadas de la vista de asignaciones?
**R:** Puede excluir columnas predeterminadas eliminándolas de la colección `Columns` o estableciendo su ancho a cero.

### P5: ¿Aspose.Tasks admite la exportación de proyectos a otros formatos además de hojas de cálculo con columnas personalizadas?
**R:** Sí, Aspose.Tasks puede exportar a PDF, HTML, XML y muchos otros formatos mientras conserva las definiciones de columnas personalizadas.

---

**Última actualización:** 2026-03-19  
**Probado con:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}