---
title: Manejo de patrones de recurrencia mensual en Aspose.Tasks
linktitle: Manejo de patrones de recurrencia mensual en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a manejar patrones de recurrencia mensual en Aspose.Tasks para .NET con este tutorial paso a paso.
weight: 18
url: /es/net/advanced-concepts/monthly-recurrence-patterns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manejo de patrones de recurrencia mensual en Aspose.Tasks

## Introducción

Aspose.Tasks para .NET es una potente API que permite a los desarrolladores manipular archivos de Microsoft Project mediante programación. Una de las funcionalidades esenciales que ofrece es la capacidad de manejar tareas recurrentes de manera eficiente. En este tutorial, profundizaremos en cómo trabajar con patrones de recurrencia mensual usando Aspose.Tasks, paso a paso.

## Requisitos previos

Antes de comenzar, asegúrese de tener instalados los siguientes requisitos previos:

## Importar espacios de nombres

Primero, asegúrese de haber importado los espacios de nombres necesarios en su proyecto .NET:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Ahora, dividamos el proceso de manejo de patrones de recurrencia mensual en varios pasos:

## Paso 1: inicializar el proyecto

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Paso 2: establecer parámetros de tareas recurrentes

Defina los parámetros para la tarea recurrente, incluido el nombre de la tarea, la duración y el patrón de recurrencia:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

## Paso 3: agregar parámetros al proyecto

```csharp
project.RootTask.Children.Add(parameters);
```

## Paso 4: guarde el proyecto

Guarde el proyecto modificado con la tarea recurrente:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Conclusión

Manejar patrones de recurrencia mensual en Aspose.Tasks para .NET es sencillo y eficiente. Si sigue los pasos descritos en este tutorial, puede crear fácilmente tareas recurrentes con intervalos mensuales y rangos de recurrencia específicos.

## Preguntas frecuentes

### P1: ¿Aspose.Tasks es compatible con todas las versiones de archivos de Microsoft Project?

R1: Aspose.Tasks admite varias versiones de archivos de Microsoft Project, incluidos MPP, MPT, XML y MPX.

### P2: ¿Puedo personalizar aún más el patrón de recurrencia?

R2: Sí, Aspose.Tasks ofrece amplias opciones para personalizar patrones de recurrencia, incluidos diarios, semanales, mensuales y anuales.

### P3: ¿Hay una prueba gratuita disponible para Aspose.Tasks?

 R3: Sí, puede obtener una prueba gratuita de Aspose.Tasks desde el sitio web[aquí](https://releases.aspose.com/).

### P4: ¿Cómo puedo obtener soporte para Aspose.Tasks?

 R4: Puede buscar ayuda y participar en debates sobre el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P5: ¿Dónde puedo comprar una licencia para Aspose.Tasks?

 R5: Puede comprar una licencia para Aspose.Tasks desde el sitio web[aquí](https://purchase.aspose.com/buy)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
