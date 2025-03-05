---
title: Tipos de recursos en Aspose.Tasks
linktitle: Tipos de recursos en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a trabajar con diferentes tipos de recursos en Aspose.Tasks para .NET, incluidos recursos de trabajo, materiales y costos, a través de un tutorial paso a paso.
type: docs
weight: 14
url: /es/net/resource-risk-analysis/resource-types/
---
## Introducción
Aspose.Tasks para .NET es una poderosa biblioteca que permite a los desarrolladores trabajar con archivos de Microsoft Project mediante programación. Ya sea que esté administrando tareas, recursos u horarios, Aspose.Tasks simplifica el proceso al proporcionar un conjunto completo de API. En este tutorial, profundizaremos en los diferentes tipos de recursos que puede utilizar dentro de sus proyectos usando Aspose.Tasks para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Visual Studio: instale Visual Studio, un potente entorno de desarrollo integrado (IDE) para el desarrollo de .NET.
2.  Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/tasks/net/).
3. Conocimientos básicos de C#: familiarícese con C#, el lenguaje de programación utilizado para el desarrollo de .NET.

## Importar espacios de nombres
Primero, importemos los espacios de nombres necesarios para acceder a las funcionalidades de Aspose.Tasks para .NET:
```csharp
    
```

## Paso 1: crear una nueva instancia de proyecto
```csharp
var project = new Project();
```
Esta línea inicializa un nuevo objeto Proyecto, que sirve como contenedor para todos los datos y operaciones relacionados con el proyecto.
## Paso 2: agregar un recurso de trabajo
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Aquí, creamos un nuevo recurso de trabajo llamado "Recurso de trabajo" y especificamos su tipo como ResourceType.Work.
## Paso 3: agregue un recurso material
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
Este paso agrega un recurso material denominado "Recurso material" con su tipo establecido en ResourceType.Material. Además, especificamos la etiqueta del material como "kg" para indicar la unidad de medida.
## Paso 4: agregar un recurso de costo
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Finalmente, agregamos un recurso de costo llamado "Recurso de costo" y configuramos su tipo como ResourceType.Cost. Además, fijamos el valor del costo en 59,99, que representa el valor monetario asociado con este recurso.

## Conclusión
En este tutorial, exploramos cómo trabajar con diferentes tipos de recursos en Aspose.Tasks para .NET, incluidos recursos de trabajo, materiales y costos. Si sigue la guía paso a paso, podrá gestionar eficazmente los recursos dentro de sus proyectos mediante programación.
## Preguntas frecuentes
### P: ¿Puedo utilizar Aspose.Tasks para .NET con otros formatos de software de gestión de proyectos?
R: Sí, Aspose.Tasks admite varios formatos, incluidos Microsoft Project (MPP), Primavera P6 y más.
### P: ¿Hay una prueba gratuita disponible para Aspose.Tasks para .NET?
 R: Sí, puedes acceder a la prueba gratuita.[aquí](https://releases.aspose.com/).
### P: ¿Cómo puedo obtener soporte técnico para Aspose.Tasks para .NET?
 R: Puedes visitar el foro de Aspose.Tasks[aquí](https://forum.aspose.com/c/tasks/15) para asistencia técnica.
### P: ¿Puedo comprar una licencia temporal de Aspose.Tasks para .NET?
 R: Sí, puedes comprar una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### P: ¿Aspose.Tasks para .NET proporciona documentación como referencia?
 R: Sí, puedes encontrar la documentación.[aquí](https://reference.aspose.com/tasks/net/).