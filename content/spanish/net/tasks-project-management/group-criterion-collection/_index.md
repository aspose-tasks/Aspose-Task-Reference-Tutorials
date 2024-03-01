---
title: Administre los criterios del grupo de proyectos de MS con Aspose.Tasks
linktitle: Gestión de la recopilación de criterios de grupo en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar la colección de Group Criterion MS Project usando Aspose.Tasks para .NET. Guía paso a paso para desarrolladores.
type: docs
weight: 28
url: /es/net/tasks-project-management/group-criterion-collection/
---
## Introducción
Aspose.Tasks para .NET es una potente API que permite a los desarrolladores trabajar con archivos de Microsoft Project mediante programación. En este tutorial, exploraremos cómo administrar la colección de criterios de grupo dentro de MS Project usando Aspose.Tasks.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1.  Aspose.Tasks para .NET: asegúrese de tener la biblioteca Aspose.Tasks instalada en su proyecto .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/net/).

2. Archivo de Microsoft Project: tenga un archivo de Microsoft Project (MPP) listo para trabajar.

## Importar espacios de nombres

En primer lugar, debe importar los espacios de nombres necesarios a su código C#. Este paso es crucial para acceder a las funcionalidades proporcionadas por Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Paso 1: cargue el archivo del proyecto

 Inicializar un`Project` objeto cargando el archivo MPP. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Paso 2: Acceda a los criterios del grupo

Recuperar el grupo del proyecto y acceder a sus criterios.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Paso 3: iterar sobre los criterios del grupo

Recorra cada criterio del grupo y muestre sus propiedades.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Paso 4: Borrar los criterios del grupo

Borre los criterios del grupo existente si no es de solo lectura.

```csharp
group.GroupCriteria.Clear();
```

## Paso 5: agregar un nuevo criterio

Cree un nuevo criterio de grupo y agréguelo al grupo.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Paso 6: copiar criterios a otro grupo

Copie los criterios de un grupo a otro.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Conclusión

En este tutorial, hemos aprendido cómo administrar la colección Group Criterion MS Project usando Aspose.Tasks para .NET. Si sigue estos pasos, podrá manipular eficazmente los criterios de grupo dentro de sus archivos de Microsoft Project mediante programación.

## Preguntas frecuentes

### P1: ¿Aspose.Tasks es compatible con todas las versiones de Microsoft Project?

R: Sí, Aspose.Tasks admite archivos de Microsoft Project de varias versiones, incluidas 2003, 2007, 2010, 2013 y 2016.

### P2: ¿Puedo aplicar varios criterios a un solo grupo?

R: Por supuesto, puede agregar varios criterios a un grupo iterando cada uno de ellos y agregándolos en consecuencia.

### P3: ¿Existe una versión de prueba disponible para Aspose.Tasks?

 R: Sí, puede obtener una prueba gratuita de Aspose.Tasks desde[aquí](https://releases.aspose.com/).

### P4: ¿Dónde puedo encontrar documentación para Aspose.Tasks?

 R: Puede consultar la documentación.[aquí](https://reference.aspose.com/tasks/net/).

### P5: ¿Cómo puedo obtener asistencia si tengo algún problema?

 R: Si tiene alguna pregunta o enfrenta algún problema, puede buscar ayuda en el foro Aspose.Tasks.[aquí](https://forum.aspose.com/c/tasks/15).