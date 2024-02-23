---
title: Gestión de la línea base de tareas en Aspose.Tasks
linktitle: Gestión de la línea base de tareas en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a gestionar las líneas base de tareas de manera eficiente con Aspose.Tasks para .NET, garantizando un seguimiento preciso del progreso y el rendimiento del proyecto.
type: docs
weight: 14
url: /es/net/advanced-features/assignment-baseline/
---
## Introducción

Cuando se trabaja en tareas de gestión de proyectos, gestionar las líneas base de las asignaciones es crucial para realizar un seguimiento preciso del progreso. Aspose.Tasks para .NET proporciona un conjunto completo de herramientas para manejar las líneas base de asignación de manera eficiente. En este tutorial, profundizaremos en el proceso de gestión de líneas base de asignaciones paso a paso.

## Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Visual Studio instalado en su sistema.
- Biblioteca Aspose.Tasks para .NET agregada a su proyecto. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/net/).
- Acceso a un archivo de proyecto en formato MPP.

## Importar espacios de nombres

Para comenzar a trabajar con Aspose.Tasks, debe importar los espacios de nombres necesarios a su proyecto C#. Agregue los siguientes espacios de nombres al principio de su archivo C#:

```csharp
using Aspose.Tasks;
using System;


```

## Paso 1: cargar el proyecto y establecer la línea base

 En primer lugar, cargue el archivo del proyecto usando el`Project` clase de Aspose.Tasks. Luego, establezca el tipo de línea base para el proyecto usando el`SetBaseline` método.

```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Paso 2: leer la información inicial de la tarea

Repita cada asignación de recursos en el proyecto y recupere información de referencia para cada asignación.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Paso 3: verificar la igualdad de referencia

Compare la información de referencia para diferentes asignaciones utilizando varios métodos de comparación proporcionados por Aspose.Tasks.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Verificar la igualdad de referencia
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Verifique la comparación de referencia
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Mostrar códigos hash de referencia
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Conclusión

La gestión de líneas base de asignaciones es parte integral de la gestión de proyectos, lo que permite un seguimiento preciso del progreso y el desempeño. Con Aspose.Tasks para .NET, el manejo de líneas base de asignaciones se vuelve ágil y eficiente, brindando a los desarrolladores herramientas poderosas para mejorar los flujos de trabajo de gestión de proyectos.

## Preguntas frecuentes

### P1: ¿Puede Aspose.Tasks manejar múltiples líneas de base para una sola tarea?

R1: Sí, Aspose.Tasks admite múltiples líneas de base para cada tarea, lo que permite un seguimiento integral del progreso del proyecto a lo largo del tiempo.

### P2: ¿Aspose.Tasks es compatible con varios formatos de archivos de proyecto además de MPP?

R2: Sí, Aspose.Tasks admite una amplia gama de formatos de archivos de proyectos, incluidos XML, MPX y MPP, lo que garantiza la compatibilidad con varias herramientas de gestión de proyectos.

### P3: ¿Puedo modificar la información de referencia mediante programación usando Aspose.Tasks?

R3: Por supuesto, Aspose.Tasks proporciona amplias API para modificar la información de referencia dinámicamente según los requisitos del proyecto, ofreciendo flexibilidad y control sobre los procesos de gestión de proyectos.

### P4: ¿Aspose.Tasks ofrece documentación y recursos de soporte para desarrolladores?

R4: Sí, los desarrolladores pueden acceder a documentación completa, tutoriales y foros en el sitio web Aspose.Tasks, lo que facilita una integración y resolución de problemas sin problemas.

### P5: ¿Existe una versión de prueba disponible de Aspose.Tasks para .NET?

 R5: Sí, los desarrolladores pueden obtener una versión de prueba gratuita de Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/), permitiéndoles evaluar sus características y capacidades antes de tomar una decisión de compra.