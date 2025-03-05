---
title: Dominar los días laborables en Aspose.Tasks
linktitle: Colección de días laborables en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Descubra el poder de Aspose.Tasks para .NET para gestionar los días laborables sin esfuerzo. Personalice los días laborables, elimine los fines de semana y cree calendarios especializados con facilidad.
type: docs
weight: 11
url: /es/net/time-recurrence-configuration/weekday-collection/
---
## Introducción
Aspose.Tasks para .NET es una poderosa biblioteca que facilita la manipulación eficiente de los datos de gestión de proyectos. En este tutorial, exploraremos la colección de días laborables en Aspose.Tasks, lo que le permitirá personalizar los días laborables, eliminar fines de semana y crear calendarios especializados para cumplir con los requisitos de su proyecto. Ya sea que sea un desarrollador experimentado o un recién llegado, esta guía paso a paso lo guiará a través del proceso de trabajar con los días de la semana en Aspose.Tasks para .NET.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
-  Instale la biblioteca Aspose.Tasks para .NET. Puedes descargarlo desde el[Página de descarga de Aspose.Tasks para .NET](https://releases.aspose.com/tasks/net/).
- Familiaridad con el lenguaje de programación C#.
- Entorno de desarrollo integrado (IDE) como Visual Studio.
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios a su proyecto C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Paso 1: crear una instancia de proyecto
Inicialice un nuevo proyecto Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Paso 2: accede al calendario
Recuperar el calendario del proyecto:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## Paso 3: Personaliza los días laborables
Borre los días laborables existentes y establezca los días laborables predeterminados:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Agregue otros días de la semana de manera similar...
```
## Paso 4: agregar horarios de trabajo
Agregue horarios de trabajo para días laborables específicos:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Paso 5: Mostrar información del calendario
Envíe los detalles del calendario a la consola:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Mostrar cada día de la semana y horarios de trabajo...
```
## Paso 6: eliminar los fines de semana
Retire el sábado y el domingo de los días laborables:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Paso 7: mostrar los horarios de trabajo actualizados
Salida de horarios de trabajo actualizados después de eliminar los fines de semana:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Muestra cada día laborable actualizado y horarios de trabajo...
```
## Paso 8: crea un calendario de 24 horas
Cree un calendario de 24 horas y copie los días laborables:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Conclusión
En este tutorial, exploramos las poderosas capacidades de Aspose.Tasks para .NET para administrar los días de la semana dentro de los calendarios del proyecto. Desde personalizar los días laborables hasta crear calendarios especializados de 24 horas, Aspose.Tasks simplifica el proceso, ofreciendo flexibilidad y control en la gestión de proyectos.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks para .NET con otros lenguajes de programación?
R: Aspose.Tasks admite principalmente lenguajes .NET, pero también ofrece versiones para Java.
### P: ¿Hay una prueba gratuita disponible para Aspose.Tasks para .NET?
 R: Sí, puedes descargar una prueba gratuita desde[Página de lanzamientos de Aspose.Tasks](https://releases.aspose.com/).
### P: ¿Cómo puedo obtener soporte para Aspose.Tasks para .NET?
 R: Visita el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener apoyo de la comunidad o considere comprar un plan de soporte.
### P: ¿Dónde puedo encontrar documentación completa sobre Aspose.Tasks para .NET?
 R: Consulte el[Aspose.Tasks para la documentación de .NET](https://reference.aspose.com/tasks/net/) para obtener información detallada.
### P: ¿Cómo obtengo una licencia temporal de Aspose.Tasks para .NET?
 R: Puede adquirir una licencia temporal del[página de licencia temporal](https://purchase.aspose.com/temporary-license/).