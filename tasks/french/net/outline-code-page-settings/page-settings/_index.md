---
title: Configurer les paramètres de la page MS Project avec Aspose.Tasks
linktitle: Configuration des paramètres de page dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment configurer les paramètres de la page MS Project à l'aide d'Aspose.Tasks pour .NET. Personnalisez l'orientation, la taille et bien plus encore en quelques étapes simples.
type: docs
weight: 20
url: /fr/net/outline-code-page-settings/page-settings/
---
## Introduction
Dans ce didacticiel, nous passerons en revue le processus de configuration des paramètres de page Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Aspose.Tasks est une API puissante qui permet aux développeurs de manipuler les fichiers Microsoft Project par programme.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1.  Aspose.Tasks pour .NET : assurez-vous d'avoir installé Aspose.Tasks pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
2. Environnement de développement : disposez d'un environnement de développement configuré avec Visual Studio ou tout autre IDE préféré pour le développement .NET.

## Importation d'espaces de noms
Pour commencer, vous devez importer les espaces de noms nécessaires dans votre projet. Ces espaces de noms donnent accès aux classes et méthodes Aspose.Tasks requises pour manipuler les fichiers MS Project.
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Étape 1 : Charger le fichier de projet
Tout d’abord, vous devez charger le fichier MS Project pour lequel vous souhaitez configurer les paramètres de page.
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## Étape 2 : accéder aux paramètres de la page
Ensuite, vous accéderez aux paramètres de page du fichier de projet.
```csharp
// Obtenez les paramètres
var settings = project.DefaultView.PageInfo.PageSettings;
```
## Étape 3 : configurer les paramètres de la page
Maintenant, configurons diverses propriétés des paramètres de la page en fonction de vos besoins.
```csharp
// Définir l'orientation de la page sur portrait
settings.IsPortrait = true;
// Définir le nombre de pages en largeur à imprimer
settings.PagesInWidth = 5;
// Définir le nombre de pages en hauteur à imprimer
settings.PagesInHeight = 7;
// Définir le pourcentage de taille normale pour ajuster l'impression à
settings.PercentOfNormalSize = 200;
// Définir le format du papier
settings.PaperSize = PrinterPaperSize.PaperB4;
// Définir le numéro de la première page pour l'impression
settings.FirstPageNumber = 3;
```
## Étape 4 : Enregistrez le fichier de projet
Enfin, enregistrez le fichier de projet avec les paramètres de page mis à jour.
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## Conclusion
Dans ce didacticiel, nous avons appris à configurer les paramètres de la page Microsoft Project à l'aide d'Aspose.Tasks pour .NET. En suivant ces étapes, vous pouvez facilement personnaliser l'orientation, la taille et d'autres options d'impression de la page en fonction de vos besoins.

## FAQ
### Q : Puis-je configurer les paramètres de page pour plusieurs fichiers MS Project simultanément ?
R : Oui, vous pouvez parcourir plusieurs fichiers de projet et appliquer les mêmes paramètres de page à chacun.
### Q : Est-il possible de rétablir les paramètres de page par défaut ?
R : Absolument, vous pouvez simplement omettre les étapes de configuration ou réinitialiser les paramètres à leurs valeurs par défaut.
### Q : Existe-t-il des limitations concernant les formats de papier pris en charge ?
R : Aspose.Tasks prend en charge une large gamme de formats de papier, y compris les formats standard et personnalisés.
### Q : Puis-je automatiser le processus de configuration des paramètres de page ?
R : Vous pouvez certainement intégrer cette fonctionnalité dans le flux de travail de votre application pour automatiser la configuration des paramètres de page.
### Q : Aspose.Tasks prend-il en charge différents formats de fichiers autres que .mpp ?
R : Oui, Aspose.Tasks prend en charge divers formats de fichiers tels que XML, MPT et HTML, entre autres.