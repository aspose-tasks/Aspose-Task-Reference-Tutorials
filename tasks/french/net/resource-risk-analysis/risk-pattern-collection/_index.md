---
title: Gérer les modèles de risque dans MS Project avec Aspose.Tasks
linktitle: Collection de modèles de risque dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment analyser et manipuler efficacement les modèles de risque dans les fichiers Microsoft Project à l'aide d'Aspose.Tasks pour .NET.
weight: 24
url: /fr/net/resource-risk-analysis/risk-pattern-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gérer les modèles de risque dans MS Project avec Aspose.Tasks

## Introduction
Aspose.Tasks for .NET fournit une solution complète pour gérer et analyser les modèles de risque dans les fichiers Microsoft Project. Dans ce didacticiel, nous verrons comment utiliser Aspose.Tasks pour travailler efficacement avec les modèles de risque dans vos projets.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1.  Aspose.Tasks for .NET SDK : téléchargez et installez le Aspose.Tasks for .NET SDK à partir de[ici](https://releases.aspose.com/tasks/net/).
2. Environnement de développement : Une connaissance pratique du développement .NET en utilisant C#.
3. Fichier Microsoft Project : préparez un fichier Microsoft Project à utiliser.

## Importer des espaces de noms
Tout d'abord, assurez-vous d'importer les espaces de noms nécessaires pour accéder à la fonctionnalité Aspose.Tasks dans votre projet C# :
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.RiskAnalysis;
```
## Étape 1 : initialiser les paramètres RiskAnalysisSettings
 Initialisez le`RiskAnalysisSettings` objet avec les paramètres souhaités tels que le nombre d'itérations pour la simulation Monte Carlo.
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Étape 2 : Charger le fichier de projet
 Chargez votre fichier Microsoft Project à l'aide du`Project` classe:
```csharp
var project = new Project("Your_Project_File.mpp");
```
## Étape 3 : accéder aux tâches et créer des modèles de risque
Accédez aux tâches de votre projet et créez des modèles de risque pour elles. Définissez des paramètres tels que le type de distribution, les valeurs optimistes, pessimistes et le niveau de confiance.
```csharp
var task1 = project.RootTask.Children.GetById(17);
var task2 = project.RootTask.Children.GetById(18);
var pattern1 = new RiskPattern(task1)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 60,
    Pessimistic = 140,
    ConfidenceLevel = ConfidenceLevel.CL75
};
var pattern2 = new RiskPattern(task2)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
```
## Étape 4 : ajouter des modèles aux paramètres
Ajoutez les modèles de risque créés aux paramètres :
```csharp
settings.Patterns.Add(pattern1);
settings.Patterns.Add(pattern2);
```
## Étape 5 : Itérer sur les modèles
Parcourez les modèles de risque ajoutés pour afficher leurs détails :
```csharp
foreach (var pattern in settings.Patterns)
{
    Console.WriteLine("Task: " + pattern.Task);
    Console.WriteLine("Distribution: " + pattern.Distribution);
    Console.WriteLine("Optimistic: " + pattern.Optimistic);
    Console.WriteLine("Pessimistic: " + pattern.Pessimistic);
    Console.WriteLine("Confidence Level: " + pattern.ConfidenceLevel);
    Console.WriteLine();
}
```
## Étape 6 : Modifier les modèles
Modifiez les modèles selon vos besoins à l'aide de l'accès à l'index :
```csharp
settings.Patterns[task1].Optimistic = 70;
settings.Patterns[task1].Pessimistic = 140;
```
## Étape 7 : Supprimer les modèles
Supprimez les modèles indésirables de la collection :
```csharp
settings.Patterns.Remove(pattern1);
```
## Étape 8 : Effacer les modèles
Effacez la collection de motifs individuellement ou complètement :
```csharp
// Suppression individuelle
settings.Patterns.Clear();
```

## Conclusion
Dans ce didacticiel, nous avons exploré comment gérer les modèles de risque dans les fichiers Microsoft Project à l'aide d'Aspose.Tasks pour .NET. En suivant ces étapes, vous pouvez analyser et manipuler efficacement les modèles de risque au sein de vos projets, améliorant ainsi vos capacités de gestion de projet.
## FAQ
### Q : Aspose.Tasks peut-il gérer des fichiers Microsoft Project volumineux ?
R : Oui, Aspose.Tasks est optimisé pour gérer efficacement les fichiers de projet volumineux, garantissant des performances fluides même avec des données volumineuses.
### Q : Aspose.Tasks prend-il en charge différentes distributions de probabilité pour l'analyse des risques ?
R : Absolument, Aspose.Tasks propose diverses distributions de probabilité telles que Normale, Uniforme et plus encore pour répondre aux divers besoins d'analyse des risques.
### Q : Puis-je intégrer Aspose.Tasks à d’autres frameworks .NET ?
R : Certes, Aspose.Tasks s'intègre de manière transparente à d'autres frameworks .NET, vous permettant d'exploiter ses capacités sur différentes plates-formes et applications.
### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks ?
 R : Oui, vous pouvez accéder à un essai gratuit d’Aspose.Tasks à partir de[ici](https://releases.aspose.com/)vous permettant d'explorer ses fonctionnalités avant de faire un achat.
### Q : Où puis-je trouver de l'aide pour Aspose.Tasks ?
 R : Vous pouvez trouver une assistance et une assistance complètes sur le forum Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15), où vous pouvez interagir avec des experts et d'autres utilisateurs pour résoudre des requêtes et des problèmes.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
