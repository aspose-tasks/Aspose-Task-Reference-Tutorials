---
date: 2026-10-15
description: Aprenda cómo agregar una propiedad personalizada y gestionar propiedades
  de proyecto personalizadas en Aspose.Tasks para .NET, mejorando el control de los
  metadatos de su proyecto.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Gestión de la colección de propiedades de proyecto personalizadas en Aspose.Tasks
og_description: Agregue una propiedad personalizada a sus archivos de proyecto con
  Aspose.Tasks para .NET. Esta guía le muestra cómo gestionar propiedades personalizadas,
  leerlas y agregar valores booleanos o de cadena de manera eficiente.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Agregar una propiedad personalizada usando la API .NET de Aspose.Tasks para
  proyectos
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Cómo agregar una propiedad personalizada en Aspose.Tasks para .NET
url: /es/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar una propiedad personalizada en Aspose.Tasks para .NET

## Introducción

Add custom property support lets you store project‑specific metadata that the built‑in fields don’t cover. In this tutorial you’ll learn how to **add custom property**, read it back, and manage the entire custom property collection using Aspose.Tasks for .NET. By the end you’ll be able to tailor project files with Boolean, DateTime, Double, and String values that fit your business rules.

## Respuestas rápidas
- **¿Puedo agregar una propiedad personalizada Boolean?** Yes – use `CustomPropertyType.Boolean`.
- **¿Cuántos tipos de propiedades personalizadas son compatibles?** Four: Boolean, DateTime, Double, String.
- **¿La colección de propiedades personalizadas es de solo lectura?** It can be read‑only if the project is loaded from a read‑only source.
- **¿Necesito una licencia para usar esta función?** A temporary license works for evaluation; a full license is required for production.
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ¿Qué es una propiedad personalizada?

A custom property is a user‑defined metadata field that you attach to a Project object. It lets you store extra information such as “Risk Level”, “Customer ID”, or any Boolean flag that isn’t covered by the standard MS‑Project fields.

## ¿Por qué agregar una propiedad personalizada en Aspose.Tasks?

Aspose.Tasks supports **50+ input and output formats** and can handle projects with **up to 10,000 tasks** without loading the entire file into memory. Adding custom properties lets you embed business‑critical data directly in the project file, eliminating the need for external databases and ensuring the data travels with the project.

## Requisitos previos

- Visual Studio (cualquier edición reciente) instalado en su estación de trabajo.  
- Aspose.Tasks para .NET – descárguelo desde el [download link](https://releases.aspose.com/tasks/net/).  
- Familiaridad básica con la sintaxis de C# y la estructura de proyectos .NET.

## Importar espacios de nombres

The following namespaces give you access to the core project model and the custom property APIs.

```csharp
using Aspose.Tasks;
using System;


```

## ¿Cómo agregar una propiedad personalizada en Aspose.Tasks?

To add a custom property, first load the project, then create a `CustomProperty` object, set its name, type, and value, and finally add it to the project's `CustomProperties` collection. This operation embeds the metadata directly into the project file, and the changes are saved when you call `project.Save(...)`.  

`CustomProperty` represents a single user‑defined field attached to a project.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Paso 1: inicializar proyecto

`Project` is the primary class representing a project file in Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Paso 2: verificar la disponibilidad de la colección de propiedades personalizadas

`CustomProperties` is the collection that holds all custom property objects for a project.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Paso 3: agregar propiedades personalizadas

`Add` method inserts a new custom property into the project's collection.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Paso 4: acceder a las propiedades personalizadas

`CustomProperties` collection implements IEnumerable, allowing iteration over each `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Paso 5: obtener el valor de una propiedad personalizada

`Get` method returns the value of a custom property by its name.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Paso 6: iterar sobre los nombres de propiedades personalizadas

`Names` property provides a list of all custom property names in the collection.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Paso 7: eliminar o limpiar propiedades personalizadas

`Remove` method deletes a specific property, while `Clear` empties the entire collection.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Problemas comunes y solución de problemas

- **Colección de solo lectura** – If `project.CustomProperties.IsReadOnly` returns `true`, ensure the source file isn’t opened with exclusive read access or copy it to a writable location before editing.  
- **Incompatibilidad de tipo** – Assigning a value that doesn’t match the declared `CustomPropertyType` throws an `ArgumentException`. Always set the `Value` after defining the correct `Type`.  
- **Guardar cambios** – After adding or removing properties, call `project.Save("output.mpp")` to persist the modifications; otherwise changes remain in memory only.

## Preguntas frecuentes

**Q: ¿Puedo agregar propiedades personalizadas de cualquier tipo de datos a mi proyecto usando Aspose.Tasks para .NET?**  
A: Yes, you can add custom properties supporting Boolean, DateTime, Double, and String types.

**Q: ¿Es posible iterar sobre los nombres de propiedades personalizadas en Aspose.Tasks para .NET?**  
A: Absolutely, you can iterate over custom property names using the `Names` property.

**Q: ¿Cómo puedo eliminar una propiedad personalizada específica de mi proyecto?**  
A: You can remove a custom property by its name using the `Remove` method.

**Q: ¿Aspose.Tasks para .NET ofrece soporte para licencias temporales?**  
A: Yes, you can obtain a temporary license from the Aspose website for evaluation purposes.

**Q: ¿Dónde puedo encontrar soporte o asistencia adicional sobre Aspose.Tasks para .NET?**  
A: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any queries or assistance.

---

**Última actualización:** 2026-10-15  
**Probado con:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo leer propiedades de proyecto incorporadas usando Aspose.Tasks para .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Administrar la colección de atributos de MS Project en Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Tipos de campos personalizados de Aspose.Tasks – Calendario y programación](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}