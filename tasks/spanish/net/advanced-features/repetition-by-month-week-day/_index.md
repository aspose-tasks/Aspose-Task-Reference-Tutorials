---
title: Repetición por mes semana día en Aspose.Tasks
linktitle: Repetición por mes semana día en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a configurar repeticiones por mes, semana y día en Aspose.Tasks para .NET para automatizar tareas recurrentes de manera eficiente.
weight: 26
url: /es/net/advanced-features/repetition-by-month-week-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Repetición por mes semana día en Aspose.Tasks

## Introducción

En el ámbito del desarrollo de software, particularmente en aplicaciones de gestión de proyectos, la capacidad de manejar tareas recurrentes de manera eficiente es primordial. Aspose.Tasks para .NET es una potente biblioteca diseñada para agilizar la creación y gestión de tareas de proyectos, incluidas las recurrentes. Una de esas funciones proporcionadas por Aspose.Tasks es la capacidad de configurar repeticiones por mes, semana y día, asegurando que las tareas se ejecuten según lo programado sin intervención manual.

## Requisitos previos

Antes de profundizar en las complejidades de configurar repeticiones por mes, semana y día usando Aspose.Tasks para .NET, asegúrese de cumplir con los siguientes requisitos previos:

1. Comprensión básica de C#: la familiaridad con el lenguaje de programación C# es esencial para comprender e implementar los ejemplos de código proporcionados.
   
2.  Instalación de Aspose.Tasks para .NET: asegúrese de haber descargado e instalado la biblioteca Aspose.Tasks para .NET. Puede obtener la biblioteca en el[pagina de descarga](https://releases.aspose.com/tasks/net/).

3. Acceso a un archivo de proyecto .mpp: tenga listo un archivo de Microsoft Project (.mpp), ya que lo utilizaremos para demostrar la implementación de repeticiones por mes, semana y día.

## Importar espacios de nombres

Para comenzar a utilizar Aspose.Tasks para .NET en su aplicación C#, debe importar los espacios de nombres necesarios. Así es como puedes hacerlo:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Dividamos el fragmento de código proporcionado en varios pasos para comprender cada parte a fondo.

## Paso 1: cargar el archivo del proyecto

```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Este paso implica crear una nueva instancia del`Project` clase y cargando un archivo de Microsoft Project existente (`Project1.mpp`) del directorio especificado.

## Paso 2: definir parámetros de tareas recurrentes

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

En este paso, definimos los parámetros para una tarea recurrente. Especificamos el nombre de la tarea, la duración, el patrón de repetición (mensual) y el rango de recurrencia (finaliza en una fecha específica).

## Paso 3: agregar una tarea recurrente al proyecto

```csharp
project.RootTask.Children.Add(parameters);
```

Aquí, agregamos los parámetros de tarea recurrente definidos a la tarea raíz del proyecto.

## Paso 4: guardar el archivo del proyecto

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Finalmente, guardamos el archivo del proyecto modificado con la tarea recurrente agregada.

## Conclusión

En conclusión, configurar repeticiones por mes, semana y día en Aspose.Tasks para .NET es un proceso sencillo que permite a los desarrolladores automatizar la gestión de tareas recurrentes dentro de sus proyectos de manera eficiente. Si sigue los pasos descritos en este tutorial, podrá integrar perfectamente esta funcionalidad en sus aplicaciones C#, ahorrando tiempo y esfuerzo en la gestión de proyectos.

## Preguntas frecuentes

###P1: ¿Puedo personalizar el patrón de recurrencia más allá de los ejemplos proporcionados?

R1: Sí, Aspose.Tasks para .NET ofrece amplias opciones de personalización para patrones de recurrencia, lo que le permite adaptarlos a sus requisitos específicos.

###P2: ¿Existe una versión de prueba disponible para Aspose.Tasks para .NET?

 R2: Sí, puede obtener una prueba gratuita de Aspose.Tasks para .NET desde el[página de lanzamientos](https://releases.aspose.com/).

###P3: ¿Cómo puedo obtener soporte para Aspose.Tasks para .NET?

 R3: Puede buscar ayuda e interactuar con la comunidad en el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

###P4: ¿Hay licencias temporales disponibles para Aspose.Tasks para .NET?

 R4: Sí, puede adquirir licencias temporales del[pagina de compra](https://purchase.aspose.com/temporary-license/) para fines de prueba y evaluación.

###P5: ¿Dónde puedo encontrar documentación completa sobre Aspose.Tasks para .NET?

 A5: Puede consultar el detalle[documentación](https://reference.aspose.com/tasks/net/) disponible en el sitio web de Aspose para obtener orientación detallada sobre el uso de la biblioteca.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
