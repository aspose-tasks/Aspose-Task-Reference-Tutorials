---
title: Enregistrez les fichiers MS Project en tant que modèles avec Aspose.Tasks
linktitle: Enregistrer les options de modèle pour Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment enregistrer des fichiers Microsoft Project en tant que modèles à l'aide d'Aspose.Tasks pour .NET. Personnalisez les paramètres du modèle pour une gestion de projet rationalisée.
weight: 18
url: /fr/net/saving-options/save-template-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrez les fichiers MS Project en tant que modèles avec Aspose.Tasks

## Introduction
Dans ce didacticiel, nous allons parcourir le processus d'enregistrement d'un modèle à l'aide d'Aspose.Tasks pour .NET. Les modèles sont utiles pour normaliser les structures et les paramètres du projet en vue d'une utilisation future. Nous montrerons comment enregistrer un projet en tant que modèle, en ajustant ses propriétés en cours de route.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1.  Bibliothèque Aspose.Tasks pour .NET : assurez-vous que la bibliothèque Aspose.Tasks pour .NET est installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
2. Connaissance de la programmation C# : Une connaissance de base de la programmation C# est requise pour comprendre et mettre en œuvre les extraits de code fournis.
3. Fichier Microsoft Project : préparez un fichier Microsoft Project (format MPP) que vous souhaitez enregistrer en tant que modèle.

## Importer des espaces de noms
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Étape 1 : Charger le projet
Tout d’abord, nous devons charger le fichier Microsoft Project (.mpp) que nous souhaitons enregistrer comme modèle.
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Étape 2 : obtenir des informations sur le fichier du projet
Récupérez des informations sur le fichier de projet chargé, telles que son format.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Étape 3 : Configurer les options d'enregistrement du modèle
Créez des options d'enregistrement de modèle et configurez ses propriétés en fonction de vos besoins. Ces options vous permettent de personnaliser les données qui doivent être supprimées du modèle.
```csharp
var options = new SaveTemplateOptions
{
	// Supprimez tous les coûts fixes du modèle de projet
	RemoveFixedCosts = true,
	// Supprimer toutes les valeurs réelles du modèle de projet
	RemoveActualValues = true,
	// Supprimer les taux de ressources du modèle de projet
	RemoveResourceRates = true,
	// Supprimez toutes les valeurs de référence du modèle de projet
	RemoveBaselineValues = true
};
```
## Étape 4 : Enregistrer le projet en tant que modèle
Enregistrez le projet en tant que modèle avec les options spécifiées.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Étape 5 : Obtenir des informations sur le fichier modèle
Récupérez des informations sur le fichier modèle enregistré, telles que son format.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Toutes nos félicitations! Vous avez enregistré avec succès un modèle à l'aide d'Aspose.Tasks pour .NET, en personnalisant ses propriétés selon vos besoins.

## Conclusion
Dans ce didacticiel, nous avons expliqué comment enregistrer un fichier Microsoft Project en tant que modèle à l'aide d'Aspose.Tasks pour .NET. Les modèles sont précieux pour normaliser les structures et les paramètres du projet, rationalisant ainsi les créations futures de projets.
## FAQ
### Q : Puis-je personnaliser les données à supprimer du modèle ?
R : Oui, vous pouvez configurer les options d'enregistrement du modèle pour supprimer des données spécifiques telles que les coûts fixes, les valeurs réelles, les taux de ressources et les valeurs de référence.
### Q : Aspose.Tasks pour .NET est-il compatible avec toutes les versions de Microsoft Project ?
R : Aspose.Tasks pour .NET offre une compatibilité étendue avec différentes versions de Microsoft Project, garantissant une intégration et des fonctionnalités transparentes.
### Q : Puis-je appliquer des modèles à des projets existants ?
R : Oui, vous pouvez appliquer des modèles à des projets existants en chargeant le fichier modèle et en le fusionnant avec votre projet actuel si nécessaire.
### Q : Aspose.Tasks pour .NET prend-il en charge le développement multiplateforme ?
R : Aspose.Tasks for .NET est principalement conçu pour les applications de framework .NET exécutées sur les plates-formes Windows.
### Q : Le support technique est-il disponible pour Aspose.Tasks pour .NET ?
 R : Oui, vous pouvez demander une assistance technique et des conseils à la communauté Aspose.Tasks.[forums](https://forum.aspose.com/c/tasks/15)ou contactez directement leur équipe d’assistance.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
