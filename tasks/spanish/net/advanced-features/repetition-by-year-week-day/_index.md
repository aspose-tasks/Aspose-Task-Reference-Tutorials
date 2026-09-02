---
date: 2026-04-03
description: Aprenda a usar Aspose.Tasks para agregar tareas recurrentes al proyecto
  y guardar el proyecto como MPP. Esta guía muestra la función Repetición por Año
  Semana Día paso a paso.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Repetición por año, semana y día en Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cómo usar Aspose.Tasks – Repetición por año, semana y día
url: /es/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Repetición por Año Semana Día en Aspose.Tasks

## Introducción

Cuando necesitas **how to use Aspose.Tasks** para manejar horarios recurrentes complejos, la biblioteca te brinda un control fino sobre los patrones anuales. En este tutorial recorreremos la creación de una tarea que se repite en un día de la semana específico de un mes determinado, abarcando varios años. Al final podrás **add recurring task project** entradas y **save project as MPP** con solo unas pocas líneas de C#.

## Respuestas rápidas
- **What does “Repetition by Year Week Day” mean?** Repite una tarea en un día de la semana elegido (p.ej., primer domingo) de un mes dado cada año.  
- **Which .NET versions are supported?** Todas las versiones modernas de .NET Framework y .NET Core/5/6.  
- **Do I need a license to run the code?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **Can I change the recurrence range?** Sí – puedes establecer una fecha de inicio, fecha de fin, o un número fijo de ocurrencias.  
- **Is the output an MPP file?** Absolutamente – el proyecto se guarda como un archivo MPP listo para Microsoft Project.

## Qué es la función “Repetition by Year Week Day”

La función le permite definir una recurrencia anual que apunta a un **day of the week** particular (p.ej., Sunday) y una **position** dentro del mes (primero, segundo, último, etc.). Esto es ideal para tareas como revisiones trimestrales, auditorías anuales, o cualquier evento que siga un ritmo basado en el calendario.

## Por qué usar Aspose.Tasks para tareas recurrentes

- **Precision** – Control total sobre meses, días de la semana y posiciones ordinales.  
- **Compatibility** – Genera archivos MPP nativos que se abren sin problemas en Microsoft Project.  
- **No COM interop** – API .NET pura, sin necesidad de instalaciones de Office.  
- **Scalability** – Funciona tanto para proyectos pequeños como para horarios a nivel empresarial.

## Requisitos previos

Antes de sumergirse en el código, asegúrese de tener:

1. **Basic .NET knowledge** – Familiaridad con C# y conceptos orientados a objetos.  
2. **Aspose.Tasks for .NET** – Descárguelo desde el [download link](https://releases.aspose.com/tasks/net/) y agregue el DLL a su proyecto.  
3. **Access to the official docs** – La [documentation](https://reference.aspose.com/tasks/net/) contiene detalles exhaustivos sobre todas las clases.  
4. **A development IDE** – Visual Studio, Rider, o cualquier editor compatible con .NET.  

Ahora que está listo, veamos la implementación.

## Cómo usar Aspose.Tasks para tareas recurrentes

### Importando los espacios de nombres necesarios

Primero, importe los espacios de nombres requeridos al alcance para que pueda trabajar con proyectos, tareas y opciones de guardado.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Paso 1: Inicializar el proyecto y los parámetros de la tarea

Cree una nueva instancia de `Project`, luego defina un objeto `RecurringTaskParameters` que describa el patrón de recurrencia.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** Ajuste `Month`, `WeekDay` y `Position` para que coincidan con su horario real.

### Paso 2: Añadir parámetros al proyecto

Inserte la definición de tarea recurrente en la raíz del proyecto.

```csharp
project.RootTask.Children.Add(parameters);
```

### Paso 3: Guardar el proyecto como MPP

Finalmente, persista el proyecto en un archivo MPP para que pueda abrirse en Microsoft Project o cualquier visor compatible.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> Esto demuestra **save project as mpp** en una sola línea de código.

## Problemas comunes y soluciones

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| No aparecen tareas después de abrir el archivo MPP | Las fechas del rango de recurrencia están fuera del calendario del proyecto | Verifique que las fechas `Start` y `Finish` estén dentro del horario laboral del proyecto |
| Excepción `ArgumentNullException` en `Add` | `parameters` es nulo o no está completamente inicializado | Asegúrese de que todas las propiedades requeridas (TaskName, Duration, RecurrencePattern) estén establecidas |
| Día de la semana seleccionado incorrecto | Desajuste del valor del enum `WeekDay` | Utilice `DayOfWeek.Monday` … `DayOfWeek.Sunday` según sea necesario |

## Preguntas frecuentes

**Q: ¿Puedo personalizar el patrón de recurrencia más allá del ejemplo proporcionado?**  
A: Sí, Aspose.Tasks le permite combinar `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern`, o incluso objetos `RecurrenceRange` personalizados para adaptarse a cualquier calendario.

**Q: ¿Es Aspose.Tasks para .NET compatible con otro software de gestión de proyectos?**  
A: Absolutamente – la biblioteca lee y escribe formatos MPP, XML y Primavera, lo que permite un intercambio de datos fluido.

**Q: ¿Cómo puedo manejar excepciones o modificaciones en tareas recurrentes?**  
A: Utilice la clase `ExceptionTask` para crear sobrescrituras para ocurrencias específicas, o edite los `RecurringTaskParameters` y vuelva a guardar el proyecto.

**Q: ¿Aspose.Tasks admite soluciones basadas en la nube?**  
A: Sí, puede ejecutar la API en Azure Functions, AWS Lambda, o cualquier servicio en la nube compatible con .NET.

**Q: ¿Hay una versión de prueba disponible para Aspose.Tasks para .NET?**  
A: Sí, puede acceder a una prueba gratuita de Aspose.Tasks para .NET desde el [website](https://releases.aspose.com/), lo que le permite explorar sus funciones antes de tomar una decisión de compra.

**Q: ¿Cómo añado una tarea recurrente a un proyecto existente sin sobrescribir otros datos?**  
A: Cargue el proyecto existente con `new Project("Existing.mpp")`, añada los `RecurringTaskParameters` a `RootTask.Children`, y luego `Save` el archivo.

## Conclusión

Al dominar **how to use Aspose.Tasks** para el escenario **Repetition by Year Week Day**, adquiere la capacidad de **add recurring task project** entradas que se alinean perfectamente con calendarios del mundo real y **save project as MPP** para una colaboración sin problemas. Incorpore estos fragmentos en sus propias soluciones para mejorar la precisión de la programación y reducir el esfuerzo manual.

---

**Última actualización:** 2026-04-03  
**Probado con:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}