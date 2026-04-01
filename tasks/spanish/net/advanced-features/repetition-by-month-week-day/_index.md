---
date: 2026-04-01
description: Aprende cómo establecer la recurrencia en Aspose.Tasks para .NET, agregar
  tareas recurrentes y automatizar tareas recurrentes por mes, semana y día.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Repetición por mes, semana y día en Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cómo establecer la recurrencia en Aspose.Tasks (mes, semana, día)
url: /es/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer recurrencia en Aspose.Tasks (mes, semana, día)

## Introducción

Si necesita **cómo establecer recurrencia** para tareas en un proyecto, Aspose.Tasks para .NET le brinda una forma limpia y programática de agregar definiciones de tareas recurrentes que se ejecutan por mes, semana o día. En este tutorial recorreremos un ejemplo del mundo real que le muestra cómo **agregar tarea recurrente**, **automatizar tareas recurrentes**, y gestionarlas directamente desde código C#. Al final, estará listo para integrar esta capacidad en cualquier solución de programación o gestión de proyectos.

## Respuestas rápidas
- **¿Qué significa “recurrence” en Aspose.Tasks?** Define un patrón (diario, semanal, mensual) que crea automáticamente instancias de tareas a lo largo de un rango de fechas.  
- **¿Qué método principal crea la recurrencia?** `RecurringTaskParameters` combinado con un `RecurrencePattern` específico.  
- **¿Necesito una licencia para ejecutar este código?** Una versión de prueba funciona para evaluación; se requiere una licencia comercial para producción.  
- **¿Puedo programar tareas semanales en lugar de mensuales?** Sí – reemplace `MonthlyRecurrencePattern` con `WeeklyRecurrencePattern`.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 y posteriores.

## Qué es la recurrencia en Aspose.Tasks?

La recurrencia es un conjunto de reglas que indica a Aspose.Tasks generar instancias de tareas a intervalos regulares—diarios, semanales o mensuales—sin duplicarlas manualmente. Esta característica es esencial para proyectos que contienen actividades rutinarias como reuniones de estado, inspecciones o trabajos de mantenimiento.

## Por qué usar las funciones de recurrencia?

- **Ahorre tiempo:** No es necesario copiar‑pegar tareas manualmente.  
- **Reduzca errores:** La biblioteca garantiza fechas y duraciones consistentes.  
- **Flexibilidad:** Combine patrones (p. ej., “primer domingo de cada 2 meses”).  
- **Automatización:** Perfecto para generar horarios en pipelines CI o herramientas de informes.

## Requisitos previos

1. **Comprensión básica de C#** – escribirá algunas líneas de código C#.  
2. **Aspose.Tasks para .NET instalado** – descárguelo de la [download page](https://releases.aspose.com/tasks/net/).  
3. **Un archivo de proyecto .mpp** – usaremos `Project1.mpp` como archivo fuente.

## Importar espacios de nombres

Para comenzar, importe los espacios de nombres de Aspose.Tasks requeridos:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Paso 1: Cargar el archivo de proyecto

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Creamos una instancia de `Project` que apunta a un archivo Microsoft Project existente.

### Paso 2: Definir parámetros de tarea recurrente

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Aquí **creamos parámetros de tarea recurrente**:

- **TaskName** – el nombre de la tarea generada.  
- **Duration** – la duración de cada ocurrencia.  
- **RecurrencePattern** – un patrón mensual que se repite cada 2 meses en el primer domingo.  
- **RecurrenceRange** – las fechas de inicio y fin que delimitan el cronograma.

### Paso 3: Agregar la tarea recurrente al proyecto

```csharp
project.RootTask.Children.Add(parameters);
```

Esta línea **agrega la tarea recurrente** a la raíz de la jerarquía del proyecto.

### Paso 4: Guardar el proyecto actualizado

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

El proyecto se guarda como un nuevo archivo `.mpp` que ahora contiene el cronograma automatizado.

## Problemas comunes y soluciones

| Problema | Razón | Solución |
|----------|-------|----------|
| **Tarea no aparece** | El rango de recurrencia está fuera de las fechas del proyecto. | Verifique que los valores `Start` y `Finish` estén dentro del calendario del proyecto. |
| **Día de la semana incorrecto** | Desajuste del enum `WeekDay`. | Utilice `DayOfWeek.Monday` … `DayOfWeek.Sunday` según sea necesario. |
| **Excepción de licencia** | Ejecutando sin una licencia válida en producción. | Aplique una licencia temporal o completa antes de guardar. |

## Preguntas frecuentes

### Q1: ¿Puedo personalizar el patrón de recurrencia más allá de los ejemplos proporcionados?

A1: Sí, Aspose.Tasks para .NET ofrece amplias opciones de personalización para los patrones de recurrencia, permitiéndole adaptarlos a sus requisitos específicos.

### Q2: ¿Hay una versión de prueba disponible para Aspose.Tasks para .NET?

A2: Sí, puede obtener una prueba gratuita de Aspose.Tasks para .NET desde la [releases page](https://releases.aspose.com/).

### Q3: ¿Cómo puedo obtener soporte para Aspose.Tasks para .NET?

A3: Puede buscar asistencia y participar con la comunidad en el [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q4: ¿Están disponibles licencias temporales para Aspose.Tasks para .NET?

A4: Sí, puede adquirir licencias temporales desde la [purchase page](https://purchase.aspose.com/temporary-license/) para propósitos de prueba y evaluación.

### Q5: ¿Dónde puedo encontrar documentación completa para Aspose.Tasks para .NET?

A5: Puede consultar la [documentation](https://reference.aspose.com/tasks/net/) detallada disponible en el sitio web de Aspose para obtener una guía profunda sobre el uso de la biblioteca.

---

**Última actualización:** 2026-04-01  
**Probado con:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}