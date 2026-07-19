---
date: 2026-07-19
description: Aprenda cómo agregar tipos de campo personalizados en Aspose.Tasks para
  .NET con código paso a paso, prerequisites y FAQs.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Tipos de campo personalizados en Aspose.Tasks
og_description: Aprenda cómo agregar tipos de campo personalizados en Aspose.Tasks
  para .NET. Siga esta guía paso a paso para crear, definir y usar extended attributes
  de manera eficiente.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Cómo agregar tipos de campo personalizados en Aspose.Tasks para .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Cómo agregar tipos de campo personalizados en Aspose.Tasks para .NET
url: /es/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar tipos de campo personalizados en Aspose.Tasks

## Introducción

En este tutorial descubrirás **cómo agregar un campo personalizado** tipos a un archivo Microsoft Project usando Aspose.Tasks para .NET. Los campos personalizados te permiten almacenar información adicional—como puntuaciones de riesgo, códigos de departamento o notas personalizadas—directamente en tareas, recursos o en el propio proyecto. Recorreremos todo el proceso, desde la configuración del entorno hasta la definición, adición y verificación de un campo de texto personalizado.

## Respuestas rápidas
- **¿Qué es un campo personalizado?** Una columna definida por el usuario que puede contener texto, números, fechas o indicadores en tareas/recursos.  
- **¿Qué clase define un campo personalizado?** `ExtendedAttributeDefinition`.  
- **¿Puedo agregar un campo personalizado a un proyecto existente?** Sí—cargue el proyecto, cree la definición y luego agréguela a la colección.  
- **¿Necesito una licencia para Aspose.Tasks?** Se requiere una licencia para producción; una prueba gratuita funciona para evaluación.  
- **¿Versiones .NET compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qué es “how to add custom field” en Aspose.Tasks?
**Cómo agregar un campo personalizado** se refiere al proceso de crear un `ExtendedAttributeDefinition` y adjuntarlo a la colección `ExtendedAttributes` de un proyecto. Esto te permite almacenar metadatos extra que no forman parte del esquema estándar de Project. Puede usarse para tareas, recursos o el propio proyecto, permitiéndote capturar información como niveles de riesgo, códigos de departamento o notas personalizadas que no están disponibles en los campos predeterminados.

## ¿Por qué usar campos personalizados en la gestión de proyectos?
Aspose.Tasks soporta **más de 50 tipos de atributos extendidos incorporados** y te permite definir **cualquier número de campos personalizados** sin afectar significativamente el tamaño del archivo. Al usar campos personalizados puedes:  
Estos campos aparecen como columnas adicionales en Microsoft Project y pueden referenciarse en fórmulas, informes y filtros. Se almacenan dentro del archivo del proyecto y viajan con él, asegurando que cualquier herramienta posterior conserve los datos personalizados.

## Requisitos previos

### 1. Visual Studio instalado
Asegúrate de que Visual Studio (2019 o posterior) esté en tu máquina. Puedes descargarlo desde el sitio web de Microsoft.

### 2. Aspose.Tasks para .NET
Agrega el paquete NuGet de Aspose.Tasks a tu proyecto. Descarga la última versión desde [here](https://releases.aspose.com/tasks/net/).

### 3. Conocimientos básicos de C#
Deberías sentirte cómodo con la sintaxis de C#, clases y la estructura de proyectos .NET.

## Importar espacios de nombres

El `Project`, `ExtendedAttributeDefinition` y los enums relacionados viven en el espacio de nombres `Aspose.Tasks`. Importa este espacio al inicio de tu archivo:

El espacio de nombres `Aspose.Tasks` proporciona todos los tipos centrales para manejar archivos Microsoft Project.

```csharp

```

## Cómo agregar un campo personalizado a un proyecto?

Carga el proyecto existente, crea una definición de campo personalizado y agrégala a la colección de atributos extendidos del proyecto—todo en tres pasos concisos. Este patrón funciona para tareas, recursos y el propio proyecto, y garantiza que el campo personalizado se conserve al guardar el archivo.

### Paso 1: Crear objeto Project
`Project` es el objeto de nivel superior de Aspose.Tasks que representa un archivo Project único en memoria. Instanciarlo carga el archivo y te brinda acceso a tareas, recursos y atributos extendidos.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Paso 2: Definir campo personalizado
`ExtendedAttributeDefinition` describe una nueva columna. En este ejemplo creamos un campo personalizado de tipo **Text** para tareas y le damos el alias “MyText”. El valor del enum `ExtendedAttributeTask.Text1` indica a Aspose.Tasks dónde almacenar el valor.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Paso 3: Agregar la definición del campo personalizado al proyecto
La colección `ExtendedAttributes` del proyecto contiene todas las definiciones de campos personalizados. Agregar la definición la hace disponible para cada tarea del proyecto.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Problemas comunes y soluciones
- **El campo no aparece en la interfaz de MS Project** – Asegúrate de establecer la propiedad `Alias`; MS Project muestra el alias como encabezado de columna.  
- **Al guardar se lanza una excepción** – Verifica que el archivo del proyecto no sea de solo lectura y que tengas una licencia válida.  
- **Los valores del campo personalizado se pierden después de recargar** – Asegúrate de llamar a `project.Save("output.mpp")` después de asignar valores a las tareas.

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Tasks con otros frameworks .NET?**  
A: Sí, Aspose.Tasks funciona con .NET Framework, .NET Core y .NET 5/6/7.

**Q: ¿Aspose.Tasks es adecuado para aplicaciones a nivel empresarial?**  
A: Absolutamente. Soporta el procesamiento de proyectos con **hasta 10,000 tareas** y puede ejecutarse en entornos de servidor multihilo.

**Q: ¿Aspose.Tasks admite varios formatos de archivo de proyecto?**  
A: Sí—Aspose.Tasks lee y escribe formatos MPP, XML, HTML y CSV, cubriendo **todas las versiones principales de Microsoft Project**.

**Q: ¿Puedo manipular datos de recursos usando Aspose.Tasks?**  
A: Sí, puedes agregar, actualizar y eliminar recursos, así como asignarles campos personalizados.

**Q: ¿Existe un foro comunitario para usuarios de Aspose.Tasks?**  
A: Sí, puedes visitar el [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para interactuar con otros usuarios y obtener soporte del equipo de Aspose.

---

**Última actualización:** 2026-07-19  
**Probado con:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Dominar definiciones de atributos extendidos de MS Project en Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Manipular atributos extendidos de MS Project con Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Integración de Field Helper MS Project en Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}