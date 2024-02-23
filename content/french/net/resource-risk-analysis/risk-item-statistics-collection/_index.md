---
title: Collecter les statistiques des éléments de risque MS Project dans Aspose.Tasks
linktitle: Collecte de statistiques sur les éléments à risque dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment collecter des statistiques sur les éléments à risque à partir de fichiers MS Project à l'aide d'Aspose.Tasks pour .NET. Améliorez vos capacités de gestion de projet.
type: docs
weight: 22
url: /fr/net/resource-risk-analysis/risk-item-statistics-collection/
---
## Introduction
Dans ce didacticiel, nous verrons comment collecter des statistiques sur les éléments à risque à partir de fichiers MS Project à l'aide d'Aspose.Tasks pour .NET. Cette bibliothèque fournit des fonctionnalités puissantes pour analyser les données du projet, y compris l'évaluation des risques et l'analyse statistique.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Aspose.Tasks pour .NET : téléchargez et installez la bibliothèque Aspose.Tasks. Vous pouvez l'obtenir auprès du[page de téléchargement](https://releases.aspose.com/tasks/net/).
2. Environnement de développement : disposez d'un environnement de développement configuré pour la programmation .NET.

## Importer des espaces de noms
Avant de commencer à coder, assurez-vous d'importer les espaces de noms nécessaires dans votre projet :
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Étape 1 : Charger le fichier de projet
Tout d'abord, vous devez charger le fichier MS Project dans votre application. Voici comment y parvenir :
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Étape 2 : Définir les paramètres d'analyse des risques
Initialisez les paramètres d'analyse des risques, y compris le nombre d'itérations, comme indiqué ci-dessous :
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Étape 3 : initialiser un modèle de risque
Définissez un modèle de risque pour l'analyse, en spécifiant le type de distribution, les pourcentages optimistes et pessimistes et le niveau de confiance :
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
## Étape 4 : Effectuer une analyse des risques
 Instancier le`RiskAnalyzer` cours et analyse du projet :
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Étape 5 : Récupérer les statistiques
Récupérez les statistiques des éléments de risque, telles que la fin anticipée, à partir du résultat de l'analyse :
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Étape 6 : Imprimer les statistiques
Parcourez les statistiques et imprimez les détails :
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Imprimer d'autres statistiques pertinentes...
}
```

## Conclusion
Dans ce didacticiel, nous avons appris à utiliser Aspose.Tasks pour .NET pour collecter des statistiques sur les éléments à risque à partir de fichiers MS Project. En suivant ces étapes, vous pouvez analyser efficacement les données du projet et évaluer les risques potentiels, contribuant ainsi à une meilleure prise de décision et à une meilleure gestion de projet.

## FAQ
### Q : Aspose.Tasks peut-il gérer des fichiers MS Project volumineux ?
R : Oui, Aspose.Tasks est capable de gérer efficacement des fichiers MS Project volumineux, offrant des performances et une évolutivité fiables.
### Q : Aspose.Tasks prend-il en charge d'autres formats de fichiers de projet que .mpp ?
R : Oui, Aspose.Tasks prend en charge différents formats de fichiers de projet, notamment XML et MPT.
### Q : Aspose.Tasks est-il adapté aux applications de gestion de projet au niveau de l'entreprise ?
R : Absolument, Aspose.Tasks est conçu pour répondre aux exigences des applications de gestion de projet au niveau de l'entreprise, en fournissant des fonctionnalités robustes et une documentation complète.
### Q : Puis-je personnaliser les paramètres d'analyse des risques dans Aspose.Tasks ?
: Oui, Aspose.Tasks offre une flexibilité dans la configuration des paramètres d'analyse des risques en fonction des exigences et des scénarios spécifiques de votre projet.
### Q : Le support technique est-il disponible pour les utilisateurs d'Aspose.Tasks ?
 R : Oui, les utilisateurs d'Aspose.Tasks peuvent accéder au support technique via Aspose.[forums](https://forum.aspose.com/c/tasks/15), où ils peuvent poser des questions, signaler des problèmes et interagir avec la communauté.