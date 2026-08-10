---
date: 2026-04-13
description: Aprenda cómo eliminar una excepción de calendario en Aspose.Tasks para
  .NET y verifique la fecha de la excepción al gestionar la programación del calendario
  en ASP.NET.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Eliminar excepción de calendario con Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Eliminar excepción del calendario con Aspose.Tasks
url: /es/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Eliminar excepción de calendario con Aspose.Tasks

## Introducción

En este tutorial, aprenderás cómo **eliminar una excepción de calendario** y gestionar otras excepciones de calendario en Aspose.Tasks usando el framework .NET. Las excepciones de calendario te permiten modelar festivos, cierres temporales o cualquier período especial donde el horario de trabajo normal cambia. Entender cómo agregar, consultar y eliminar estas excepciones es esencial para una programación de proyectos precisa, especialmente al trabajar con escenarios de **programación de calendarios ASP.NET**.

## Respuestas rápidas
- **¿Cuál es el método principal para eliminar una excepción?** Usa el método `Delete()` en el objeto `CalendarException`.  
- **¿Qué clase verifica una fecha contra una excepción?** `CalendarException.CheckException()`—útil para **comprobar la fecha de excepción**.  
- **¿Necesito una licencia para ejecutar el código?** Sí, se requiere una licencia válida de Aspose.Tasks para uso en producción.  
- **¿Puedo agregar múltiples excepciones a un calendario?** Absolutamente; la colección `Exceptions` admite muchas entradas.  
- **¿Versiones .NET compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qué es una excepción de calendario?

Una **excepción de calendario** representa una desviación del calendario de trabajo regular—piénsalo como una regla que dice “en estas fechas, las horas de trabajo son diferentes o no hay trabajo”. En Aspose.Tasks, cada excepción puede tener sus propios horarios de trabajo, patrón de recurrencia y banderas que indican si el día es laborable.

## ¿Por qué gestionar excepciones de calendario en la programación de calendarios ASP.NET?

- **Cronogramas precisos:** Los proyectos respetan automáticamente festivos y cierres especiales, evitando plazos poco realistas.  
- **Flexibilidad:** Puedes definir patrones diarios, semanales, mensuales o anuales, adaptándolos a calendarios empresariales del mundo real.  
- **Automatización:** Comprobar programáticamente una fecha de excepción te permite crear lógica de programación dinámica en aplicaciones ASP.NET.

## Requisitos previos

- Conocimientos básicos de programación en C#.  
- Visual Studio (cualquier versión reciente).  
- Biblioteca Aspose.Tasks para .NET añadida a tu proyecto (via NuGet o referencia manual).  

## Importar espacios de nombres

Primero, importa los espacios de nombres que necesitarás:

```csharp
using Aspose.Tasks;
using System;
```

## Paso 1: Eliminar excepción de calendario

Eliminar una excepción no deseada es sencillo. El siguiente código carga un proyecto, selecciona el primer calendario, muestra información básica, elimina la primera excepción y luego muestra el recuento actualizado.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **Consejo profesional:** Siempre verifica que el índice de la excepción exista antes de llamar a `Delete()` para evitar `IndexOutOfRangeException`.

## Paso 2: Obtener tiempo de trabajo de una excepción de calendario

Si necesitas inspeccionar las horas de trabajo definidas para una excepción, usa `GetWorkingTime()`. Este ejemplo también muestra cómo **comprobar la fecha de excepción** con `CheckException`.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Paso 3: Definir excepciones de calendario

A continuación se muestra un recorrido completo que demuestra cómo **agregar**, **comprobar** y **eliminar** excepciones de calendario. Observa el uso de `CheckException` para **comprobar la fecha de excepción** en un momento específico.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Problemas comunes y consejos

| Problema | Razón | Solución |
|----------|-------|----------|
| **`IndexOutOfRangeException` al eliminar** | Intentar eliminar una excepción que no existe. | Verifica que `calendar.Exceptions.Count` > índice antes de llamar a `Delete()`. |
| **Tiempos de trabajo incorrectos** | No se establecen `DayWorking` o `WorkingTimes` correctamente. | Usa `exception.WorkingTimes.Add(new WorkingTime(...))` para definir períodos explícitos. |
| **Excepción no reconocida** | `CheckException` devuelve `false` porque la fecha está fuera del rango definido. | Revisa `FromDate`/`ToDate` y el `Type` (Daily, Weekly, etc.). |

## Preguntas frecuentes

**P: ¿Puedo agregar múltiples excepciones a un solo calendario?**  
R: Sí, puedes agregar tantas excepciones como necesites para representar festivos, ventanas de mantenimiento o cualquier regla de programación especial.

**P: ¿Cómo puedo **comprobar la fecha de excepción** para un día específico?**  
R: Usa el método `CheckException(DateTime date)` en una instancia de `CalendarException`. Devuelve `true` si la fecha suministrada cae dentro del rango de la excepción.

**P: ¿Es posible eliminar una excepción existente de un calendario?**  
R: Absolutamente. Accede a la colección `Exceptions` y llama a `Remove()` o invoca `Delete()` en el objeto `CalendarException` específico.

**P: ¿Qué tipos de excepciones de calendario son compatibles?**  
R: Aspose.Tasks admite tipos de excepción Diaria, Semanal, Mensual y Anual, dándote flexibilidad para modelar casi cualquier patrón de recurrencia.

**P: ¿Puedo personalizar las horas de trabajo para fechas de excepción específicas?**  
R: Sí. Después de crear una excepción, rellena su colección `WorkingTimes` con objetos `WorkingTime` que definan las horas de inicio y fin para ese día.

## Conclusión

Hemos recorrido todo el ciclo de vida de las operaciones de **eliminar excepción de calendario**, desde inspeccionar excepciones existentes hasta agregar nuevas y comprobar fechas. Dominar estas técnicas garantiza que los cronogramas de tus proyectos respeten calendarios del mundo real, haciendo que tus implementaciones de programación de calendarios ASP.NET sean robustas y fiables.

---

**Última actualización:** 2026-04-13  
**Probado con:** Aspose.Tasks for .NET (última versión)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}