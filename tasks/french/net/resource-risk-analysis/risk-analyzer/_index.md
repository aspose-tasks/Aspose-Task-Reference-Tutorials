---
title: Analyser les risques de MS Project avec Aspose.Tasks
linktitle: Analyser les risques avec Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à analyser efficacement les risques MS Project avec Aspose.Tasks pour .NET. Suivez notre guide étape par étape pour une gestion complète des risques.
weight: 20
url: /fr/net/resource-risk-analysis/risk-analyzer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Analyser les risques de MS Project avec Aspose.Tasks

## Introduction
La gestion des risques dans la gestion de projet est essentielle pour garantir la réussite du projet. Aspose.Tasks for .NET fournit des outils puissants pour analyser et atténuer les risques dans les fichiers Microsoft Project. Dans ce didacticiel, nous explorerons comment analyser les risques MS Project à l'aide d'Aspose.Tasks, étape par étape.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Visual Studio : assurez-vous que Visual Studio est installé sur votre système.
2.  Aspose.Tasks pour .NET : téléchargez et installez Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
3. Fichier Microsoft Project : préparez un fichier MS Project que vous souhaitez analyser pour détecter les risques.

## Importer des espaces de noms
Dans votre code C#, incluez les espaces de noms nécessaires :
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Étape 1 : initialiser les paramètres d'analyse des risques
Configurez les paramètres d’analyse des risques, tels que le nombre d’itérations et les modèles de risque.
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Étape 2 : Charger le fichier MS Project
Chargez le fichier MS Project dont vous souhaitez analyser les risques.
```csharp
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Étape 3 : Définir le modèle de tâche et de risque
Spécifiez la tâche et définissez le modèle de risque pour l'analyse.
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
## Étape 4 : Analyser les risques du projet
Effectuer l'analyse des risques sur le projet.
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
var earlyFinish = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
```
## Étape 5 : Récupérer les résultats de l'analyse
Récupérez et affichez les résultats de l’analyse, tels que les valeurs attendues et les percentiles.
```csharp
Console.WriteLine("Expected value: {0}", earlyFinish.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", earlyFinish.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", earlyFinish.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", earlyFinish.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", earlyFinish.GetPercentile(90));
Console.WriteLine("Minimum: {0}", earlyFinish.Minimum);
Console.WriteLine("Maximum: {0}", earlyFinish.Maximum);
```
## Étape 6 : Ajuster les paramètres d'analyse (facultatif)
Modifiez les paramètres d'analyse si nécessaire et réexécutez l'analyse.
```csharp
settings = new RiskAnalysisSettings
{
    IterationsCount = 300
};
analyzer.Settings = settings;
analysisResult = analyzer.Analyze(project);
earlyFinish = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
```
## Étape 7 : Enregistrer le rapport d'analyse
Enregistrez le rapport d'analyse, par exemple, sous forme de fichier PDF.
```csharp
analysisResult.SaveReport(DataDir + "AnalysisReport_out.pdf");
```

## Conclusion
En conclusion, Aspose.Tasks for .NET offre des fonctionnalités robustes pour analyser les risques de MS Project, permettant aux chefs de projet de prendre des décisions éclairées et d'atténuer les problèmes potentiels. En suivant les étapes décrites dans ce didacticiel, vous pouvez utiliser efficacement Aspose.Tasks pour gérer les risques du projet en toute confiance.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks avec d’autres outils de gestion de projet ?
: Oui, Aspose.Tasks prend en charge l'intégration avec diverses plateformes et outils de gestion de projet.
### Q : Aspose.Tasks est-il adapté aux projets au niveau de l'entreprise ?
R : Absolument, Aspose.Tasks est conçu pour répondre aux besoins des projets à petite échelle et au niveau de l'entreprise.
### Q : Puis-je personnaliser les paramètres d'analyse des risques dans Aspose.Tasks ?
R : Oui, vous pouvez adapter les paramètres d'analyse des risques en fonction des exigences spécifiques de votre projet.
### Q : Aspose.Tasks prend-il en charge plusieurs langages de programmation ?
R : Aspose.Tasks cible principalement les langages .NET, mais il offre également la prise en charge de Java.
### Q : Où puis-je trouver une assistance supplémentaire pour Aspose.Tasks ?
 R : Vous pouvez explorer la documentation Aspose.Tasks ou visiter le support[forum]( https://forum.aspose.com/c/tasks/15) à l'aide.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
