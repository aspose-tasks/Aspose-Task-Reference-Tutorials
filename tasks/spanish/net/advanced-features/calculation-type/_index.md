---
date: 2026-03-24
description: Aprenda a configurar el cálculo en Aspose.Tasks para .NET, con ejemplos
  para calcular valores resumidos, definir la fórmula de cálculo y configurar el resumen
  acumulado.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cómo establecer el tipo de cálculo en Aspose.Tasks
url: /es/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer el tipo de cálculo en Aspose.Tasks

## Introducción

Si necesitas **cómo establecer la regla de cálculo** para tareas y filas de resumen en un archivo Microsoft Project, este tutorial te muestra exactamente eso usando Aspose.Tasks para .NET. Recorreremos un **ejemplo completo de tipo de cálculo**, demostraremos cómo **calcular valores de resumen** y explicaremos cómo **definir la fórmula de cálculo** y **configurar el resumen acumulado** para atributos extendidos. Al final, podrás agregar una tarea a un proyecto, establecer lógica de cálculo personalizada y controlar el comportamiento de acumulación con confianza.

## Respuestas rápidas
- **¿Cuál es el propósito principal?** Controlar cómo se calculan los valores de tareas y resúmenes en un archivo Project.  
- **¿Qué clase de API se utiliza?** `ExtendedAttributeDefinition` junto con `CalculationType` y `SummaryRowsCalculationType`.  
- **¿Puedo usar una fórmula?** Sí – establece `CalculationType = CalculationType.Formula` y proporciona una cadena de fórmula.  
- **¿Cómo acumulo los valores de resumen?** Usa `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` y especifica un `RollupType` como `Average`.  
- **¿Necesito una licencia?** Se requiere una licencia válida de Aspose.Tasks para uso en producción.

## ¿Qué es el tipo de cálculo y cómo establecer el cálculo?

`CalculationType` indica a Aspose.Tasks cómo calcular el valor de un atributo extendido. Puedes elegir un valor estático, una fórmula o permitir que la biblioteca acumule valores de tareas hijas. Establecer el cálculo correctamente es esencial cuando deseas que el proyecto refleje reglas de negocio personalizadas sin actualizaciones manuales.

## ¿Por qué usar el tipo de cálculo para calcular valores de resumen?

Cuando un proyecto contiene tareas resumen, a menudo necesitas que las filas de resumen muestren datos agregados (p. ej., costo total, duración promedio). Configurando **calcular valores de resumen** mediante `SummaryRowsCalculationType` y `RollupType`, Aspose.Tasks puede mantener automáticamente esos agregados sincronizados al modificar tareas individuales.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

1. Conocimientos básicos de C# y el framework .NET.  
2. Visual Studio (cualquier versión reciente) instalado en tu máquina.  
3. Biblioteca Aspose.Tasks para .NET instalada – puedes descargarla desde [aquí](https://releases.aspose.com/tasks/net/).  
4. Acceso a la documentación oficial de Aspose.Tasks para .NET para referencia, disponible [aquí](https://reference.aspose.com/tasks/net/).

## Importar espacios de nombres

Antes de sumergirte en el ejemplo, asegúrate de importar los espacios de nombres necesarios:

```csharp
using Aspose.Tasks;
using System;
```

## Paso 1: Crear un nuevo Project

Primero, creamos un objeto `Project` vacío que contendrá nuestras tareas y atributos personalizados.

```csharp
var project = new Project();
```

## Paso 2: Agregar una tarea al proyecto

Ahora **agregamos datos de proyecto** creando una tarea simple, estableciendo su fecha de inicio y dándole una duración de un día.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Paso 3: Definir el tipo de cálculo para un atributo extendido (Ejemplo de fórmula)

Aquí creamos una definición de atributo extendido cuyo valor se calcula a partir de una fórmula. Esto demuestra un **ejemplo de tipo de cálculo** y muestra cómo **definir la fórmula de cálculo**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Paso 4: Definir el tipo de cálculo para filas de resumen (Configurar resumen acumulado)

A continuación, creamos otra definición de atributo extendido que indica a Aspose.Tasks **configurar el resumen acumulado** usando el tipo de acumulación *Average*. Esta es la forma típica de **calcular valores de resumen** para costo, trabajo o campos personalizados.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Problemas comunes y solución de errores

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| La fórmula devuelve `null` | Referencia de campo incorrecta en la fórmula | Verifica el nombre del campo entre corchetes (p. ej., `[Start]` no `[stARt]`). |
| Las filas de resumen muestran 0 | `SummaryRowsCalculationType` no está configurado o `RollupType` incorrecto | Asegúrate de que `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` y elige un `RollupType` apropiado. |
| El proyecto no se carga después de agregar atributos | Incompatibilidad entre la definición del atributo y su uso en la tarea | Añade la definición del atributo **antes** de asignarlo a cualquier tarea. |

## Conclusión

En este tutorial, hemos cubierto **cómo establecer reglas de cálculo** en Aspose.Tasks para .NET, desde crear una tarea simple hasta definir tipos de cálculo basados en fórmulas y en acumulación. Al dominar estas configuraciones obtienes un control granular sobre **calcular valores de resumen**, lo que permite análisis de proyecto más ricos sin trabajo manual en hojas de cálculo.

## Preguntas frecuentes

### P1: ¿Qué es el tipo de cálculo en Aspose.Tasks?

R1: El tipo de cálculo en Aspose.Tasks determina cómo se calculan los valores para tareas y tareas resumen dentro de un proyecto, ofreciendo opciones como Fórmula y Acumulación.

### P2: ¿Cómo establezco el tipo de cálculo para un atributo extendido?

R2: Puedes establecer el tipo de cálculo para un atributo extendido definiendo su propiedad `CalculationType` según corresponda.

### P3: ¿Puedo personalizar el tipo de cálculo para filas de resumen en un proyecto?

R3: Sí, Aspose.Tasks permite especificar el tipo de cálculo para filas de resumen, lo que te permite adaptar los cálculos de valores según tus requisitos.

### P4: ¿Existen diferentes tipos de acumulación disponibles para los cálculos de tareas resumen?

R4: Sí, Aspose.Tasks proporciona varios tipos de acumulación como Average, Sum y Count para calcular los valores de tareas resumen.

### P5: ¿Dónde puedo encontrar más recursos sobre Aspose.Tasks para .NET?

R5: Puedes explorar la documentación y los foros de soporte de la comunidad disponibles en [Aspose.Tasks para .NET](https://reference.aspose.com/tasks/net/) para obtener orientación y asistencia completas.

---

**Última actualización:** 2026-03-24  
**Probado con:** Aspose.Tasks para .NET (última versión)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}