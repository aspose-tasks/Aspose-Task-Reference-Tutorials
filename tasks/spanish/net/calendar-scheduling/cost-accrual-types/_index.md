---
date: 2026-07-05
description: Aprenda cómo seguir el presupuesto del proyecto y gestionar los costos
  del proyecto usando Aspose.Tasks para .NET. Defina Cost Accrual Types para un seguimiento
  preciso de los costos.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Cost Accrual Types en Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Seguimiento del presupuesto del proyecto con Cost Accrual Types en Aspose.Tasks
url: /es/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rastrear el presupuesto del proyecto con tipos de acumulación de costos en Aspose.Tasks

## Introducción

Rastrear con precisión el **presupuesto del proyecto** es la columna vertebral de una entrega exitosa. Cuando la información de costos se captura en los momentos adecuados, puedes pronosticar sobrecostos, ajustar recursos y mantener informadas a las partes interesadas. Aspose.Tasks para .NET brinda a los desarrolladores un control detallado sobre la acumulación de costos, permitiéndote decidir *cuándo* se registra un costo—ya sea al inicio del trabajo, de forma continua, o solo cuando el trabajo se completa. Este tutorial te guía a través de los conceptos, muestra cómo establecer un tipo de acumulación y demuestra las mejores prácticas para un seguimiento fiable del presupuesto.

## Respuestas rápidas
- **¿Cuál es el propósito principal de los tipos de acumulación de costos?** Determinan el punto en el ciclo de vida de una tarea en el que se reconoce el costo, lo que permite un seguimiento preciso del presupuesto.  
- **¿Qué valor de enumeración retrasa el costo hasta que el trabajo termina?** `CostAccrualType.End`.  
- **¿Necesito una licencia para ejecutar el código?** Sí, se requiere una licencia válida de Aspose.Tasks para uso en producción.  
- **¿Puedo cambiar los tipos de acumulación para muchos recursos a la vez?** Sí—recorre la colección `Resources` y asigna el tipo deseado.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ¿Qué es el tipo de acumulación de costos?
Un **tipo de acumulación de costos** indica a Aspose.Tasks cuándo aplicar el costo de un recurso al presupuesto del proyecto. Está representado por la enumeración `CostAccrualType` y puede establecerse por recurso o por tarea. Elegir el tipo correcto garantiza que los datos de costos se alineen con las políticas de facturación de tu organización, ya sea que necesites costos registrados al inicio del trabajo, prorrateados a lo largo de la duración, o solo después de la finalización.

## ¿Por qué rastrear el presupuesto del proyecto usando tipos de acumulación de costos?
Aspose.Tasks admite **cuatro** opciones de acumulación—`Start`, `Prorated`, `Duration` y `End`—que cubren todo el rango de escenarios típicos de contabilidad de proyectos. Seleccionar la opción adecuada te permite alinear el reconocimiento de costos con los ciclos de facturación contractuales, reducir la variación en los informes financieros y generar estados de costos que se integren sin problemas con los sistemas ERP, todo mientras mantienes un bajo uso de memoria en proyectos grandes.

## Requisitos previos

Antes de comenzar, asegúrate de contar con los siguientes requisitos:

