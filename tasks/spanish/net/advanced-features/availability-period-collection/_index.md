---
date: 2026-03-21
description: Aprenda a gestionar los períodos de disponibilidad de los recursos y
  lograr una disponibilidad eficaz de los recursos del proyecto con Aspose.Tasks para
  .NET. Esta guía paso a paso muestra cómo agregar, actualizar y eliminar períodos
  de disponibilidad.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Disponibilidad de recursos del proyecto – Gestión de períodos de disponibilidad
  en Aspose.Tasks
url: /es/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Disponibilidad de Recursos del Proyecto: Colección de Períodos de Disponibilidad en Aspose.Tasks

Gestionar la **disponibilidad de recursos del proyecto** es una parte fundamental de una planificación exitosa. En este tutorial aprenderás **cómo gestionar la disponibilidad** de los recursos usando la API Aspose.Tasks para .NET, paso a paso, desde cargar un proyecto hasta copiar períodos entre recursos.

## Respuestas rápidas
- **¿Cuál es la clase principal para los períodos de disponibilidad?** `AvailabilityPeriod` en el espacio de nombres `Aspose.Tasks`.  
- **¿Puedo borrar los períodos existentes?** Sí, llama a `resource.AvailabilityPeriods.Clear()`.  
- **¿Cómo añado un nuevo período?** Crea un objeto `AvailabilityPeriod` y usa `Add` o `Insert`.  
- **¿Es posible copiar períodos a otro recurso?** Absolutamente – usa `CopyTo` y luego agrega cada elemento al recurso de destino.  
- **¿Necesito una licencia para uso en producción?** Sí, se requiere una licencia comercial de Aspose.Tasks para implementaciones que no sean de prueba.

## ¿Qué es la disponibilidad de recursos del proyecto?
La disponibilidad de recursos del proyecto define las fechas y unidades (porcentaje de capacidad) cuando un recurso puede ser asignado a tareas. Al controlar estos períodos evitas la sobreasignación y mejoras la precisión del cronograma.

## ¿Por qué usar Aspose.Tasks para gestionar períodos de disponibilidad?
- **Integración completa con .NET** – sin interop COM, código totalmente administrado.  
- **Control granular** – establece fechas de inicio/fin exactas y unidades fraccionarias.  
- **Copia fácil** – mueve datos de disponibilidad entre recursos sin análisis manual.  
- **Optimizado para rendimiento** – funciona eficientemente con archivos MPP grandes.

## Requisitos previos
1. **Visual Studio** – cualquier versión reciente (2019, 2022 o posterior).  
2. **Aspose.Tasks para .NET** – descárgalo desde [aquí](https://releases.aspose.com/tasks/net/).  
3. **Conocimientos básicos de C#** – deberías estar cómodo con clases, colecciones y LINQ.

## Importar espacios de nombres

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

Importamos el espacio de nombres principal de Aspose.Tasks junto con las colecciones estándar de .NET que necesitaremos más adelante.

## Paso 1: Inicializar el proyecto y el recurso

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Aquí cargamos un archivo MPP existente y obtenemos el recurso cuya disponibilidad queremos editar (ID = 1).

## Paso 2: Borrar los períodos de disponibilidad existentes

```csharp
resource.AvailabilityPeriods.Clear();
```

Borrar elimina cualquier período previamente definido, dándonos una hoja limpia.

## Paso 3: Añadir períodos de disponibilidad

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Recuperamos una colección de objetos `AvailabilityPeriod` (se asume que el asistente `GetPeriods` está definido en otro lugar) y añadimos cada uno, verificando que la colección sea modificable.

## Paso 4: Insertar un nuevo período de disponibilidad

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Esto crea un período personalizado para el año 2013 e lo inserta en la posición 1 (segundo espacio) si aún no está presente.

## Paso 5: Mostrar los períodos de disponibilidad

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Una rápida volcado en consola muestra el recuento total y los detalles de cada período – útil para depuración o verificación.

## Paso 6: Copiar los períodos de disponibilidad a otro recurso

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Copiamos toda la colección a un arreglo, borramos los períodos del recurso de destino y luego los repoblamos. Esto demuestra cómo duplicar datos de disponibilidad entre recursos.

## Paso 7: Actualizar y eliminar períodos de disponibilidad

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Aquí ajustamos `AvailableUnits` para el penúltimo período y luego eliminamos el período 2013 que añadimos antes.

## Problemas comunes y soluciones
- **Error de colección de solo lectura** – Asegúrate de que el proyecto no esté abierto en modo solo lectura o de que hayas llamado a `resource.AvailabilityPeriods.Clear()` antes de añadir nuevos elementos.  
- **Períodos superpuestos** – Aspose.Tasks no fusiona automáticamente los solapamientos; puede que necesites escribir lógica personalizada para detectarlos y resolverlos.  
- **Formato de fecha incorrecto** – Siempre usa objetos `DateTime`; el análisis de cadenas puede generar errores dependientes de la configuración regional.

## Preguntas frecuentes

**P: ¿Puedo añadir campos personalizados a los períodos de disponibilidad?**  
R: No, los períodos de disponibilidad en Aspose.Tasks para .NET no admiten campos personalizados.

**P: ¿Los períodos de disponibilidad están vinculados a tareas específicas?**  
R: No, están asociados a recursos y definen cuándo el recurso está generalmente disponible para tareas.

**P: ¿Puedo importar períodos de disponibilidad desde fuentes externas?**  
R: Sí, puedes importar períodos desde CSV, XML o una base de datos creando objetos `AvailabilityPeriod` y añadiéndolos a la colección.

**P: ¿Cómo manejo períodos de disponibilidad superpuestos?**  
R: Los solapamientos no se resuelven automáticamente; debes implementar validación personalizada para fusionar o rechazar períodos conflictivos.

**P: ¿Existe un límite al número de períodos de disponibilidad que puede tener un recurso?**  
R: No hay un límite codificado, pero colecciones muy grandes pueden afectar el rendimiento; considera consolidar períodos cuando sea posible.

## Conclusión

En esta guía cubrimos todo lo que necesitas saber para gestionar la **disponibilidad de recursos del proyecto** con Aspose.Tasks para .NET—desde inicializar un proyecto y borrar datos antiguos, hasta añadir, insertar, copiar, actualizar y eliminar períodos de disponibilidad. Dominar estos pasos te ayuda a mantener calendarios de recursos precisos y tus cronogramas de proyecto realistas.

---

**Última actualización:** 2026-03-21  
**Probado con:** Aspose.Tasks para .NET (última versión)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}