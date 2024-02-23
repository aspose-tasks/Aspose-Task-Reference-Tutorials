---
title: Dominar los tiempos de trabajo en Aspose.Tasks
linktitle: Colección de tiempos de trabajo en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore el poder de Aspose.Tasks para .NET para administrar los cronogramas de proyectos de manera eficiente. Personalice calendarios, establezca horarios de trabajo y optimice sus proyectos con facilidad.
type: docs
weight: 14
url: /es/net/time-recurrence-configuration/working-time-collection/
---
## Introducción
¿Está buscando dominar el arte de gestionar los tiempos de trabajo en Aspose.Tasks para .NET? ¡No busque más! En esta guía paso a paso, profundizaremos en las complejidades de la recopilación del tiempo de trabajo utilizando Aspose.Tasks, permitiéndole manejar eficientemente calendarios personalizados y optimizar los cronogramas de sus proyectos.
## Requisitos previos
Antes de embarcarnos en este viaje, asegúrese de contar con los siguientes requisitos previos:
-  Biblioteca Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks para .NET desde[Página de lanzamiento de Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- Entorno de trabajo: configure un entorno de desarrollo adecuado, preferiblemente utilizando un IDE compatible con .NET.
## Importar espacios de nombres
En su proyecto, importe los espacios de nombres necesarios para acceder a las funcionalidades de Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Ahora, dividamos el tutorial en varios pasos, asegurando una experiencia de aprendizaje fluida.
## Paso 1: crea un calendario personalizado
Comience creando un nuevo proyecto y agregándole un calendario personalizado:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Paso 2: definir los días laborables
Configure los días laborables predeterminados de lunes a viernes:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Paso 3: configurar los horarios de trabajo de los sábados
Especificar horarios de trabajo para los sábados:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Paso 4: Imprima los períodos laborales de los sábados
Imprimir los horarios de trabajo configurados para el sábado:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Paso 5: configurar el horario laboral del domingo
Definir horarios de trabajo para los domingos:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Paso 6: Imprima los períodos laborales dominicales
Imprimir los horarios de trabajo configurados para el domingo:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Paso 7: agregue días personalizados al calendario
Incluir en el calendario el sábado y domingo configurados:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Paso 8: recorrer los horarios de trabajo
Recorra los horarios de trabajo y muéstrelos para cada día en el calendario:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Ahora que ha seguido los pasos con éxito, está preparado para aprovechar el poder de Aspose.Tasks para .NET para gestionar los tiempos de trabajo de forma eficaz.
## Conclusión
Dominar la recopilación de tiempos de trabajo en Aspose.Tasks le permite personalizar los calendarios de los proyectos, garantizando una programación precisa y una utilización eficiente de los recursos. Sumérgete en tus proyectos con confianza, armado con el conocimiento adquirido en esta guía completa.
## Preguntas frecuentes
### ¿Aspose.Tasks es adecuado para la gestión de proyectos a gran escala?
Sí, Aspose.Tasks está diseñado para manejar proyectos de diferentes tamaños y proporciona funciones sólidas para una gestión eficiente de proyectos.
### ¿Puedo integrar Aspose.Tasks con otras bibliotecas .NET?
¡Ciertamente! Aspose.Tasks se integra perfectamente con otras bibliotecas .NET, mejorando su versatilidad y compatibilidad.
### ¿Con qué frecuencia se actualiza Aspose.Tasks?
 Aspose.Tasks se actualiza periódicamente para incorporar nuevas funciones, mejoras y mejoras de compatibilidad. Comprobar el[página de lanzamiento](https://releases.aspose.com/tasks/net/) para las últimas actualizaciones.
### ¿Hay una prueba gratuita disponible para Aspose.Tasks?
 Sí, puedes explorar Aspose.Tasks con una prueba gratuita visitando[este enlace](https://releases.aspose.com/).
### ¿Dónde puedo buscar soporte para Aspose.Tasks?
 Para cualquier consulta o ayuda, visite el[Foro de soporte de Aspose.Tasks](https://forum.aspose.com/c/tasks/15).