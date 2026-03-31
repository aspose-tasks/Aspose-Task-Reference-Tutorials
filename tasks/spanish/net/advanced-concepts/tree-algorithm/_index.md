---
date: 2026-03-19
description: Aprende cómo agregar recursos al proyecto y calcular la duración de las
  tareas usando el algoritmo de árbol de Aspose.Tasks, y asignar recursos a las tareas
  en .NET.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Agregar recurso al proyecto con algoritmo de árbol en Aspose.Tasks
url: /es/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar recurso al proyecto con el algoritmo de árbol en Aspose.Tasks

## Introducción

En este tutorial descubrirá **cómo agregar un recurso al proyecto** aprovechando el potente algoritmo de árbol suministrado por Aspose.Tasks para .NET. Recorreremos la creación de una jerarquía de tareas, el cálculo de la duración de las tareas y la asignación de recursos a las tareas, todo de manera clara, paso a paso, que podrá copiar en su propia solución.

## Respuestas rápidas
- **¿Qué hace el algoritmo de árbol?** Recorre una jerarquía de tareas para agregar valores de trabajo de manera eficiente.  
- **¿Qué operación principal cubre esta guía?** Agregar un recurso a un proyecto y actualizar los totales de trabajo.  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para uso en producción.  
- **¿Puedo usar esto con .NET Core?** Sí, Aspose.Tasks admite .NET Framework y .NET Core.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un archivo de proyecto básico.

## ¿Qué es “agregar recurso al proyecto” en Aspose.Tasks?

Agregar un recurso a un proyecto significa crear un objeto `Resource`, definir su tipo (p. ej., trabajo) y vincularlo a una o más tareas mediante `ResourceAssignments`. Esto permite que el planificador calcule el esfuerzo, el costo y la duración total del proyecto.

## ¿Por qué usar el algoritmo de árbol para los cálculos del trabajo de recursos?

El algoritmo de árbol recorre el árbol de tareas una sola vez, acumulando el trabajo de las tareas hoja hasta sus tareas resumen. Este enfoque es mucho más eficiente que iterar sobre cada tarea individualmente, especialmente en proyectos grandes con jerarquías profundas. Además, garantiza que los valores de trabajo resumido permanezcan sincronizados con sus sub‑tareas.

## Requisitos previos

1. **Visual Studio** – cualquier edición reciente (2019, 2022 o posterior).  
2. **Aspose.Tasks for .NET** – descárguelo desde [aquí](https://releases.aspose.com/tasks/net/).  
3. **Conocimientos básicos de C#** – debe sentirse cómodo con clases, objetos y LINQ simple.

## Importar espacios de nombres

En su proyecto C#, importe los espacios de nombres necesarios para trabajar con las funcionalidades de Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Ahora, desglosaremos cada ejemplo en varios pasos:

## Paso 1: Cargar archivo de proyecto

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Cargue el archivo de proyecto en memoria usando la clase `Project`.

## Paso 2: Definir jerarquía de tareas

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Defina la jerarquía de tareas agregando tareas padre e hijo.

## Paso 3: Establecer propiedades de la tarea (incluyendo **calcular duración de la tarea**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Aquí **calculamos la duración de la tarea** convirtiendo las horas de trabajo en un objeto `Duration` y luego derivamos la fecha de finalización.

## Paso 4: Agregar recurso (**asignar recursos a tareas**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Este fragmento **agrega un recurso al proyecto** y **asigna recursos a tareas** para que el planificador sepa quién es responsable del trabajo.

## Paso 5: Aplicar algoritmo de árbol

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Inicialice la clase `WorkAccumulator` y aplique el algoritmo de árbol para recopilar el trabajo común a lo largo de la jerarquía.

## Paso 6: Actualizar trabajo de la tarea

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Actualice los valores de trabajo de las tareas basándose en la información recopilada.

## Problemas comunes y consejos

- **Configuración de calendario faltante:** Si la fecha de finalización parece incorrecta, asegúrese de que el calendario del proyecto esté configurado correctamente antes de llamar a `GetFinishDateByStartAndWork`.  
- **Tipo de recurso no coincide:** Siempre establezca `Rsc.Type` a `ResourceType.Work` para recursos basados en esfuerzo; de lo contrario, la acumulación de trabajo puede devolver cero.  
- **Consejo profesional:** Después de actualizar el trabajo, llame a `project.Save("UpdatedProject.mpp")` para guardar los cambios.

## Conclusión

Al seguir estos pasos ahora sabe cómo **agregar un recurso al proyecto**, **calcular la duración de la tarea** y **asignar recursos a tareas** usando el algoritmo de árbol de Aspose.Tasks. Este método simplifica la gestión de la jerarquía y mantiene los valores de trabajo resumido precisos con un código mínimo.

## Preguntas frecuentes

### Q1: ¿Qué es Aspose.Tasks para .NET?

Aspose.Tasks para .NET es una API potente que permite a los desarrolladores manipular archivos de Microsoft Project programáticamente usando C#.

### Q2: ¿Puedo descargar una prueba gratuita de Aspose.Tasks para .NET?

Sí, puede descargar una prueba gratuita de Aspose.Tasks para .NET desde [aquí](https://releases.aspose.com/).

### Q3: ¿Dónde puedo encontrar la documentación de Aspose.Tasks para .NET?

Puede encontrar la documentación de Aspose.Tasks para .NET [aquí](https://reference.aspose.com/tasks/net/).

### Q4: ¿Cómo puedo obtener soporte para Aspose.Tasks para .NET?

Para soporte relacionado con Aspose.Tasks para .NET, puede visitar el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: ¿Hay una licencia temporal disponible para propósitos de prueba?

Sí, puede obtener una licencia temporal para propósitos de prueba desde [aquí](https://purchase.aspose.com/temporary-license/).

## Preguntas frecuentes

**Q: ¿Puedo usar este enfoque con un archivo de proyecto grande existente?**  
A: Absolutamente. El algoritmo de árbol funciona con cualquier instancia de `Project`, sin importar el tamaño.

**Q: ¿El algoritmo también actualiza los valores de costo?**  
A: El ejemplo se centra en el trabajo, pero puede ampliarlo para incluir costos acumulando `Tsk.Cost` de forma similar.

**Q: ¿Qué versiones de .NET son compatibles?**  
A: Aspose.Tasks es compatible con .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ y .NET 6+.

**Q: ¿Cómo manejo varios recursos por tarea?**  
A: Agregue cada recurso con `project.ResourceAssignments.Add(task, resource)`; el acumulador sumará su trabajo automáticamente.

---

**Última actualización:** 2026-03-19  
**Probado con:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}