---
date: 2026-03-24
description: Aprenda cómo establecer el modo de cálculo en Aspose.Tasks para .NET,
  cubriendo el modo de cálculo automático, manual y sin cálculo para gestionar las
  dependencias de tareas.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Cómo establecer el modo de cálculo en Aspose.Tasks para .NET
url: /es/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer el modo de cálculo en Aspose.Tasks para .NET

## Introducción

Aspose.Tasks para .NET es una API potente que le permite trabajar con archivos de Microsoft Project de forma programática. Uno de los ajustes más importantes que encontrará es el **modo de cálculo**, que controla cómo se actualizan las fechas de las tareas y los cronogramas del proyecto. En este tutorial aprenderá **cómo establecer el modo de cálculo**, explorará el **modo de cálculo automático**, el **modo de cálculo manual** y el **modo de cálculo none**, y verá cómo estas opciones afectan a **gestionar dependencias de tareas**, **crear la fecha de inicio del proyecto** y **vincular relaciones de fin‑inicio** entre tareas.

## Respuestas rápidas
- **¿Qué es el modo de cálculo?** Determina si las fechas de las tareas se recalculan automáticamente, manualmente o no se recalculan.  
- **¿Por qué usar el modo de cálculo manual?** Para obtener control total sobre cuándo se actualiza el cronograma, útil en actualizaciones masivas.  
- **¿Cuál es el modo predeterminado?** El modo de cálculo automático, que actualiza las fechas instantáneamente después de los cambios.  
- **¿Puedo cambiar el modo en tiempo de ejecución?** Sí, simplemente establezca la propiedad `CalculationMode` en el objeto `Project`.  
- **¿Necesito una licencia?** Se requiere una licencia válida de Aspose.Tasks para uso en producción.

## Qué significa “cómo establecer el cálculo” en Aspose.Tasks?

Establecer el modo de cálculo es tan simple como asignar un valor de enumeración a la propiedad `Project.CalculationMode`. La enumeración ofrece tres opciones: `Automatic`, `Manual` y `None`. Elegir el modo adecuado depende de su flujo de trabajo—si desea actualizaciones instantáneas, procesamiento por lotes o control total.

## Requisitos previos

Antes de comenzar, asegúrese de contar con:

1. **Visual Studio** – cualquier versión reciente (2019, 2022 o posterior).  
2. **Aspose.Tasks para .NET** – descargue e instale la biblioteca desde [aquí](https://releases.aspose.com/tasks/net/).  
3. **Conocimientos básicos de C#** – debe sentirse cómodo creando aplicaciones de consola y usando paquetes NuGet.

## Importar espacios de nombres

Antes de comenzar a trabajar con Aspose.Tasks para .NET, importemos los espacios de nombres necesarios:

```csharp
using Aspose.Tasks;
using System;
```

## Cómo establecer el modo de cálculo

A continuación encontrará ejemplos paso a paso para cada modo de cálculo. Los bloques de código permanecen sin cambios respecto al tutorial original; las explicaciones circundantes se han ampliado para mayor claridad.

### Aplicar el modo de cálculo automático

El modo automático recalcula las fechas al instante siempre que modifique tareas o enlaces.

#### Paso 1: Crear una nueva instancia de Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Paso 2: Establecer la fecha de inicio del proyecto y agregar tareas

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Paso 3: Vincular tareas (fin‑a‑inicio)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Paso 4: Verificar las fechas recalculadas

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Aplicar el modo de cálculo manual

El modo manual desactiva las actualizaciones automáticas, dándole la oportunidad de procesar cambios por lotes antes de forzar una recalculación.

#### Paso 1: Crear una nueva instancia de Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Paso 2: Establecer la fecha de inicio del proyecto y agregar tareas

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Paso 3: Verificar las propiedades de la tarea

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Paso 4: Vincular tareas y verificar fechas (sin recalculación automática)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Aplicar el modo de cálculo None

El modo None desactiva todos los cálculos internos. Úselo cuando solo necesite leer o exportar datos sin realizar cambios en el cronograma.

#### Paso 1: Crear una nueva instancia de Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Paso 2: Agregar una nueva tarea

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Paso 3: Verificar las propiedades de la tarea (sin IDs automáticos)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Problemas comunes y soluciones

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| Las fechas no se actualizan después de vincular tareas | El proyecto está en modo **Manual** o **None** | Establezca `project.CalculationMode = CalculationMode.Automatic` o llame a `project.Calculate()` manualmente |
| Los IDs de tarea permanecen en 0 | Usar el modo **None** impide la generación de IDs | Cambie a modo **Automatic** o **Manual**, luego recalcule |
| El enlace falla con `ArgumentException` | La fecha de inicio del predecesor es posterior a la del sucesor al usar el modo **Manual** sin recalculación | Asegúrese de que las fechas de inicio sean correctas o recalcule después de agregar enlaces |

## Preguntas frecuentes

**Q1: ¿Puedo cambiar el modo de cálculo dinámicamente durante la ejecución?**  
A1: Sí, puede modificar la propiedad `CalculationMode` en cualquier punto de su código y luego llamar a `project.Calculate()` si necesita una actualización inmediata.

**Q2: ¿Aspose.Tasks admite otros formatos de archivo de gestión de proyectos además de Microsoft Project?**  
A2: Aspose.Tasks se centra principalmente en los formatos de Microsoft Project, pero también admite Primavera P6 XML, Primavera DB y Asta Powerproject XML.

**Q3: ¿Es Aspose.Tasks adecuado tanto para proyectos de pequeña escala como para proyectos a nivel empresarial?**  
A3: Absolutamente. La API escala desde listas de tareas simples hasta cronogramas empresariales complejos y multi‑fase.

**Q4: ¿Puedo integrar Aspose.Tasks con otras bibliotecas y frameworks de .NET?**  
A4: Sí, puede combinar Aspose.Tasks con ASP.NET, WPF, Xamarin o cualquier otra tecnología .NET para crear soluciones de gestión de proyectos avanzadas.

**Q5: ¿Existe un foro comunitario o canal de soporte disponible para usuarios de Aspose.Tasks?**  
A5: Sí, puede visitar el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener soporte comunitario y participar en discusiones.

---

**Última actualización:** 2026-03-24  
**Probado con:** Aspose.Tasks 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}