---
title: Opciones para cargar en Aspose.Tasks
linktitle: Opciones para cargar en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda cómo aprovechar el poder de Aspose.Tasks para .NET para administrar de manera eficiente documentos de Microsoft Project con una guía paso a paso.
type: docs
weight: 16
url: /es/net/advanced-concepts/loading-options/
---
## Introducción

Aspose.Tasks para .NET es una poderosa biblioteca que permite a los desarrolladores manipular documentos de Microsoft Project mediante programación. Ya sea que necesite crear, leer, escribir o convertir archivos de proyecto, Aspose.Tasks proporciona una amplia gama de funcionalidades para optimizar sus tareas. En este tutorial, profundizaremos en los conceptos básicos del uso de Aspose.Tasks para .NET, dividiendo los procesos clave en pasos simples y prácticos.

## Requisitos previos

Antes de sumergirse en Aspose.Tasks para .NET, asegúrese de tener configurados los siguientes requisitos previos:

1. Visual Studio: instale Visual Studio o cualquier otro IDE de su elección.
2.  Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks para .NET desde[sitio web](https://releases.aspose.com/tasks/net/).
3. Comprensión básica de C#: familiarícese con los fundamentos del lenguaje de programación C#.

Ahora que tenemos cubiertos nuestros requisitos previos, exploremos los espacios de nombres esenciales y profundicemos en la guía paso a paso.

## Importando espacios de nombres

En su proyecto C#, importe los espacios de nombres necesarios para acceder a las funcionalidades de Aspose.Tasks:

1. Aspose.Tasks: este espacio de nombres proporciona clases e interfaces principales para trabajar con documentos del proyecto.

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

Ahora, dividamos las diferentes tareas en guías paso a paso.

## Paso 1: cargar proyectos protegidos con contraseña

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Inicialice FileStream para cargar el archivo del proyecto
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Crear instancia de LoadOptions
        var options = new LoadOptions
        {
            Password = "password" // Establecer la contraseña
        };

        // Cargue el proyecto con las opciones especificadas.
        var project = new Project(stream, options);

        // Mostrar nombre del proyecto
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

## Paso 2: cargar proyectos Primavera con opciones personalizadas

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Crear instancia de LoadOptions
    var loadOptions = new LoadOptions();

    // Configurar las opciones de lectura de Primavera
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Establecer el UID del proyecto
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Configurar las opciones de lectura de Primavera
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Cargue el proyecto Primavera con las opciones especificadas
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Mostrar nombre del proyecto
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Realizar más operaciones con el proyecto cargado
}
```

## Paso 3: especificar la codificación del archivo

```csharp
public void SpecifyFileEncoding()
{
    // Crear instancia de LoadOptions
    LoadOptions lo = new LoadOptions();

    // Especificar codificación al abrir un proyecto desde un archivo Primavera XER
    lo.Encoding = Encoding.GetEncoding(1251);

    // Cargue el proyecto con la codificación especificada
    var project = new Project("encoding1251.xer", lo);

    // Realizar más operaciones con el proyecto cargado
}
```

## Paso 4: cargar proyectos Primavera con manejo de errores

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Crear instancia de LoadOptions
    var loadOptions = new LoadOptions();

    // Configurar las opciones de lectura de Primavera
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Establecer el UID del proyecto
    };

    // Configurar las opciones de lectura de Primavera
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //Establecer manejo de errores personalizado
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Cargue el proyecto Primavera con opciones especificadas y manejo de errores.
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Realizar más operaciones con el proyecto cargado
}

// Método de manejo de errores personalizado
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implementar lógica de manejo de errores personalizada
}
```

Si sigue estos pasos, podrá utilizar eficazmente las opciones de carga en Aspose.Tasks para .NET para manipular los documentos del proyecto según sus requisitos.

## Conclusión

En este tutorial, exploramos los fundamentos del trabajo con opciones de carga en Aspose.Tasks para .NET. Desde cargar proyectos protegidos con contraseña hasta especificar un manejo de errores personalizado, dominar estas técnicas le permitirá administrar de manera eficiente archivos de Proyecto dentro de sus aplicaciones .NET.

## Preguntas frecuentes

### P1: ¿Aspose.Tasks para .NET es compatible con todas las versiones de Microsoft Project?

R1: Sí, Aspose.Tasks para .NET admite varias versiones de Microsoft Project, lo que garantiza la compatibilidad entre diferentes entornos.

### P2: ¿Puedo integrar Aspose.Tasks para .NET con otras bibliotecas de terceros?

R2: Por supuesto, Aspose.Tasks para .NET se integra perfectamente con otras bibliotecas .NET, ofreciendo funcionalidad y flexibilidad mejoradas.

### P3: ¿Aspose.Tasks para .NET proporciona documentación y recursos de soporte?

 A3: Sí, puede consultar el completo[documentación](https://reference.aspose.com/tasks/net/) y acceder a soporte a través del[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P4: ¿Existen opciones de licencia disponibles para Aspose.Tasks para .NET?

 R4: Sí, puede explorar diferentes opciones de licencia, incluidas pruebas gratuitas y licencias temporales, en la página[Sitio web de Aspose.Tasks](https://purchase.aspose.com/buy).

### P5: ¿Con qué frecuencia se publican actualizaciones y nuevas funciones para Aspose.Tasks para .NET?

R5: Aspose.Tasks para .NET recibe actualizaciones periódicas y mejoras de funciones para garantizar un rendimiento óptimo y compatibilidad con tecnologías en evolución.