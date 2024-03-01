---
title: Manipulation des critères du groupe MS Project dans Aspose.Tasks
linktitle: Critères de groupe dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment manipuler les fichiers MS Project par programme dans .NET à l'aide d'Aspose.Tasks. Récupérez des exemples étape par étape d’informations sur les groupes de tâches et les critères.
type: docs
weight: 27
url: /fr/net/tasks-project-management/group-criteria/
---
## Introduction
Aspose.Tasks for .NET est une API puissante qui facilite l'utilisation des fichiers Microsoft Project dans vos applications .NET. Que vous développiez un logiciel de gestion de projet ou que vous ayez besoin de manipuler les données du projet par programmation, Aspose.Tasks propose un ensemble complet de fonctionnalités pour répondre à vos besoins.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
### 1. Connaissance de C# et .NET Framework
La connaissance du langage de programmation C# et du .NET Framework est essentielle pour comprendre et mettre en œuvre les exemples fournis dans ce didacticiel.
### 2. Installation d'Aspose.Tasks pour .NET
 Assurez-vous que Aspose.Tasks pour .NET est installé dans votre environnement de développement. Vous pouvez télécharger la bibliothèque depuis[ici](https://releases.aspose.com/tasks/net/) et suivez les instructions d'installation fournies.
### 3. Environnement de développement intégré (IDE)
Installez un IDE tel que Visual Studio sur votre système pour écrire et exécuter du code C#.

## Importer des espaces de noms
Pour commencer, importez les espaces de noms nécessaires dans votre code C# :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Étape 1 : Charger un fichier Microsoft Project
Tout d'abord, spécifiez le chemin d'accès à votre fichier Microsoft Project :
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 Remplacer`"Your Document Directory"` avec le chemin d'accès à votre fichier de projet.
## Étape 2 : Récupérer les informations sur les groupes de tâches
Ensuite, récupérez les informations sur les groupes de tâches du projet :
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Cet extrait de code imprime le nombre total de groupes de tâches, récupère le deuxième groupe de tâches, son nom et le nombre de critères qu'il contient.
## Étape 3 : Récupérer les informations sur les critères du groupe de travail
Examinons maintenant les détails d'un critère spécifique au sein du groupe de tâches :
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Ce segment affiche diverses propriétés du critère telles que son index, son champ, les informations de regroupement, la couleur de la cellule, la couleur de la police, l'intervalle de groupe et le point de départ.
## Étape 4 : Récupérer les informations sur la police du critère
Enfin, obtenez les détails du critère liés à la police :
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
Cette étape imprime le nom de la police, la taille, le style et indique si le critère est trié par ordre croissant ou décroissant.

## Conclusion
Dans ce didacticiel, nous avons expliqué comment utiliser Aspose.Tasks pour .NET pour récupérer des informations sur les groupes de tâches et les critères à partir d'un fichier Microsoft Project. En suivant le guide étape par étape, vous pouvez travailler efficacement avec les données de projet par programmation dans vos applications .NET.
## FAQ
### Aspose.Tasks peut-il gérer des fichiers Microsoft Project volumineux ?
Aspose.Tasks est optimisé pour gérer efficacement les fichiers de projets volumineux, garantissant ainsi des performances et une fiabilité élevées.
### Aspose.Tasks est-il compatible avec toutes les versions de Microsoft Project ?
Oui, Aspose.Tasks prend en charge différentes versions de Microsoft Project, garantissant la compatibilité entre différents formats de fichiers.
### Puis-je manipuler les données du projet à l’aide d’Aspose.Tasks ?
Absolument, Aspose.Tasks fournit des fonctionnalités étendues pour manipuler les données du projet, notamment les tâches, les ressources, les calendriers, etc.
### Aspose.Tasks offre-t-il une prise en charge pour différentes plates-formes .NET ?
Oui, Aspose.Tasks prend en charge plusieurs plates-formes .NET, notamment .NET Framework, .NET Core et .NET Standard.
### Existe-t-il un forum communautaire pour Aspose.Tasks où je peux demander de l'aide ?
 Oui, vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour poser des questions, partager des connaissances et collaborer avec d'autres utilisateurs.