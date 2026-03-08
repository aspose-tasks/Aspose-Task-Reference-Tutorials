---
date: 2026-03-08
description: Aprenda cómo crear una tarea recurrente mensual en Aspose.Tasks para
  .NET con este tutorial paso a paso.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cómo crear una tarea recurrente mensual en Aspose.Tasks
url: /es/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear tarea recurrente mensual usando Aspose.Tasks

## Introducción

Aspose.Tasks para .NET le permite manipular programáticamente archivos de Microsoft Project, y una de las necesidades reales más comunes es **crear programaciones de tareas recurrentes mensuales**. Ya sea que esté construyendo una herramienta de seguimiento de proyectos, automatizando la asignación de recursos, o generando ítems de trabajo de mantenimiento recurrentes, este tutorial le guía paso a paso para agregar un patrón de recurrencia mensual a una tarea.

En las siguientes secciones verá cómo configurar el proyecto, definir los parámetros de recurrencia y, finalmente, guardar el archivo actualizado, todo con explicaciones claras y consejos prácticos.

## Respuestas rápidas
- **¿Qué significa “tarea recurrente mensual”?** Una tarea que se repite en un patrón de día o semana definido cada mes.  
- **¿Qué clase de la API maneja la recurrencia?** `RecurringTaskParameters` junto con `MonthlyRecurrencePattern`.  
- **¿Necesito una licencia para ejecutar el ejemplo?** Una prueba gratuita sirve para evaluación; se requiere una licencia para producción.  
- **¿Puedo cambiar el intervalo?** Sí – establezca `RepetitionInterval` al número de meses entre ocurrencias.  
- **¿Qué formatos de archivo son compatibles?** Tanto archivos de proyecto `.mpp` como `.xml` pueden cargarse y guardarse.

## ¿Qué es un patrón de recurrencia mensual?

Un patrón de recurrencia mensual indica a Microsoft Project (y a Aspose.Tasks) con qué frecuencia debe repetirse una tarea cada mes. Puede especificar un día fijo del mes (p. ej., el 1.º) o una posición relativa (p. ej., el último viernes). La API traduce estas reglas a la estructura subyacente del archivo de Project.

## ¿Por qué usar Aspose.Tasks para esto?

- **Control total** – Sin limitaciones de UI; usted define cada aspecto del patrón en código.  
- **Multiplataforma** – Funciona en .NET Framework, .NET Core y .NET 5/6+.  
- **No se requiere Microsoft Project** – Genere o modifique archivos en un servidor o pipeline CI.  

## Requisitos previos

Antes de comenzar, asegúrese de tener:

- .NET 6 (o .NET 5/Framework 4.7+) instalado.  
- Paquete NuGet Aspose.Tasks para .NET añadido a su proyecto.  
- Un archivo de proyecto de ejemplo (`Project1.mpp`) colocado en una carpeta conocida (`DataDir`).  

## Importar espacios de nombres

Primero, importe los espacios de nombres requeridos para trabajar con tareas y guardar proyectos:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Paso 1: Inicializar el proyecto

Cree una instancia de `Project` que apunte a su archivo `.mpp` existente. Esto carga el archivo en memoria para que pueda modificarlo.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Consejo profesional:** Si el archivo no existe, Aspose.Tasks creará automáticamente un nuevo proyecto en blanco.

## Paso 2: Definir los parámetros de la tarea recurrente

Defina los detalles de la tarea recurrente, incluido su nombre, duración y el patrón mensual que desea aplicar.

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

- `DayPosition = 1` significa que la tarea ocurre en el **primer día** del mes.  
- `RepetitionInterval = 2` hace que la tarea se repita **cada dos meses**.  
- `Start` y `Finish` definen la ventana general durante la cual la recurrencia está activa.

## Paso 3: Añadir los parámetros al proyecto

Adjunte el objeto `RecurringTaskParameters` a la colección de hijos de la tarea raíz. Esto crea efectivamente la tarea recurrente en la jerarquía del proyecto.

```csharp
project.RootTask.Children.Add(parameters);
```

## Paso 4: Guardar el proyecto

Persista los cambios guardando el proyecto en un nuevo archivo. Puede elegir cualquier formato compatible; aquí usamos el formato nativo `.mpp`.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Después de ejecutar el código, abra el archivo resultante en Microsoft Project para ver la tarea recurrente mensual que acaba de crear.

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| La tarea no aparece después de guardar | El proyecto no se actualiza en la UI | Vuelva a abrir el archivo o llame a `project.UpdateTaskLinks()` antes de guardar. |
| Fecha de inicio incorrecta | `Start` establecido en un fin de semana | Utilice `DateTime` que caiga en un día laborable o ajuste el calendario. |
| Intervalo de recurrencia ignorado | Usando `ByMonthDayRepetition` con `DayPosition` = 0 | Asegúrese de que `DayPosition` esté entre 1‑31. |

## Conclusión

Al seguir estos pasos ahora sabe cómo **crear programaciones de tareas recurrentes mensuales** con Aspose.Tasks para .NET. La API le brinda un control granular sobre los intervalos de recurrencia, los rangos de inicio/fin y el patrón de día específico, lo que le permite automatizar escenarios complejos de planificación de proyectos.

## Preguntas frecuentes

### Q1: ¿Aspose.Tasks es compatible con todas las versiones de archivos de Microsoft Project?

A1: Aspose.Tasks admite diversas versiones de archivos de Microsoft Project, incluidos MPP, MPT, XML y MPX.

### Q2: ¿Puedo personalizar aún más el patrón de recurrencia?

A2: Sí, Aspose.Tasks ofrece opciones extensas para personalizar patrones de recurrencia, incluidos diarios, semanales, mensuales y anuales.

### Q3: ¿Hay una prueba gratuita disponible para Aspose.Tasks?

A3: Sí, puede obtener una prueba gratuita de Aspose.Tasks en el sitio web [here](https://releases.aspose.com/).

### Q4: ¿Cómo puedo obtener soporte para Aspose.Tasks?

A4: Puede buscar asistencia y participar en discusiones en el [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: ¿Dónde puedo comprar una licencia para Aspose.Tasks?

A5: Puede comprar una licencia para Aspose.Tasks en el sitio web [here](https://purchase.aspose.com/buy)

## Preguntas frecuentes (FAQ)

**P: ¿Puedo usar este código en una aplicación .NET Core?**  
R: Absolutamente. Aspose.Tasks para .NET soporta completamente .NET Core 3.1 y versiones posteriores.

**P: ¿Cómo cambio la recurrencia a “último día laborable del mes”?**  
R: Use `ByMonthDayRepetition` con `DayPosition = -1` (los valores negativos cuentan desde el final del mes) y establezca `WeekDay` según corresponda.

**P: ¿Qué ocurre si el rango de recurrencia supera el calendario del proyecto?**  
R: La API respeta el calendario del proyecto; las ocurrencias que caen en días no laborables se omiten o se trasladan según la configuración del calendario.

**P: ¿Es posible eliminar una ocurrencia específica de una tarea recurrente?**  
R: Sí. Después de añadir la tarea recurrente, puede obtener ocurrencias individuales mediante `Task.GetOccurrences()` y eliminar las que no necesite.

**P: ¿Aspose.Tasks maneja automáticamente las diferencias de zona horaria?**  
R: La biblioteca almacena las fechas en UTC; puede convertirlas a hora local usando los métodos estándar de .NET `DateTime` si es necesario.

---

**Última actualización:** 2026-03-08  
**Probado con:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}