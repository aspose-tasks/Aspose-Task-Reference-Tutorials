---
title: Statistiques concernant les éléments à risque dans Aspose.Tasks
linktitle: Statistiques concernant les éléments à risque dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Libérez la puissance de l’analyse des risques dans les fichiers MS Project à l’aide d’Aspose.Tasks pour .NET. Obtenez des informations, atténuez les incertitudes et favorisez la réussite de vos projets sans effort.
type: docs
weight: 21
url: /fr/net/resource-risk-analysis/risk-item-statistics/
---
## Introduction
Cherchez-vous à améliorer vos prouesses en matière de gestion de projet à l’aide d’Aspose.Tasks pour .NET ? Plongez dans le domaine de l'analyse des risques avec notre didacticiel étape par étape sur l'obtention de statistiques sur les éléments de risque dans les fichiers MS Project. En tirant parti des puissantes capacités d'Aspose.Tasks, vous pouvez obtenir des informations inestimables sur les incertitudes du projet et prendre des décisions éclairées pour atténuer efficacement les risques.
## Conditions préalables
Avant de nous lancer dans cette aventure, assurez-vous d’avoir les conditions préalables suivantes en place :
1.  Aspose.Tasks for .NET Library : téléchargez et installez la bibliothèque à partir du[Aspose.Tasks pour la documentation .NET](https://reference.aspose.com/tasks/net/). Cette bibliothèque vous équipe d'outils robustes pour manipuler les fichiers MS Project par programme.
2. Environnement de développement .NET : configurez votre environnement de développement .NET, y compris Visual Studio ou tout autre IDE de votre choix, pour faciliter l'intégration transparente d'Aspose.Tasks dans vos projets.

## Importer des espaces de noms
Incorporez les espaces de noms nécessaires dans votre projet pour exploiter les fonctionnalités d'Aspose.Tasks :
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Étape 1 : Définir le répertoire de données
```csharp
String DataDir = "Your Document Directory";
```
 Assurez-vous de remplacer`"Your Document Directory"` avec le chemin d'accès à votre répertoire de documents où se trouvent vos fichiers MS Project.
## Étape 2 : configurer les paramètres d'analyse des risques
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Ajuste le`IterationsCount`paramètre basé sur les exigences de votre projet pour contrôler la précision de l’analyse des risques.
## Étape 3 : Charger le fichier MS Project
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Chargez le fichier MS Project souhaité dans le`project` objet pour une analyse plus approfondie.
## Étape 4 : Définir la tâche et initialiser le modèle de risque
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
Spécifiez la tâche d'analyse des risques et configurez le modèle de risque avec des paramètres appropriés tels que le type de distribution, les durées optimistes et pessimistes et le niveau de confiance.
## Étape 5 : Analyser les risques du projet
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Initiez le processus d’analyse des risques en utilisant les paramètres définis et les données du projet.
## Étape 6 : Récupérer et afficher les statistiques
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
Récupérez et affichez diverses mesures statistiques liées aux éléments de risque dans le fichier MS Project, notamment la valeur attendue, l'écart type, les centiles, les valeurs minimales et maximales.

## Conclusion
En conclusion, maîtriser l'analyse des risques dans les fichiers MS Project à l'aide d'Aspose.Tasks pour .NET ouvre un champ de possibilités pour les chefs de projet et les parties prenantes. En suivant notre didacticiel complet, vous pouvez naviguer à travers les incertitudes en toute confiance, garantissant ainsi la réussite de votre projet.
## FAQ
### Puis-je intégrer Aspose.Tasks à d’autres bibliothèques .NET pour des fonctionnalités étendues ?
Absolument! Aspose.Tasks s'intègre de manière transparente à diverses bibliothèques .NET, vous permettant d'amplifier ses capacités en fonction des exigences de votre projet.
### Existe-t-il une version d’essai disponible pour Aspose.Tasks pour .NET ?
 Oui, vous pouvez explorer les fonctionnalités d'Aspose.Tasks en accédant au[essai gratuit](https://releases.aspose.com/) disponible sur notre site Internet.
### À quelle fréquence les mises à jour et les améliorations sont-elles publiées pour Aspose.Tasks ?
Nous nous efforçons d'améliorer continuellement Aspose.Tasks en publiant périodiquement des mises à jour et des améliorations, garantissant ainsi que vous avez toujours accès aux dernières fonctionnalités et optimisations.
### Puis-je obtenir une assistance technique pour Aspose.Tasks ?
Certainement! Notre équipe d'assistance dédiée est facilement disponible sur le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour vous aider à répondre à toutes vos questions ou difficultés que vous pourriez rencontrer au cours de votre parcours de mise en œuvre.
### Proposez-vous des licences temporaires pour des projets à court terme ?
 Oui, si vous avez besoin d'Aspose.Tasks pour un projet à court terme, vous pouvez profiter de notre service pratique[permis temporaire](https://purchase.aspose.com/temporary-license/) option pour répondre à vos besoins en matière de licences sans aucun engagement à long terme.