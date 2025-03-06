---
title: Intervalos recurrentes de MS Project sin esfuerzo en Aspose.Tasks
linktitle: Gestión de intervalos recurrentes en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Descubra cómo administrar sin esfuerzo intervalos recurrentes en MS Project usando Aspose.Tasks para .NET.
type: docs
weight: 12
url: /es/net/rate-recurring-tasks/recurring-intervals/
---
## Introducción
¿Está buscando administrar intervalos recurrentes de manera eficiente en archivos de Microsoft Project usando Aspose.Tasks para .NET? Este tutorial completo lo guiará a través del proceso paso a paso, asegurándose de que pueda manejar sin esfuerzo intervalos recurrentes en sus proyectos. Antes de sumergirnos en el tutorial, repasemos algunos requisitos previos para asegurarnos de que esté listo para comenzar.
## Requisitos previos
Antes de continuar con este tutorial, asegúrese de tener lo siguiente:
1. Conocimiento de programación C#: se requiere una comprensión básica del lenguaje de programación C# y su sintaxis.
2. Visual Studio instalado: asegúrese de tener Visual Studio instalado en su sistema para codificar y compilar las aplicaciones .NET.
3. Aspose.Tasks para la biblioteca .NET: descargue e instale la biblioteca Aspose.Tasks para .NET. Puedes obtenerlo de[aquí](https://releases.aspose.com/tasks/net/).

## Importar espacios de nombres
Comience importando los espacios de nombres necesarios para acceder a las funcionalidades proporcionadas por la biblioteca Aspose.Tasks para .NET.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Ahora, dividamos cada ejemplo en varios pasos y explíquelos en detalle.
## Paso 1: inicializar el objeto del proyecto:
```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
 Aquí, inicializamos una nueva instancia del`Project` clase proporcionando la ruta al archivo de Microsoft Project.
## Paso 2: Establecer fecha de estado:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Este paso establece la fecha de estado del proyecto en su fecha de inicio.
## Paso 3: acceda a la vista del diagrama de Gantt:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Accedemos a la vista Diagrama de Gantt del proyecto.
## Paso 4: Leer la línea de progreso:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
Este paso recupera el intervalo recurrente para las líneas de progreso de la vista del diagrama de Gantt.
## Paso 5: Mostrar información del intervalo:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Aquí, mostramos información sobre el intervalo, el número de semana semanal y los días semanales.
## Paso 6: redefinir el intervalo recurrente:
```csharp
var newInterval = new RecurringInterval();
```
 Creamos una nueva instancia de`RecurringInterval` para redefinir el intervalo recurrente.
## Paso 7: Establezca líneas de progreso mensuales:
```csharp
// Establezca líneas de progreso mensuales por día.
interval.MonthlyDay = true;
// Establezca el número de días de las líneas de progreso mensuales.
interval.MonthlyDayDayNumber = 1;
// Establezca el número mensual de líneas de progreso mensuales.
interval.MonthlyDayMonthNumber = 1;
// Establezca líneas de progreso por primer o último día predefinido.
interval.MonthlyFirstLast = true;
// Establezca el tipo de líneas de progreso mensual del primer o último día.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Establezca el número mensual de líneas de progreso.
interval.MonthlyFirstLastMonthNumber = 1;
```
Estos pasos configuran las líneas de progreso mensual según los parámetros especificados.
## Paso 8: Actualizar las líneas de progreso:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Actualizamos las líneas de progreso en la vista del diagrama de Gantt con el intervalo recurrente recién definido.
## Paso 9: guarde el proyecto como PDF:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Finalmente, guardamos el proyecto con el intervalo recurrente actualizado como un archivo PDF.

## Conclusión
En conclusión, la gestión de intervalos recurrentes en archivos de Microsoft Project utilizando Aspose.Tasks para .NET se simplifica con las funcionalidades integrales proporcionadas por la biblioteca. Si sigue la guía paso a paso descrita en este tutorial, podrá manejar de manera eficiente intervalos recurrentes en sus proyectos, mejorando la productividad y la organización.
### Preguntas frecuentes
### ¿Puedo usar Aspose.Tasks para .NET con otros lenguajes de programación?
Sí, Aspose.Tasks para .NET se puede utilizar con cualquier lenguaje compatible con .NET, como C# y VB.NET.
### ¿Existe una versión de prueba disponible para Aspose.Tasks para .NET?
 Sí, puedes descargar una versión de prueba gratuita desde[aquí](https://releases.aspose.com/).
### ¿Cómo puedo obtener soporte para Aspose.Tasks para .NET?
 Puede obtener soporte en el foro Aspose.Tasks[aquí](https://forum.aspose.com/c/tasks/15).
### ¿Puedo comprar una licencia temporal de Aspose.Tasks para .NET?
 Sí, puede comprar una licencia temporal en[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo encontrar la documentación completa de Aspose.Tasks para .NET?
 La documentación completa se puede encontrar[aquí](https://reference.aspose.com/tasks/net/).