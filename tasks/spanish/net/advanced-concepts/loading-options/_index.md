---
date: 2026-03-08
description: Aprenda cómo importar un archivo de proyecto usando Aspose.Tasks para
  .NET, incluyendo cómo especificar la codificación del archivo y cargar el archivo
  de Microsoft Project de manera eficiente.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Importar archivo de proyecto – Opciones de carga en Aspose.Tasks
url: /es/net/advanced-concepts/loading-options/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Importar archivo de proyecto – Opciones de carga en Aspose.Tasks

## Introducción

Aspose.Tasks for .NET facilita la **importar archivo de proyecto** desde Microsoft Project, Primavera y otros formatos. Ya sea que necesite leer un archivo protegido con contraseña, establecer una codificación personalizada o manejar errores de análisis, la biblioteca le brinda un control granular mediante opciones de carga. En este tutorial recorreremos los escenarios más comunes para que pueda **cargar archivo de Microsoft Project** con confianza en sus aplicaciones .NET.

## Respuestas rápidas
- **¿Cuál es la forma principal de importar un archivo de proyecto?** Use the `Project` constructor with a `LoadOptions` instance.  
- **¿Puedo abrir archivos protegidos con contraseña?** Yes—set the `Password` property on `LoadOptions`.  
- **¿Cómo especifico la codificación del archivo?** Assign an `Encoding` object to `LoadOptions.Encoding`.  
- **¿Es personalizable el manejo de errores?** Absolutely—provide a delegate to `LoadOptions.ErrorHandler`.  
- **¿Estas opciones funcionan con archivos Primavera?** Yes, via `PrimaveraReadOptions` inside `LoadOptions`.

## Requisitos previos

Before diving in, make sure you have:

1. **Visual Studio** (o cualquier IDE .NET preferido).  
2. **Aspose.Tasks for .NET** – descárguelo desde el [website](https://releases.aspose.com/tasks/net/).  
3. Un conocimiento básico de la sintaxis de **C#** y la estructura del proyecto.

Ahora que estamos listos, importemos los espacios de nombres requeridos.

## Importar espacios de nombres

In your C# project, add the following `using` statements so the API classes are available:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## Cómo importar archivo de proyecto con opciones de carga

Below are four practical examples that cover the most frequent loading scenarios.

### Paso 1: Cargar un proyecto protegido con contraseña

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### Paso 2: Cargar un proyecto Primavera con opciones personalizadas

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### Paso 3: **Especificar codificación del archivo** al importar un archivo XER

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### Paso 4: Cargar un proyecto Primavera con manejo de errores personalizado

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

Al seguir estos pasos, puede importar datos de **archivo de proyecto** con precisión, adaptar el proceso de carga a sus necesidades y mantener su aplicación robusta.

## Problemas comunes y consejos

- **Contraseña incorrecta** – la propiedad `Password` lanzará una excepción; verifique la credencial antes de cargar.  
- **Codificación no compatible** – asegúrese de que la página de códigos que especifica exista en la máquina de destino (`Encoding.GetEncoding(1251)` funciona para cirílico).  
- **Faltan opciones de Primavera** – si necesita preservar los UID de tareas, establezca `PreserveUids = true`; de lo contrario pueden aparecer IDs duplicados.  
- **El manejador de errores devuelve null** – devolver `null` indica al analizador que omita el elemento problemático; personalícelo según sea necesario.

## Preguntas frecuentes

**P: ¿Es Aspose.Tasks for .NET compatible con todas las versiones de Microsoft Project?**  
R: Sí, admite una amplia gama de versiones de Microsoft Project, por lo que puede **cargar formatos de archivo de Microsoft Project** desde archivos MPP antiguos hasta los formatos más recientes.

**P: ¿Puedo integrar Aspose.Tasks for .NET con otras bibliotecas de terceros?**  
R: Absolutamente. La biblioteca funciona sin problemas con otros paquetes .NET, lo que le permite combinarla con frameworks de informes, UI o acceso a datos.

**P: ¿Aspose.Tasks for .NET proporciona documentación y recursos de soporte?**  
R: Sí, puede consultar la completa [documentación](https://reference.aspose.com/tasks/net/) y acceder al soporte a través del [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**P: ¿Hay opciones de licencia disponibles para Aspose.Tasks for .NET?**  
R: Sí, puede explorar diferentes opciones de licencia, incluidas pruebas gratuitas y licencias temporales, en el [sitio web de Aspose.Tasks](https://purchase.aspose.com/buy).

**P: ¿Con qué frecuencia se publican actualizaciones y nuevas funciones para Aspose.Tasks for .NET?**  
R: Aspose.Tasks recibe actualizaciones regulares que añaden funciones, mejoran el rendimiento y mantienen la compatibilidad con las últimas versiones de Microsoft Project.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}