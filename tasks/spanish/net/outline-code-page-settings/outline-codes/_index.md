---
title: Administrar códigos de esquema de proyecto en Aspose.Tasks para .NET
linktitle: Gestión de códigos de esquema en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar códigos de esquema de MS Project con Aspose.Tasks para .NET. Simplifique la organización del proyecto sin esfuerzo.
weight: 10
url: /es/net/outline-code-page-settings/outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Administrar códigos de esquema de proyecto en Aspose.Tasks para .NET

## Introducción
En este tutorial, exploraremos cómo administrar códigos de esquema de Microsoft Project usando Aspose.Tasks para .NET. Los códigos de esquema son campos personalizados en Microsoft Project que permiten a los usuarios categorizar y organizar tareas según criterios específicos. Aspose.Tasks simplifica el proceso de lectura y manipulación de estos códigos de esquema mediante programación.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1.  Biblioteca Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks para .NET desde[sitio web](https://releases.aspose.com/tasks/net/).
2. Entorno de desarrollo: configure un entorno de desarrollo adecuado para la programación .NET, como Visual Studio.
3. Conocimientos básicos de C#: la familiaridad con el lenguaje de programación C# será beneficiosa para comprender los ejemplos de código.

## Importando espacios de nombres
Para comenzar, necesita importar los espacios de nombres necesarios a su proyecto C#. Esto le permite acceder a las clases y métodos proporcionados por la biblioteca Aspose.Tasks.
1. Abra Visual Studio: inicie su IDE de Visual Studio.
2. Cree un nuevo proyecto: inicie un nuevo proyecto de C# o abra uno existente en el que desee utilizar Aspose.Tasks.
3. Agregue la referencia de Aspose.Tasks: haga clic derecho en su proyecto en el Explorador de soluciones, seleccione "Administrar paquetes NuGet", busque "Aspose.Tasks" e instale la última versión.
4. Importe el espacio de nombres Aspose.Tasks: en la parte superior de su archivo C#, agregue la siguiente directiva de uso:
```csharp
using Aspose.Tasks;
using System;

```
## Paso 1: definir el directorio de documentos
Primero, establezca la ruta al directorio que contiene su archivo de MS Project.
```csharp
String DataDir = "Your Document Directory";
```
 Reemplazar`"Your Document Directory"` con la ruta real a su archivo de proyecto.
## Paso 2: cargue el archivo del proyecto
 Crear una instancia nueva`Project` objeto cargando el archivo de MS Project.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Esto inicializa el objeto del proyecto con el archivo especificado.
## Paso 3: leer los códigos de esquema
Repita todas las tareas del proyecto y recupere sus códigos de esquema.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
Este fragmento de código recorre cada tarea, verifica si tiene códigos de esquema e imprime detalles como ID de campo, Guía de valor e ID de valor para cada código de esquema asociado con la tarea.

## Conclusión
En conclusión, Aspose.Tasks para .NET proporciona poderosas capacidades para administrar códigos de esquema de Microsoft Project mediante programación. Si sigue los pasos descritos en este tutorial, puede leer y manipular códigos de esquema de manera eficiente en sus archivos de MS Project usando C#.
## Preguntas frecuentes
### P: ¿Puedo modificar códigos de esquema usando Aspose.Tasks?
R: Sí, puede modificar códigos de esquema mediante programación utilizando Aspose.Tasks para .NET. Simplemente acceda a los códigos de esquema de las tareas y actualice sus valores según sea necesario.
### P: ¿Aspose.Tasks es compatible con todas las versiones de Microsoft Project?
R: Aspose.Tasks admite una amplia gama de versiones de Microsoft Project, incluidas 2003, 2007, 2010, 2013, 2016 y 2019.
### P: ¿Aspose.Tasks requiere una licencia para uso comercial?
R: Sí, se requiere una licencia válida para el uso comercial de Aspose.Tasks. Puede obtener una licencia en el sitio web de Aspose.
### P: ¿Puedo probar Aspose.Tasks antes de comprarlo?
R: Sí, puede descargar una versión de prueba gratuita de Aspose.Tasks desde el sitio web para evaluar sus características y capacidades.
### P: ¿Dónde puedo obtener soporte para Aspose.Tasks?
 R: Puede obtener soporte para Aspose.Tasks visitando el foro en[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Código fuente completo
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
