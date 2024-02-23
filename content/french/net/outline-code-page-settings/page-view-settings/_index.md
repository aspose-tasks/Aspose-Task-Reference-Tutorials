---
title: Personnaliser les paramètres d'affichage de la page MS Project dans Aspose.Tasks
linktitle: Configurer les paramètres d'affichage de la page dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment configurer les paramètres d'affichage des pages dans Aspose.Tasks pour .NET afin d'adapter le format d'impression de vos documents Microsoft Project.
type: docs
weight: 21
url: /fr/net/outline-code-page-settings/page-view-settings/
---
## Introduction
Microsoft Project est un outil puissant de gestion de projet, mais vous devez parfois personnaliser la façon dont votre projet est affiché et imprimé. Avec Aspose.Tasks pour .NET, vous pouvez facilement configurer les paramètres d'affichage des pages pour répondre à vos besoins spécifiques. Dans ce didacticiel, nous vous guiderons étape par étape tout au long du processus.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1.  Aspose.Tasks pour .NET : assurez-vous d'avoir téléchargé et installé la bibliothèque Aspose.Tasks pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
2. Fichier Microsoft Project : préparez un fichier Microsoft Project pour lequel vous souhaitez configurer les paramètres d'affichage des pages.

## Importer des espaces de noms
Tout d’abord, vous devez importer les espaces de noms nécessaires pour travailler avec Aspose.Tasks dans votre projet .NET.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Étape 1 : Charger le fichier de projet
 Commencez par charger votre fichier Microsoft Project dans une instance du`Project` classe.
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Étape 2 : Définir le nombre de premières colonnes
Spécifiez le nombre de premières colonnes à imprimer sur toutes les pages.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## Étape 3 : Imprimer les notes
Choisissez si vous souhaitez imprimer des notes avec le projet.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Étape 4 : Ajuster l'échelle de temps à la fin de la page
Décidez si l'échelle de temps doit être ajustée à la fin d'une page lors de l'impression.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Étape 5 : Imprimer toutes les colonnes de la feuille
Spécifiez s'il faut imprimer toutes les colonnes de feuille d'une vue.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Étape 6 : Imprimer des pages vierges
Choisissez d'imprimer ou non les pages vierges d'une vue.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Étape 7 : Imprimer les premières colonnes sur toutes les pages
Définissez s'il faut imprimer un nombre spécifié de premières colonnes sur toutes les pages.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Étape 8 : Enregistrez le projet avec les paramètres configurés
Enfin, enregistrez le projet avec les paramètres d'affichage de page configurés, en spécifiant le format de sortie, tel que PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## Conclusion
La configuration des paramètres d'affichage des pages Microsoft Project dans Aspose.Tasks pour .NET est simple et vous permet d'adapter le format d'impression à vos besoins exacts. En suivant les étapes décrites dans ce didacticiel, vous pouvez vous assurer que les documents de votre projet sont présentés exactement comme requis.
## FAQ
### Q : Puis-je configurer les paramètres d'affichage des pages pour d'autres formats de fichiers que le PDF ?
R : Oui, Aspose.Tasks prend en charge différents formats de fichiers pour l'enregistrement de projets, notamment XLSX, MPP et HTML.
### Q : Y a-t-il des limites quant au nombre de colonnes que je peux imprimer ?
R : Aspose.Tasks vous permet de personnaliser le nombre de colonnes à imprimer en fonction de vos besoins.
### Q : Puis-je appliquer différents paramètres d'affichage de page pour différents projets ?
R : Oui, vous pouvez ajuster les paramètres d'affichage des pages indépendamment pour chaque fichier de projet avec lequel vous travaillez.
### Q : Aspose.Tasks est-il compatible avec toutes les versions de Microsoft Project ?
R : Aspose.Tasks offre une compatibilité avec Microsoft Project 2003 et les versions ultérieures.
### Q : Où puis-je trouver une assistance ou un support supplémentaire pour Aspose.Tasks ?
 R : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)pour toute demande de renseignements ou problème que vous rencontrez lors de l’utilisation.