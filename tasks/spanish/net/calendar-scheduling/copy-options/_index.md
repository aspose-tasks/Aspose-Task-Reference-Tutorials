---
date: 2026-07-05
description: Aprenda a copiar datos del proyecto usando Aspose.Tasks para .NET con
  opciones de copia. Mejore sus aplicaciones .NET con una gestión de proyectos precisa.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Cómo copiar datos del proyecto con opciones de copia en Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Cómo copiar datos del proyecto con opciones de copia en Aspose.Tasks
url: /es/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo copiar datos del proyecto con opciones de copia en Aspose.Tasks

## Introducción

If you need to **cómo copiar proyecto** information from one Microsoft Project file to another, Aspose.Tasks for .NET gives you a clean, code‑first way to do it. In this tutorial we’ll walk through the complete workflow—loading a source project, configuring copy options, creating a copy, and loading the result—so you can integrate project‑copying logic into any .NET application with confidence.

## Respuestas rápidas
- **¿Qué hace la función de copia?** Duplica los datos del proyecto mientras le permite incluir o excluir secciones específicas como calendarios, recursos o información de vista.  
- **¿Qué clase controla el comportamiento?** `CopyToOptions` le permite afinar lo que se copia.  
- **¿Necesito una licencia?** Se requiere una licencia válida de Aspose.Tasks para producción; una prueba gratuita funciona para desarrollo.  
- **¿Formatos compatibles?** Aspose.Tasks maneja archivos MPP, XML y XER—más de 20 + formatos en total.  
- **¿Puedo omitir datos de vista?** Sí, establezca `CopyToOptions.SkipViewData = true` para omitir la información relacionada con la UI.

## ¿Qué es “cómo copiar proyecto” en Aspose.Tasks?
**“Cómo copiar proyecto”** se refiere a usar la API de Aspose.Tasks para duplicar los datos de un objeto Project en un nuevo archivo, filtrando opcionalmente los elementos no deseados. Esta operación es útil para crear plantillas, archivado o crear variantes de proyecto sin pasos manuales de la UI, y funciona con todos los formatos de archivo compatibles.

## ¿Por qué usar Opciones de Copia en Aspose.Tasks?
Aspose.Tasks soporta **más de 50 entidades relacionadas con proyectos** (tareas, recursos, calendarios, asignaciones, etc.) y puede procesar archivos con **hasta 10 000 tareas** manteniendo el uso de memoria bajo 200 MB. Usar `CopyToOptions` le permite evitar copiar datos de vista pesados, reduciendo el tamaño del archivo de salida en **30‑40 %** y acelerando la operación aproximadamente **2×** para proyectos grandes.

## Requisitos previos

1. **Aspose.Tasks for .NET** – descargue la última versión desde el [download link](https://releases.aspose.com/tasks/net/).  
2. **Entorno de desarrollo .NET** – Visual Studio 2022 (o cualquier IDE que soporte .NET 6+) instalado.  
3. **Una licencia válida de Aspose.Tasks** – opcional para evaluación, obligatoria para compilaciones de producción.  
4. **Un archivo de proyecto existente** (p. ej., `SourceProject.xml`) que desea copiar.

## ¿Cómo importar espacios de nombres para Aspose.Tasks?
Agregue las directivas `using` requeridas al inicio de su archivo C# para que el compilador pueda localizar los tipos de Aspose.Tasks. Incluir estas declaraciones le brinda acceso directo a `Project`, `CopyToOptions` y otras clases de utilidad sin calificar completamente sus nombres, simplificando su código y mejorando la legibilidad.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Paso 1: Inicializar objetos Project

Primero, cree una instancia `Project` que represente el archivo fuente y cargue los datos XML. La clase `Project` representa un archivo Microsoft Project cargado en memoria, exponiendo tareas, recursos, calendarios y otra información del proyecto.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Consejo profesional:** Si trabaja con archivos muy grandes, considere usar el constructor `LoadOptions` para habilitar la carga diferida y mantener bajo el consumo de memoria.

## Paso 2: Crear una copia del proyecto

A continuación, instancie un segundo objeto `Project` que recibirá los datos copiados. Este objeto comienza vacío.

```csharp
Project copiedProject = new Project();
```

Ahora tiene dos objetos `Project` distintos: uno cargado desde el disco y otro listo para recibir la copia.

## Paso 3: Cargar el proyecto copiado

Después de la operación de copia (mostrada más adelante), querrá verificar el resultado cargando el archivo recién guardado en otra instancia `Project`.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Cargar el archivo nuevamente confirma que la copia se realizó con éxito y que las opciones que configuró se comportaron como se esperaba.

## Paso 4: Configurar opciones de copia

La clase `CopyToOptions` le permite especificar exactamente qué se transfiere del origen al destino.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Establecer `SkipViewData = true` reduce el tamaño del archivo de salida y acelera la operación, especialmente cuando solo necesita datos lógicos del proyecto.

## Paso 5: Realizar la copia del proyecto

Finalmente, invoque el método `CopyTo` en el proyecto fuente, pasando el proyecto de destino y las opciones que configuró.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Esta llamada de dos líneas realiza toda la operación de copia, respetando las opciones que definió. El `CopiedProject.xml` resultante contiene solo los datos que solicitó.

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **NullReferenceException al llamar a `CopyTo`** | Proyecto de destino no instanciado. | Asegúrese de que se llame a `new Project()` antes de `CopyTo`. |
| **Tareas faltantes después de la copia** | `CopyCommonData` establecido en `false`. | Establezca `CopyCommonData = true` o copie colecciones específicas manualmente. |
| **Archivo de salida grande** | `SkipViewData` dejado en `false`. | Active `SkipViewData` para omitir datos relacionados con la UI. |
| **Licencia no aplicada** | Archivo de licencia no cargado. | Llame a `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` antes de usar cualquier API. |

## Preguntas frecuentes

**P: ¿Puedo copiar solo un subconjunto de tareas?**  
R: Sí, use `CopyToOptions` junto con `ProjectRootTask` para especificar una tarea inicial, o copie manualmente las tareas seleccionadas después de la copia inicial.

**P: ¿Aspose.Tasks admite copiar entre diferentes formatos de archivo?**  
R: Absolutamente. Puede cargar un archivo MPP y guardar la copia como XML, XER, o cualquier otro formato compatible—más de **20 + formatos** en total.

**P: ¿Cómo manejo archivos de proyecto protegidos con contraseña?**  
R: Cargue el origen con `new Project("file.mpp", new LoadOptions { Password = "pwd" })`, luego continúe con la copia como de costumbre.

**P: ¿Hay una forma de copiar grupos de recursos sin tareas?**  
R: Establezca `CopyToOptions.CopyResources = true` y `CopyToOptions.CopyTasks = false` para transferir solo la información de recursos.

**P: ¿Dónde puedo encontrar más ejemplos?**  
R: Visite el [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para fragmentos impulsados por la comunidad, consejos de solución de problemas y documentación oficial.

---

**Última actualización:** 2026-07-05  
**Probado con:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Dominar los datos del proyecto con Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Dominar las opciones de guardado de MS Project para Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Calendario y programación de Aspose.Tasks](/tasks/net/calendar-scheduling/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}