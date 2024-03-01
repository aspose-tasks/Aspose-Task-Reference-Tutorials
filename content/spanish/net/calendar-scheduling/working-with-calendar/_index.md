---
title: Trabajar con Calendario en Aspose.Tasks
linktitle: Trabajar con Calendario en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Administre calendarios de proyectos, calcule duraciones y maneje excepciones con facilidad usando Aspose.Tasks para .NET.
type: docs
weight: 10
url: /es/net/calendar-scheduling/working-with-calendar/
---
## Introducción

Aspose.Tasks para .NET proporciona potentes funciones para trabajar con calendarios, lo que permite a los desarrolladores gestionar de manera eficiente la programación de proyectos y la asignación de recursos. En este tutorial, exploraremos cómo utilizar Aspose.Tasks para interactuar con calendarios, cubriendo operaciones esenciales como recuperar información del calendario, definir semanas laborales, calcular horas de trabajo y más.

## Requisitos previos

Antes de comenzar, asegúrese de tener configurados los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
-  Instalación de Aspose.Tasks para .NET. Si no está instalado, descárgalo desde[aquí](https://releases.aspose.com/tasks/net/).
- Familiaridad con Visual Studio o cualquier otro entorno de desarrollo .NET preferido.

## Importar espacios de nombres

Antes de comenzar a codificar, asegúrese de importar los espacios de nombres necesarios:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Ahora, dividamos cada ejemplo en varios pasos en un formato de guía paso a paso:

## Paso 1: recuperar la información del calendario

Para recuperar información del calendario de un proyecto, siga estos pasos:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Recuperar información de calendarios
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

Explicación:
- Cargue el archivo del proyecto.
- Repita cada calendario del proyecto.
- Imprime UID y nombre de cada calendario.

## Paso 2: Lea la información sobre las semanas laborales

Para leer la información de las semanas laborales de un calendario, siga estos pasos:

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

Explicación:
- Cargue el archivo del proyecto.
- Obtenga el calendario por UID.
- Repita cada semana laboral en el calendario.
- Imprima el nombre, la fecha de inicio y la fecha de finalización de cada semana laboral.
- Recorra los días laborables y los horarios de trabajo dentro de cada semana.

## Paso 3: leer las propiedades del calendario

Para leer las propiedades de los calendarios del proyecto, siga estos pasos:

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

Explicación:
- Cargue el archivo del proyecto.
- Repita cada calendario del proyecto.
- Imprima UID, nombre y si es un calendario base.
- Imprima las horas de trabajo para cada tipo de día.

## Paso 4: Calcular las horas de trabajo

Para calcular las horas de trabajo para una tarea, siga estos pasos:

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

Explicación:
- Cargue el archivo del proyecto.
- Obtenga detalles de la tarea como calendario, fecha de inicio y fecha de finalización.
- Calcule las horas de trabajo repitiendo cada día y verificando si es un día laborable.
- Resuma la duración total en minutos.

## Paso 5: definir los días laborables para el calendario

Para definir los días de la semana para un calendario, siga estos pasos:

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

Explicación:
- Crea un nuevo proyecto y calendario.
- Agregue días laborables predeterminados (de lunes a jueves) y horarios laborales personalizados para los viernes.
- Establecer sábado y domingo como días no laborables.

## Paso 6: escribir datos del calendario actualizados en MPP

Para escribir datos de calendario actualizados en un archivo MPP, siga estos pasos:

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://compra.aspose.com/temporary-license/).");
    }
}
```

Explicación:
- Cargue el archivo del proyecto y recupere el calendario estándar.
- Modificar datos del calendario como excepciones y horarios de trabajo.
- Guarde el proyecto actualizado con los datos del calendario modificados.

## Paso 7: Calcular la fecha de finalización de la tarea dividida

Para calcular la fecha de finalización de una tarea dividida, siga estos pasos:

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

Explicación:
- Cargue el archivo del proyecto y recupere la tarea dividida.
- Obtenga el calendario del proyecto.
- Calcule la fecha de finalización en función de una duración personalizada.

## Paso 8: recuperar las excepciones del calendario

Para recuperar información sobre las excepciones del calendario, siga estos pasos:

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

Explicación:
- Cargue el archivo del proyecto.
- Iterar a través de cada calendario y sus excepciones.
- Imprima las fechas de inicio y finalización de cada excepción.

## Paso 9: Obtenga el calendario de recursos base

Para trabajar con el calendario base del calendario de un recurso, siga estos pasos:

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

Explicación:
- Cargue el archivo del proyecto.
- Agregue un recurso y su calendario.
- Imprima el nombre del calendario base para todos los recursos.

## Paso 10: eliminar calendario

Para eliminar un calendario de un proyecto, siga estos pasos:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Explicación:
- Cargue el archivo del proyecto.
- Obtenga el calendario por nombre.
- Eliminar el calendario.

## Paso 11: Obtenga la fecha de finalización por inicio y trabajo

Para calcular una fecha de finalización por fecha de inicio y trabajo, siga estos pasos:

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

Explicación:
- Cargue el archivo del proyecto.
- Obtenga el calendario estándar.
- Definir una fecha de inicio y duración del trabajo.
- Calcule la fecha de finalización en función de la fecha de inicio y el trabajo.

## Paso 12: comience el siguiente día laborable

Para comenzar el siguiente día laborable utilizando un calendario, siga estos pasos:

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

Explicación:
- Cargue el archivo del proyecto.
- Obtenga el calendario por UID.
- Obtenga la hora de inicio del siguiente día laborable.

## Paso 13: Obtener el final del día laborable anterior

Para obtener el final del día laborable anterior mediante un calendario, siga estos pasos:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Explicación:
- Cargue el archivo del proyecto.
- Obtenga el calendario por UID.
- Obtenga la hora de finalización del día laborable anterior.

## Paso 14: Obtenga la fecha de inicio desde la finalización y la duración

Para obtener una fecha de inicio por fecha de finalización y duración, siga estos pasos:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Explicación:
- Cargue el archivo del proyecto.
- Obtenga el calendario por UID.
- Calcule la fecha de inicio a partir de la fecha de finalización y la duración.

## Paso 15: Obtenga horas de trabajo

Para obtener horas de trabajo para una fecha específica, siga estos pasos:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Explicación:
- Cargue el archivo del proyecto.
- Obtenga el calendario por UID.
- Obtenga las horas de trabajo para la fecha especificada.

## Paso 16: Obtenga horarios de trabajo

Para obtener horarios de trabajo para una fecha específica, siga estos pasos:

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

Explicación:
- Cargue el archivo del proyecto.
- Obtenga el calendario por UID.
- Obtenga los horarios de trabajo para la fecha especificada.

## Conclusión

Trabajar con calendarios en Aspose.Tasks para .NET es crucial para gestionar los cronogramas de proyectos de manera efectiva. Con los ejemplos proporcionados y las guías paso a paso, puede manipular fácilmente los datos del calendario, calcular la duración de las tareas y manejar las excepciones de manera eficiente. Al integrar estas funcionalidades en sus aplicaciones, puede optimizar los procesos de gestión de proyectos y garantizar una programación precisa.

## Preguntas frecuentes

### P1: ¿Necesito una licencia para usar Aspose.Tasks para .NET?

 R1: Sí, necesita una licencia válida para utilizar Aspose.Tasks para .NET en sus aplicaciones. Puede comprar una licencia completa u obtener una licencia temporal de 30 días en[aquí](https://purchase.aspose.com/temporary-license/).

### P2: ¿Puedo modificar las excepciones del calendario mediante programación?

R2: Sí, puede agregar, actualizar o eliminar excepciones de calendario mediante programación utilizando Aspose.Tasks para las API de .NET.

### P3: ¿Cómo puedo calcular las fechas de finalización de las tareas con duraciones personalizadas?

 A3: Aspose.Tasks para .NET proporciona métodos como`GetTaskFinishDateFromDuration()` para calcular las fechas de finalización de las tareas en función de duraciones personalizadas.

### P4: ¿Es posible crear calendarios personalizados, como calendarios de turnos de noche?

R4: Sí, puede crear calendarios personalizados, como calendarios de turnos de noche, utilizando Aspose.Tasks para las API de .NET.

### P5: ¿Puedo recuperar información sobre excepciones de calendario de archivos de proyecto?

R5: Sí, puede recuperar fácilmente información sobre excepciones de calendario de archivos de proyecto usando Aspose.Tasks para .NET.