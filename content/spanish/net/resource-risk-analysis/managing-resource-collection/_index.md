---
title: Gestión de la recopilación de recursos del proyecto en Aspose.Tasks
linktitle: Gestión de la recopilación de recursos en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar de manera eficiente las colecciones de recursos de Microsoft Project en .NET usando la API Aspose.Tasks. Incrementar la productividad y la flexibilidad.
type: docs
weight: 13
url: /es/net/resource-risk-analysis/managing-resource-collection/
---
## Introducción
En este tutorial, exploraremos cómo administrar eficazmente las colecciones de recursos de Microsoft Project utilizando Aspose.Tasks para .NET. Aspose.Tasks es una potente API que permite a los desarrolladores trabajar con archivos de Microsoft Project mediante programación, lo que permite una integración y manipulación perfecta de los datos del proyecto.
## Requisitos previos
Antes de sumergirse en este tutorial, asegúrese de tener los siguientes requisitos previos:
1. Conocimiento de C# y .NET Framework: este tutorial asume familiaridad con el lenguaje de programación C# y .NET Framework.
2. Instalación de Aspose.Tasks para .NET: asegúrese de haber instalado Aspose.Tasks para .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/net/).
3. Configuración del entorno de desarrollo: configure su entorno de desarrollo con Visual Studio o cualquier otro IDE preferido.

## Importar espacios de nombres
Antes de comenzar, importe los espacios de nombres necesarios para acceder a las funcionalidades de Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Paso 1: cargue el archivo del proyecto
En primer lugar, cargue el archivo de Microsoft Project en el objeto del proyecto Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## Paso 2: agregar recurso vacío
A continuación, agreguemos un recurso vacío al proyecto:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## Paso 3: agregar recurso con un nombre
Ahora, agregue un recurso con un nombre específico al proyecto:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## Paso 4: agregar recurso antes que otro recurso
Agregue un recurso con un nombre específico antes de otro recurso según su ID:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## Paso 5: acceder a los recursos por ID o UID
Puede acceder a los recursos ya sea por su ID o UID:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## Paso 6: Imprimir información de recursos
Imprimir información sobre los recursos del proyecto:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## Paso 7: Eliminar recursos
Eliminar recursos del proyecto:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## Conclusión
La gestión de colecciones de recursos de Microsoft Project mediante Aspose.Tasks para .NET proporciona a los desarrolladores un sólido conjunto de herramientas para manejar de manera eficiente los recursos del proyecto mediante programación. Si sigue los pasos descritos en este tutorial, podrá manipular sin problemas los recursos dentro de sus proyectos, mejorando la productividad y la flexibilidad en las tareas de gestión de proyectos.
## Preguntas frecuentes
### P: ¿Puede Aspose.Tasks manejar archivos de proyectos de gran escala?

R: Sí, Aspose.Tasks está diseñado para manejar archivos de proyectos de gran escala de manera eficiente, ofreciendo alto rendimiento y confiabilidad.

### P: ¿Aspose.Tasks es compatible con diferentes versiones de Microsoft Project?

R: Aspose.Tasks admite varias versiones de Microsoft Project, lo que garantiza la compatibilidad entre diferentes entornos.

### P: ¿Puedo personalizar las propiedades de los recursos usando Aspose.Tasks?

R: Por supuesto, Aspose.Tasks proporciona amplias capacidades para personalizar las propiedades de los recursos de acuerdo con los requisitos específicos del proyecto.

### P: ¿Aspose.Tasks admite subprocesos múltiples para operaciones simultáneas?

R: Sí, Aspose.Tasks admite subprocesos múltiples, lo que permite operaciones simultáneas en los datos del proyecto para mejorar el rendimiento.

### P: ¿Hay soporte técnico disponible para los usuarios de Aspose.Tasks?

 R: Sí, los usuarios de Aspose.Tasks pueden acceder a soporte técnico a través del foro.[aquí](https://forum.aspose.com/c/tasks/15).