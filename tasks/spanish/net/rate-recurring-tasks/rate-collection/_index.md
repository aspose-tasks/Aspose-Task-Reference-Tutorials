---
title: Domine las tarifas de proyectos de MS con Aspose.Tasks
linktitle: Colección de tarifas en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar tarifas en archivos de MS Project usando Aspose.Tasks para .NET. Tutorial paso a paso para una gestión eficaz de los recursos.
weight: 11
url: /es/net/rate-recurring-tasks/rate-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Domine las tarifas de proyectos de MS con Aspose.Tasks

## Introducción
¡Bienvenido a nuestro tutorial sobre cómo administrar tarifas en MS Project usando Aspose.Tasks para .NET! En esta guía, lo guiaremos a través del proceso de trabajar con tarifas en sus archivos de MS Project usando Aspose.Tasks. Si es un desarrollador experimentado o recién está comenzando con el desarrollo de .NET, este tutorial le proporcionará instrucciones paso a paso para manejar eficazmente las tasas dentro de sus proyectos.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de tener los siguientes requisitos previos:
### 1. Visual Studio instalado
Asegúrese de tener Visual Studio instalado en su sistema. Puede descargarlo desde el sitio web si aún no lo ha hecho.
### 2. Aspose.Tareas para .NET
 Descargue e instale la biblioteca Aspose.Tasks para .NET desde[sitio web](https://releases.aspose.com/tasks/net/).
### 3. Conocimientos básicos de C# y .NET
Familiarícese con el lenguaje de programación C# y los conceptos básicos del marco .NET para comprender mejor los ejemplos de código proporcionados en este tutorial.
## Importar espacios de nombres
En su proyecto C#, importe los espacios de nombres necesarios para usar las funcionalidades de Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Ahora, dividamos cada ejemplo en varios pasos:
## Paso 1: Cargue un archivo de MS Project
```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Aquí creamos un nuevo`Project` objeto cargando un archivo de MS Project existente.
## Paso 2: agregue un recurso y establezca el trabajo y las tarifas
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Agregamos un nuevo recurso al proyecto, configuramos su tipo como trabajo, cantidad de trabajo y tarifa estándar.
## Paso 3: agregar tarifas al recurso
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Agregamos tarifas al recurso especificando las fechas de inicio y finalización, la tarifa estándar y el formato de tarifa.
## Paso 4: Imprimir información de tarifas
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
Este paso imprime información sobre las tarifas asociadas con el recurso.
## Paso 5: actualizar una tarifa
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Actualizamos la fecha de finalización de una tarifa específica.
## Paso 6: eliminar tarifas
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Este paso elimina todas las tarifas de un tipo específico.
## Paso 7: iterar sobre las tasas restantes
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Finalmente, iteramos sobre las tasas restantes después de la eliminación.
## Conclusión
En conclusión, este tutorial le proporcionó una guía completa sobre cómo administrar tarifas en archivos de MS Project usando Aspose.Tasks para .NET. Si sigue las instrucciones paso a paso descritas en este tutorial, podrá manejar eficientemente las tarifas dentro de sus proyectos, garantizando una gestión precisa de los recursos.
## Preguntas frecuentes
### P: ¿Puedo utilizar Aspose.Tasks para .NET con otro software de gestión de proyectos?
R: Sí, Aspose.Tasks para .NET admite la integración con varios software de gestión de proyectos, incluidos MS Project, Primavera y más.
### P: ¿Aspose.Tasks para .NET es compatible con diferentes versiones de archivos de MS Project?
R: Por supuesto, Aspose.Tasks para .NET admite trabajar con archivos de MS Project de diferentes versiones, lo que garantiza flexibilidad y compatibilidad.
### P: ¿Aspose.Tasks para .NET ofrece documentación y soporte?
 R: Sí, puede encontrar documentación completa y acceso a foros de soporte en Aspose.Tasks.[sitio web](https://reference.aspose.com/tasks/net/).
### P: ¿Puedo probar Aspose.Tasks para .NET antes de comprarlo?
R: Sí, puede aprovechar una prueba gratuita de Aspose.Tasks para .NET para evaluar sus características y compatibilidad con sus requisitos.
### P: ¿Cómo puedo comprar una licencia de Aspose.Tasks para .NET?
 R: Puede adquirir una licencia de Aspose.Tasks para .NET desde[sitio web](https://purchase.aspose.com/temporary-license/)que proporciona opciones de licencia flexibles que se adaptan a sus necesidades.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
