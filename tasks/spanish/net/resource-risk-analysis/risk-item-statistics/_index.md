---
title: Estadísticas para elementos de riesgo en Aspose.Tasks
linktitle: Estadísticas para elementos de riesgo en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Desbloquee el poder del análisis de riesgos en archivos de MS Project utilizando Aspose.Tasks para .NET. Obtenga información valiosa, mitigue las incertidumbres e impulse el éxito del proyecto sin esfuerzo.
weight: 21
url: /es/net/resource-risk-analysis/risk-item-statistics/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Estadísticas para elementos de riesgo en Aspose.Tasks

## Introducción
¿Está buscando mejorar su destreza en la gestión de proyectos utilizando Aspose.Tasks para .NET? Profundice en el ámbito del análisis de riesgos con nuestro tutorial paso a paso sobre cómo obtener estadísticas para elementos de riesgo en archivos de MS Project. Al aprovechar las poderosas capacidades de Aspose.Tasks, puede obtener información valiosa sobre las incertidumbres del proyecto y tomar decisiones informadas para mitigar los riesgos de manera efectiva.
## Requisitos previos
Antes de embarcarnos en este viaje, asegúrese de contar con los siguientes requisitos previos:
1.  Aspose.Tasks para la biblioteca .NET: descargue e instale la biblioteca desde[Aspose.Tasks para la documentación de .NET](https://reference.aspose.com/tasks/net/). Esta biblioteca le proporciona herramientas sólidas para manipular archivos de MS Project mediante programación.
2. Entorno de desarrollo .NET: configure su entorno de desarrollo .NET, incluido Visual Studio o cualquier otro IDE de su elección, para facilitar la integración perfecta de Aspose.Tasks en sus proyectos.

## Importar espacios de nombres
Incorpore los espacios de nombres necesarios en su proyecto para aprovechar las funcionalidades de Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Paso 1: definir el directorio de datos
```csharp
String DataDir = "Your Document Directory";
```
 Asegúrese de reemplazar`"Your Document Directory"` con la ruta a su directorio de documentos donde se encuentran sus archivos de MS Project.
## Paso 2: configurar los ajustes del análisis de riesgos
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Ajustar el`IterationsCount`parámetro basado en los requisitos de su proyecto para controlar la precisión del análisis de riesgos.
## Paso 3: cargar el archivo de MS Project
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Cargue el archivo de MS Project deseado en el`project` objeto para un análisis posterior.
## Paso 4: definir la tarea e inicializar el patrón de riesgo
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
Especifique la tarea para el análisis de riesgos y configure el patrón de riesgo con parámetros apropiados, como el tipo de distribución, las duraciones optimistas y pesimistas y el nivel de confianza.
## Paso 5: Analizar los riesgos del proyecto
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Inicie el proceso de análisis de riesgos utilizando la configuración definida y los datos del proyecto.
## Paso 6: recuperar y mostrar estadísticas
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
Recupere y muestre varias métricas estadísticas relacionadas con elementos de riesgo en el archivo de MS Project, incluido el valor esperado, la desviación estándar, los percentiles y los valores mínimo y máximo.

## Conclusión
En conclusión, dominar el análisis de riesgos en archivos de MS Project usando Aspose.Tasks para .NET abre un mundo de posibilidades para los gerentes de proyectos y las partes interesadas. Si sigue nuestro tutorial completo, podrá navegar a través de las incertidumbres con confianza, garantizando resultados exitosos del proyecto.
## Preguntas frecuentes
### ¿Puedo integrar Aspose.Tasks con otras bibliotecas .NET para ampliar la funcionalidad?
¡Absolutamente! Aspose.Tasks se integra perfectamente con varias bibliotecas .NET, lo que le permite ampliar sus capacidades según los requisitos de su proyecto.
### ¿Existe una versión de prueba disponible para Aspose.Tasks para .NET?
 Sí, puede explorar las funciones de Aspose.Tasks accediendo al[prueba gratis](https://releases.aspose.com/) disponible en nuestro sitio web.
### ¿Con qué frecuencia se publican actualizaciones y mejoras para Aspose.Tasks?
Nos esforzamos por mejorar continuamente Aspose.Tasks mediante la publicación de actualizaciones y mejoras periódicamente, asegurando que siempre tenga acceso a las últimas funciones y optimizaciones.
### ¿Puedo obtener soporte técnico para Aspose.Tasks?
¡Ciertamente! Nuestro equipo de soporte dedicado está disponible en el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para ayudarle con cualquier consulta o desafío que pueda encontrar durante su proceso de implementación.
### ¿Ofrecen licencias temporales para proyectos a corto plazo?
 Sí, si necesita Aspose.Tasks para un proyecto a corto plazo, puede aprovechar nuestra conveniente[licencia temporal](https://purchase.aspose.com/temporary-license/) opción para satisfacer sus necesidades de licencia sin compromisos a largo plazo.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
