---
title: Recopile estadísticas de elementos de riesgo de MS Project en Aspose.Tasks
linktitle: Colección de estadísticas de elementos de riesgo en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a recopilar estadísticas de elementos de riesgo de archivos de MS Project utilizando Aspose.Tasks para .NET. Mejore sus capacidades de gestión de proyectos.
type: docs
weight: 22
url: /es/net/resource-risk-analysis/risk-item-statistics-collection/
---
## Introducción
En este tutorial, exploraremos cómo recopilar estadísticas de elementos de riesgo de archivos de MS Project usando Aspose.Tasks para .NET. Esta biblioteca proporciona potentes funcionalidades para analizar datos de proyectos, incluida la evaluación de riesgos y el análisis estadístico.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Aspose.Tasks para .NET: descargue e instale la biblioteca Aspose.Tasks. Puedes conseguirlo desde el[pagina de descarga](https://releases.aspose.com/tasks/net/).
2. Entorno de desarrollo: Tener un entorno de desarrollo configurado para programación .NET.

## Importar espacios de nombres
Antes de comenzar a codificar, asegúrese de importar los espacios de nombres necesarios en su proyecto:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Paso 1: cargue el archivo del proyecto
Primero, debe cargar el archivo de MS Project en su aplicación. Así es como puedes lograrlo:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Paso 2: Definir la configuración del análisis de riesgos
Inicialice la configuración del análisis de riesgos, incluido el número de iteraciones, como se muestra a continuación:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Paso 3: Inicializar un patrón de riesgo
Configure un patrón de riesgo para el análisis, especificando el tipo de distribución, los porcentajes optimistas y pesimistas y el nivel de confianza:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## Paso 4: realizar un análisis de riesgos
 Instanciar el`RiskAnalyzer` clase y analizar el proyecto:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Paso 5: recuperar estadísticas
Recupere las estadísticas del elemento de riesgo, como la finalización anticipada, del resultado del análisis:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Paso 6: Imprimir estadísticas
Repita las estadísticas e imprima los detalles:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Imprima otras estadísticas relevantes...
}
```

## Conclusión
En este tutorial, aprendimos cómo utilizar Aspose.Tasks para .NET para recopilar estadísticas de elementos de riesgo de archivos de MS Project. Si sigue estos pasos, podrá analizar eficazmente los datos del proyecto y evaluar los riesgos potenciales, lo que ayudará a mejorar la toma de decisiones y la gestión del proyecto.

## Preguntas frecuentes
### P: ¿Puede Aspose.Tasks manejar archivos grandes de MS Project?
R: Sí, Aspose.Tasks es capaz de manejar archivos grandes de MS Project de manera eficiente, ofreciendo rendimiento y escalabilidad confiables.
### P: ¿Aspose.Tasks admite otros formatos de archivos de proyecto además de .mpp?
R: Sí, Aspose.Tasks admite varios formatos de archivos de proyecto, incluidos XML y MPT.
### P: ¿Aspose.Tasks es adecuado para aplicaciones de gestión de proyectos de nivel empresarial?
R: Por supuesto, Aspose.Tasks está diseñado para satisfacer las demandas de las aplicaciones de gestión de proyectos de nivel empresarial, proporcionando funciones sólidas y documentación extensa.
### P: ¿Puedo personalizar la configuración del análisis de riesgos en Aspose.Tasks?
R: Sí, Aspose.Tasks ofrece flexibilidad para configurar los ajustes de análisis de riesgos para adaptarse a los requisitos y escenarios específicos de su proyecto.
### P: ¿Hay soporte técnico disponible para los usuarios de Aspose.Tasks?
 R: Sí, los usuarios de Aspose.Tasks pueden acceder a soporte técnico a través de Aspose.[foros](https://forum.aspose.com/c/tasks/15), donde pueden hacer preguntas, informar problemas e interactuar con la comunidad.