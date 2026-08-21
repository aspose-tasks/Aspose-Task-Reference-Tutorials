---
date: 2026-03-19
description: Aprende a establecer la línea base del proyecto y gestionar eficientemente
  las líneas base de asignaciones con Aspose.Tasks para .NET, garantizando un seguimiento
  preciso del progreso del proyecto.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Establecer la línea base del proyecto – Gestionar la línea base de asignación
  en Aspose.Tasks
url: /es/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer la línea base del proyecto – Gestión de la línea base de asignaciones en Aspose.Tasks

## Introducción

Al trabajar en tareas de gestión de proyectos, **establecer una línea base del proyecto** es esencial para medir el progreso real frente al plan original. Aspose.Tasks para .NET no solo permite **establecer la línea base del proyecto**, sino que también brinda control total sobre las líneas base de asignaciones, habilitando un seguimiento preciso del rendimiento. En este tutorial recorreremos todo el proceso: cargar un proyecto, establecer una línea base, leer los datos de la línea base de asignaciones y comparar líneas base, para que puedas monitorear tus proyectos con confianza.

## Respuestas rápidas
- **¿Qué significa “establecer línea base del proyecto”?** Registra los datos originales de calendario y costo para compararlos posteriormente con el rendimiento real.  
- **¿Qué método de la API establece una línea base?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **¿Las líneas base de asignaciones requieren una llamada separada?** No, se almacenan automáticamente al establecer una línea base del proyecto.  
- **¿Qué formatos son compatibles?** MPP, XML, MPX y más a través de Aspose.Tasks.  
- **¿Se necesita una licencia para producción?** Sí, se requiere una licencia comercial para uso que no sea de prueba.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

- Conocimientos básicos de programación en C#.  
- Visual Studio (cualquier versión reciente).  
- Biblioteca Aspose.Tasks para .NET añadida a tu proyecto. Puedes descargarla [aquí](https://releases.aspose.com/tasks/net/).  
- Acceso a un archivo de proyecto en formato MPP (por ejemplo, `AssignmentBaseline2007.mpp`).

## Importar espacios de nombres

Agrega los espacios de nombres requeridos al inicio de tu archivo C# para que el compilador sepa dónde encontrar las clases de Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
```

## Paso 1: Cargar el proyecto y establecer la línea base del proyecto

Primero, carga el archivo MPP existente y luego llama a `SetBaseline` para **establecer la línea base del proyecto** para todo el proyecto.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Paso 2: Leer la información de la línea base de asignación

Una vez establecida la línea base, cada asignación de recurso contiene sus propios registros de línea base. El bucle a continuación extrae e imprime esos detalles, incluidos las fechas de inicio/fin, costo, trabajo y cualquier dato faseado en el tiempo.

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

## Paso 3: Comparar líneas base de asignaciones

Puedes comparar líneas base de diferentes asignaciones usando los operadores de igualdad y comparación incorporados. Esto es útil cuando necesitas detectar cambios de calendario o sobrecostos entre tareas.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Problemas comunes y soluciones

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **Los datos de la línea base aparecen vacíos** | El archivo del proyecto se abrió en modo solo lectura o nunca se estableció la línea base. | Llama a `project.SetBaseline(BaselineType.Baseline)` antes de leer las líneas base de asignación. |
| **`NullReferenceException` en `TimephasedData`** | No todas las líneas base contienen entradas faseadas en el tiempo. | Siempre verifica `baseline.TimephasedData != null` (como se muestra en el código). |
| **Recuperación incorrecta de UID** | Los valores UID difieren entre versiones de archivo. | Usa `ResourceAssignments.GetByUid` con el UID correcto o itera para encontrar la asignación que necesitas. |

## Preguntas frecuentes

**P: ¿Puede Aspose.Tasks manejar múltiples líneas base para una sola asignación?**  
R: Sí, Aspose.Tasks admite múltiples líneas base para cada asignación, lo que permite un seguimiento integral del progreso del proyecto a lo largo del tiempo.

**P: ¿Es Aspose.Tasks compatible con varios formatos de archivo de proyecto además de MPP?**  
R: Sí, Aspose.Tasks soporta una amplia gama de formatos de archivo de proyecto, incluidos XML, MPX y MPP, garantizando compatibilidad con diversas herramientas de gestión de proyectos.

**P: ¿Puedo modificar la información de la línea base programáticamente usando Aspose.Tasks?**  
R: Absolutamente, Aspose.Tasks proporciona APIs extensas para modificar la información de la línea base de forma dinámica según los requisitos del proyecto, ofreciendo flexibilidad y control sobre los procesos de gestión.

**P: ¿Aspose.Tasks ofrece documentación y recursos de soporte para desarrolladores?**  
R: Sí, los desarrolladores pueden acceder a documentación completa, tutoriales y foros en el sitio web de Aspose.Tasks, facilitando una integración fluida y la resolución de problemas.

**P: ¿Existe una versión de prueba disponible para Aspose.Tasks para .NET?**  
R: Sí, los desarrolladores pueden obtener una versión de prueba gratuita de Aspose.Tasks para .NET [aquí](https://releases.aspose.com/), lo que les permite evaluar sus características y capacidades antes de decidir una compra.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-03-19  
**Probado con:** Aspose.Tasks 24.12 para .NET  
**Autor:** Aspose  

---