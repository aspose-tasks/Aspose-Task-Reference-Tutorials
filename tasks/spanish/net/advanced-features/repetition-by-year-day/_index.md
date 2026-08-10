---
date: 2026-04-03
description: Aprenda la programación de tareas de gestión de proyectos y cómo agregar
  tareas recurrentes usando Aspose.Tasks para .NET, incluyendo guardar el proyecto
  como MPP.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Repetición por día del año en Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Programación de tareas de gestión de proyectos con repetición anual en Aspose.Tasks
url: /es/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Programación de Tareas de Gestión de Proyectos con Repetición por Día del Año en Aspose.Tasks

## Introducción

La **programación de tareas de gestión de proyectos** es la columna vertebral de cualquier proyecto exitoso. Cuando las tareas se repiten anualmente —como auditorías anuales, ventanas de mantenimiento o revisiones estacionales— manejar esas recurrencias manualmente puede ser propenso a errores y consumir mucho tiempo. Aspose.Tasks para .NET simplifica esto al permitir definir patrones de día del año de forma programática, de modo que pueda centrarse en lo que más importa: entregar valor. En este tutorial aprenderá **cómo agregar lógica de tarea recurrente** basada en un día específico del año y verá exactamente **cómo guardar el proyecto como MPP** para una integración fluida con Microsoft Project.

## Respuestas rápidas
- **¿Qué significa “repetición por día del año”?** Programa una tarea en un día específico de un mes específico cada año.  
- **¿Qué clase de API crea la recurrencia?** `YearlyRecurrencePattern` combined with `ByYearDayRepetition`.  
- **¿Puedo establecer una fecha de inicio y fin?** Sí, usando `EndByRecurrenceRange`.  
- **¿Qué formato de archivo se produce?** El proyecto se guarda como un archivo MPP (`SaveFileFormat.Mpp`).  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial para uso que no sea de evaluación.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de que tiene los siguientes requisitos previos:

1. Bibliotheca Aspose.Tasks para .NET: Descargue e instale la biblioteca Aspose.Tasks para .NET desde el [sitio web](https://releases.aspose.com/tasks/net/).  
2. Entorno de desarrollo: Configure un entorno de desarrollo adecuado con Visual Studio o cualquier otro IDE preferido para el desarrollo en .NET.  
3. Conocimientos básicos de C#: Familiarícese con los fundamentos del lenguaje de programación C# para seguir los ejemplos de código.  
4. Conceptos de gestión de proyectos: Comprender los conceptos de gestión de proyectos y la programación de tareas ayudará a asimilar eficazmente los conceptos del tutorial.

## Importar espacios de nombres

Antes de comenzar a programar, importemos los espacios de nombres necesarios para facilitar la manipulación de tareas usando Aspose.Tasks para .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Ahora, desglosaremos el ejemplo proporcionado en varios pasos y explicaremos cada paso en detalle.

## Cómo agregar una tarea recurrente con patrón de día del año

### Paso 1: Cargar archivo de proyecto

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Aquí, inicializamos un nuevo objeto `Project` y cargamos un archivo de proyecto existente llamado **Project1.mpp**.

### Paso 2: Definir parámetros de tarea recurrente

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

En este paso, definimos los parámetros para nuestra tarea recurrente. Especificamos el nombre de la tarea, la duración y el patrón de recurrencia. Para una recurrencia anual, usamos `YearlyRecurrencePattern` y establecemos la repetición para que ocurra el **1.º día de julio** usando `ByYearDayRepetition`. Además, definimos el rango de recurrencia desde el 1 de julio de 2018 hasta el 1 de julio de 2019.

### Paso 3: Agregar tarea al proyecto

```csharp
project.RootTask.Children.Add(parameters);
```

Aquí, agregamos los parámetros de la tarea recurrente definidos a la tarea raíz del proyecto.

### Paso 4: Guardar proyecto como MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Finalmente, **guardamos el proyecto como un archivo MPP**, dejándolo listo para abrirse en Microsoft Project o cualquier visor compatible.

## Por qué es importante

- **Automatización** – Elimina la entrada manual de tareas anuales, reduciendo errores humanos.  
- **Consistencia** – Garantiza que el mismo patrón día‑mes se aplique a lo largo de varios años.  
- **Integración** – El archivo MPP resultante puede compartirse con las partes interesadas que dependen de Microsoft Project.  

## Errores comunes y consejos

- **Precisión de DateTime** – Asegúrese de que la hora de inicio se alinee con el calendario de su proyecto; de lo contrario, la tarea puede aparecer desplazada.  
- **Zonas horarias** – La API trabaja con objetos `DateTime`; considere la conversión a UTC si su aplicación abarca varias regiones.  
- **Aplicación de licencia** – En modo de evaluación, el MPP guardado puede contener una marca de agua; use una licencia válida para producción.

## Preguntas frecuentes

**Q: ¿Puede Aspose.Tasks manejar patrones de recurrencia complejos?**  
A: Sí, Aspose.Tasks ofrece soporte integral para varios patrones de recurrencia, incluidos los anuales, mensuales, semanales y diarios.

**Q: ¿Es Aspose.Tasks compatible con diferentes formatos de archivo de proyecto?**  
A: Absolutamente, Aspose.Tasks soporta formatos de archivo de proyecto populares como MPP, XML y CSV, garantizando compatibilidad con distintas herramientas de gestión de proyectos.

**Q: ¿Aspose.Tasks ofrece documentación y soporte para desarrolladores?**  
A: Sí, los desarrolladores pueden acceder a una documentación extensa y buscar asistencia en los foros de la comunidad de Aspose.Tasks para cualquier consulta o problema que encuentren.

**Q: ¿Puedo personalizar propiedades de la tarea como duración y fecha de inicio usando Aspose.Tasks?**  
A: Por supuesto, Aspose.Tasks ofrece APIs robustas para manipular dinámicamente las propiedades de las tareas, permitiendo a los desarrolladores personalizar duraciones, fechas de inicio, dependencias y más.

**Q: ¿Aspose.Tasks es adecuado tanto para proyectos de pequeña escala como para proyectos a nivel empresarial?**  
A: En efecto, Aspose.Tasks está diseñado para atender las necesidades de los desarrolladores que trabajan en proyectos de cualquier escala, desde tareas individuales hasta proyectos empresariales de gran envergadura.

---

**Última actualización:** 2026-04-03  
**Probado con:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}