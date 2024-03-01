---
title: Gestion de la collecte de ressources de projet dans Aspose.Tasks
linktitle: Gestion de la collecte de ressources dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer efficacement les collections de ressources Microsoft Project dans .NET à l'aide de l'API Aspose.Tasks. Augmentez la productivité et la flexibilité.
type: docs
weight: 13
url: /fr/net/resource-risk-analysis/managing-resource-collection/
---
## Introduction
Dans ce didacticiel, nous verrons comment gérer efficacement les collections de ressources Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Aspose.Tasks est une API puissante qui permet aux développeurs de travailler avec des fichiers Microsoft Project par programme, permettant une intégration et une manipulation transparentes des données du projet.
## Conditions préalables
Avant de vous lancer dans ce didacticiel, assurez-vous d'avoir les prérequis suivants :
1. Connaissance de C# et .NET Framework : ce didacticiel suppose une connaissance du langage de programmation C# et du .NET Framework.
2. Installation d'Aspose.Tasks pour .NET : assurez-vous d'avoir installé Aspose.Tasks pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
3. Configuration de l'environnement de développement : configurez votre environnement de développement avec Visual Studio ou tout autre IDE préféré.

## Importer des espaces de noms
Avant de commencer, importez les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.Tasks :
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Étape 1 : Charger le fichier de projet
Tout d'abord, chargez le fichier Microsoft Project dans l'objet de projet Aspose.Tasks :
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## Étape 2 : ajouter une ressource vide
Ensuite, ajoutons une ressource vide au projet :
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## Étape 3 : ajouter une ressource avec un nom
Maintenant, ajoutez une ressource avec un nom spécifié au projet :
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## Étape 4 : ajouter une ressource avant une autre ressource
Ajoutez une ressource avec un nom spécifié avant une autre ressource en fonction de son ID :
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## Étape 5 : Accéder aux ressources par ID ou UID
Vous pouvez accéder aux ressources soit par leur ID, soit par leur UID :
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## Étape 6 : Impression des informations sur les ressources
Imprimer les informations sur les ressources du projet :
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## Étape 7 : suppression de ressources
Supprimez des ressources du projet :
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## Conclusion
La gestion des collections de ressources Microsoft Project à l'aide d'Aspose.Tasks pour .NET fournit aux développeurs un ensemble d'outils robustes pour gérer efficacement les ressources du projet par programmation. En suivant les étapes décrites dans ce didacticiel, vous pouvez manipuler de manière transparente les ressources de vos projets, améliorant ainsi la productivité et la flexibilité des tâches de gestion de projet.
## FAQ
### Q : Aspose.Tasks peut-il gérer des fichiers de projet à grande échelle ?

R : Oui, Aspose.Tasks est conçu pour gérer efficacement des fichiers de projets à grande échelle, offrant des performances et une fiabilité élevées.

### Q : Aspose.Tasks est-il compatible avec différentes versions de Microsoft Project ?

R : Aspose.Tasks prend en charge différentes versions de Microsoft Project, garantissant ainsi la compatibilité entre différents environnements.

### Q : Puis-je personnaliser les propriétés des ressources à l’aide d’Aspose.Tasks ?

R : Absolument, Aspose.Tasks offre des fonctionnalités étendues pour personnaliser les propriétés des ressources en fonction des exigences spécifiques du projet.

### Q : Aspose.Tasks prend-il en charge le multithreading pour les opérations simultanées ?

: Oui, Aspose.Tasks prend en charge le multithreading, permettant des opérations simultanées sur les données du projet pour améliorer les performances.

### Q : Le support technique est-il disponible pour les utilisateurs d'Aspose.Tasks ?

 R : Oui, les utilisateurs d'Aspose.Tasks peuvent accéder au support technique via le forum.[ici](https://forum.aspose.com/c/tasks/15).