### 1. Instalar Aspose.Tasks para .NET
Para comenzar, necesitas tener Aspose.Tasks para .NET instalado en tu entorno de desarrollo. Puedes descargar la biblioteca desde la [página de descarga](https://releases.aspose.com/tasks/net/) y seguir las instrucciones de instalación proporcionadas.

### 2. Familiaridad con .NET Framework
Se requiere conocimiento básico del framework .NET y del lenguaje de programación C# para seguir los ejemplos de este tutorial.

## ¿Cómo establecer el tipo de acumulación de costos para un recurso?

Carga el proyecto, localiza el recurso objetivo y asigna el `CostAccrualType` deseado. El patrón de dos líneas a continuación es el enfoque estándar: crear una instancia `Project`, obtener el recurso por su ID y luego establecer `CostAccrualType`. Esta secuencia concisa garantiza que **rastrees el presupuesto del proyecto** con precisión desde el momento en que se agrega el recurso.

### Paso 1: Importar espacios de nombres
Comencemos importando los espacios de nombres necesarios para acceder a la funcionalidad de Aspose.Tasks en nuestro proyecto .NET:

```csharp

```

Ahora que tenemos los espacios de nombres listos, podemos pasar a cargar un archivo de proyecto.

### Paso 2: Cargar archivo de proyecto
La clase `Project` representa un archivo de Microsoft Project y brinda acceso a sus tareas, recursos y otros datos.

```csharp
var project = new Project("Project2.mpp");
```

Primero, necesitamos cargar el archivo de proyecto en nuestra aplicación. Creamos un nuevo objeto `Project` y lo inicializamos con la ruta a nuestro archivo de proyecto.

### Paso 3: Acceder al recurso
La colección `Resources` contiene todos los recursos definidos en el proyecto. El método `GetById` recupera un recurso por su identificador único.

```csharp
var resource = project.Resources.GetById(1);
```

A continuación, accedemos al recurso al que queremos aplicar el tipo de acumulación de costos. Utilizamos el método `GetById` de la colección `Resources` y pasamos el ID del recurso como argumento. Esto demuestra **acceso al recurso por id**, un requisito común al automatizar actualizaciones de costos.

### Paso 4: Establecer el tipo de acumulación de costos
El método `Set` asigna un valor a un campo del recurso.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Aquí, establecemos el tipo de acumulación de costos para el recurso. En este ejemplo, lo configuramos como `CostAccrualType.End`, lo que significa que los costos no se acumularán hasta que el trabajo restante sea cero. Elegir `End` es ideal cuando deseas **rastrear el presupuesto del proyecto** solo después de que una tarea se haya completado por completo.

### Paso 5: Continuar trabajando con el proyecto
Después de establecer el tipo de acumulación de costos, puedes continuar trabajando con el proyecto según sea necesario, realizando operaciones o cálculos adicionales, como generar informes de costos, actualizar asignaciones o exportar el archivo.

## Problemas comunes y consejos profesionales
- **Consejo profesional:** Siempre llama a `project.Save` después de modificar los tipos de acumulación para guardar los cambios.  
- **Trampa:** Configurar `CostAccrualType.Start` en un recurso que nunca inicia trabajo inflará los informes de presupuesto—verifica primero los cronogramas de las tareas.  
- **Consejo profesional:** Usa `project.Resources.ToList()` cuando necesites actualizar en lote muchos recursos; esto evita búsquedas repetidas en la colección y mejora el rendimiento en proyectos grandes.

## Preguntas frecuentes

**Q:** ¿Puedo cambiar el tipo de acumulación de costos para varios recursos simultáneamente?  
**A:** Sí, recorre `project.Resources` y asigna el `CostAccrualType` deseado a cada recurso dentro de un bucle `foreach`.

**Q:** ¿Cuáles son los otros tipos de acumulación de costos disponibles además de `End`?  
**A:** Aspose.Tasks ofrece `Start`, `Prorated` y `Duration`, cada uno alineado con una estrategia de facturación diferente.

**Q:** ¿Cómo puedo determinar el tipo de acumulación de costos actual para un recurso específico?  
**A:** Obtén el valor mediante `resource.Get(TskResource.CostAccrualType)`; devuelve la enumeración que representa la configuración actual.

**Q:** ¿Es posible aplicar diferentes tipos de acumulación de costos a distintas tareas en el mismo proyecto?  
**A:** Absolutamente. Tanto las tareas como los recursos exponen una propiedad `CostAccrualType`, lo que permite una configuración independiente por entidad.

**Q:** ¿Aspose.Tasks admite tipos de acumulación de costos personalizados?  
**A:** No, la biblioteca actualmente solo admite los cuatro tipos incorporados; la lógica personalizada debe implementarse externamente si es necesario.

---

**Última actualización:** 2026-07-05  
**Probado con:** Aspose.Tasks 24.8 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Calendario y programación de Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [Manejo de tarifas de MS Project con Aspose.Tasks para .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Gestión sin esfuerzo de recursos de MS Project con Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}