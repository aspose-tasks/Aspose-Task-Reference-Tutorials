---
date: 2026-04-09
description: Aprenda cómo establecer el calendario estándar y gestionar los días festivos
  del proyecto en sus proyectos .NET usando Aspose.Tasks para una programación precisa.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Establecer calendario estándar y manejar excepciones en Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Establecer calendario estándar y manejar excepciones en Aspose.Tasks
url: /es/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer calendario estándar y manejar excepciones en Aspose.Tasks

## Introducción

La programación precisa es la columna vertebral de cualquier proyecto exitoso, y los planes del mundo real a menudo deben desviarse del calendario de trabajo predeterminado debido a festivos, eventos especiales o interrupciones inesperadas. Aspose.Tasks para .NET facilita la configuración de **set standard calendar** y luego superponer excepciones personalizadas. En este tutorial aprenderá cómo cargar un calendario de proyecto, establecer un calendario estándar y gestionar los festivos del proyecto mediante la característica Calendar Exception Collection.

## Respuestas rápidas
- **¿Qué hace “set standard calendar”?** Restablece un calendario al horario de trabajo predeterminado (9 AM‑5 PM, lunes‑viernes) antes de agregar excepciones personalizadas.  
- **¿Qué método elimina las excepciones existentes?** `Calendar.Exceptions.Clear()` elimina todas las excepciones definidas previamente.  
- **¿Cómo puedo agregar un festivo?** Cree un `CalendarException` con `DayWorking = false` y agréguelo a la colección.  
- **¿Necesito recargar el proyecto después de los cambios?** No, los cambios se aplican directamente al objeto `Project` en memoria.  
- **¿Qué bibliotecas se requieren?** Aspose.Tasks for .NET (cualquier versión compatible de .NET) y los espacios de nombres `System`.

## Requisitos previos

Antes de sumergirse en el código, asegúrese de tener:

1. **Aspose.Tasks for .NET** – descárguelo [aquí](https://releases.aspose.com/tasks/net/).  
2. Conocimientos básicos de **C#** – escribirá algunos fragmentos breves.  
3. Un entorno de desarrollo como **Visual Studio** o **JetBrains Rider**.

## Importar espacios de nombres

Estas directivas `using` le dan acceso a las clases necesarias para la manipulación del calendario.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## ¿Qué es una excepción de calendario?

Una *excepción de calendario* representa un período en el que el horario de trabajo normal se altera – por ejemplo, un festivo a nivel de empresa o un horario temporal de horas extra. Al agregar excepciones a un calendario puede modelar restricciones del mundo real sin cambiar el calendario base.

## Cómo establecer un calendario estándar en Aspose.Tasks

El primer paso es cargar su archivo de proyecto y obtener el calendario con el que desea trabajar.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Paso 1: Eliminar excepciones existentes y restablecer a un calendario estándar

Antes de agregar nuevas reglas, es una buena práctica eliminar cualquier excepción anterior y los ajustes de **set standard calendar**. Esto garantiza una base limpia.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Paso 2: Definir una excepción de tiempo de trabajo

A veces necesita crear un horario temporal (p. ej., horas extendidas para el lanzamiento de un producto). El siguiente fragmento define una excepción de tiempo de trabajo que abarca varios días e incluye dos períodos de trabajo diarios.

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### Paso 3: Agregar excepciones de tiempo no laborable (festivos)

Para **manage project holidays**, cree excepciones donde `DayWorking` sea `false`. El ejemplo a continuación agrega un bloque de festivo de dos días.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Paso 4: Mostrar excepciones de calendario (verificación)

Después de agregar excepciones, a menudo querrá verificar que se hayan registrado correctamente. El siguiente bucle imprime los detalles de cada excepción en la consola.

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### Paso 5: Eliminar todas las excepciones (limpieza)

Si necesita revertir el calendario a su estado original, puede eliminar todas las excepciones programáticamente.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Problemas comunes y soluciones

| Problema | Razón | Solución |
|----------|-------|----------|
| Las excepciones no aparecen después de guardar | El proyecto no se guardó después de las modificaciones | Llame a `project.Save("output.mpp")` después de realizar los cambios. |
| Las excepciones superpuestas causan horas de trabajo inesperadas | Aspose.Tasks usa la última excepción añadida para períodos superpuestos | Ordene sus llamadas `Add` cuidadosamente o ajuste las prioridades manualmente. |
| `MakeStandardCalendar` restablece los tiempos de trabajo personalizados | Intencionalmente elimina los tiempos personalizados; vuelva a agregarlos después de la llamada si es necesario. | Agregue sus objetos `WorkingTime` personalizados después de invocar `MakeStandardCalendar`. |

## Preguntas frecuentes

**Q: ¿Puedo agregar múltiples excepciones a un solo calendario?**  
A: Sí, puede agregar múltiples excepciones a un calendario usando el método `AddRange`.

**Q: ¿Cómo manejo excepciones recurrentes, como festivos semanales?**  
A: Puede calcular programáticamente excepciones recurrentes y agregarlas al calendario usando lógica personalizada.

**Q: ¿Es posible importar excepciones de calendario desde fuentes externas?**  
A: Sí, puede leer excepciones de calendario de fuentes externas como bases de datos o archivos CSV e integrarlas en su proyecto.

**Q: ¿Qué ocurre si hay excepciones superpuestas en el calendario?**  
A: Aspose.Tasks for .NET le permite manejar excepciones superpuestas definiendo prioridades o resolviendo conflictos según los requisitos de su proyecto.

**Q: ¿Puedo personalizar los horarios de trabajo para cada día dentro de una excepción?**  
A: Sí, puede especificar horarios de trabajo personalizados para días individuales dentro de una excepción para adaptarse a necesidades de programación específicas.

## Conclusión

Al **setting a standard calendar** primero y luego superponer excepciones personalizadas, obtiene control total sobre la programación del proyecto, facilitando **manage project holidays** y cualquier otra línea de tiempo de casos especiales. La Calendar Exception Collection en Aspose.Tasks ofrece una forma limpia y programática de modelar calendarios del mundo real directamente dentro de sus aplicaciones .NET.

---

**Última actualización:** 2026-04-09  
**Probado con:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}