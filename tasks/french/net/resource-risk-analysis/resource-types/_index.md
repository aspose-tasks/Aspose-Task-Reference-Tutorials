---
title: Types de ressources dans Aspose.Tasks
linktitle: Types de ressources dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à travailler avec différents types de ressources dans Aspose.Tasks pour .NET, y compris les ressources de travail, de matériel et de coûts, grâce à un didacticiel étape par étape.
weight: 14
url: /fr/net/resource-risk-analysis/resource-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Types de ressources dans Aspose.Tasks

## Introduction
Aspose.Tasks for .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers Microsoft Project par programme. Que vous gériez des tâches, des ressources ou des plannings, Aspose.Tasks simplifie le processus en fournissant un ensemble complet d'API. Dans ce didacticiel, nous aborderons les différents types de ressources que vous pouvez utiliser dans vos projets à l'aide d'Aspose.Tasks pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Visual Studio : installez Visual Studio, un puissant environnement de développement intégré (IDE) pour le développement .NET.
2.  Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
3. Connaissance de base de C# : Familiarisez-vous avec C#, le langage de programmation utilisé pour le développement .NET.

## Importer des espaces de noms
Tout d'abord, importons les espaces de noms nécessaires pour accéder aux fonctionnalités d'Aspose.Tasks for .NET :
```csharp
    
```

## Étape 1 : Créer une nouvelle instance de projet
```csharp
var project = new Project();
```
Cette ligne initialise un nouvel objet Project, qui sert de conteneur pour toutes les données et opérations liées au projet.
## Étape 2 : ajouter une ressource de travail
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Ici, nous créons une nouvelle ressource de travail nommée « Ressource de travail » et spécifions son type comme ResourceType.Work.
## Étape 3 : ajouter une ressource matérielle
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
Cette étape ajoute une ressource matérielle nommée « Ressource matérielle » avec son type défini sur ResourceType.Material. De plus, nous spécifions l'étiquette du matériau comme « kg » pour indiquer l'unité de mesure.
## Étape 4 : Ajouter une ressource de coût
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Enfin, nous ajoutons une ressource de coût nommée « Cost Resource » et définissons son type sur ResourceType.Cost. De plus, nous avons fixé la valeur du coût à 59,99, ce qui représente la valeur monétaire associée à cette ressource.

## Conclusion
Dans ce didacticiel, nous avons exploré comment utiliser différents types de ressources dans Aspose.Tasks pour .NET, notamment les ressources de travail, de matériel et de coût. En suivant le guide étape par étape, vous pouvez gérer efficacement les ressources de vos projets par programmation.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks pour .NET avec d’autres formats de logiciels de gestion de projet ?
R : Oui, Aspose.Tasks prend en charge divers formats, notamment Microsoft Project (MPP), Primavera P6, etc.
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour .NET ?
 R : Oui, vous pouvez accéder à l'essai gratuit[ici](https://releases.aspose.com/).
### Q : Comment puis-je obtenir une assistance technique pour Aspose.Tasks pour .NET ?
 R : Vous pouvez visiter le forum Aspose.Tasks[ici](https://forum.aspose.com/c/tasks/15) pour une assistance technique.
### Q : Puis-je acheter une licence temporaire pour Aspose.Tasks pour .NET ?
 R : Oui, vous pouvez acheter une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Q : Aspose.Tasks pour .NET fournit-il une documentation à titre de référence ?
 R : Oui, vous pouvez trouver la documentation[ici](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
