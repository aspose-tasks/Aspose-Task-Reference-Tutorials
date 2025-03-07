---
title: Image Enregistrer les options de MS Project pour Aspose.Tasks
linktitle: Options d'enregistrement d'image pour Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment enregistrer les options MS Project sous forme d'images à l'aide d'Aspose.Tasks pour .NET. Suivez notre guide étape par étape pour une intégration transparente.
weight: 11
url: /fr/net/saving-options/image-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Image Enregistrer les options de MS Project pour Aspose.Tasks


## Introduction
Dans le monde du développement de logiciels, gérer efficacement les tâches du projet est crucial pour une gestion de projet réussie. Aspose.Tasks for .NET offre une solution puissante aux développeurs travaillant avec des fichiers Microsoft Project, leur permettant de manipuler, convertir et gérer les tâches de projet de manière transparente au sein de leurs applications .NET.
## Conditions préalables
Avant de vous lancer dans l'utilisation d'Aspose.Tasks pour .NET pour enregistrer les options de MS Project sous forme d'images, assurez-vous d'avoir les conditions préalables suivantes en place :
### 1. Installez Aspose.Tasks pour .NET
Pour commencer, vous devez avoir Aspose.Tasks pour .NET installé dans votre environnement de développement. Vous pouvez télécharger la bibliothèque à partir du[site web](https://releases.aspose.com/tasks/net/) et suivez les instructions d'installation fournies.
### 2. Obtenez une licence (facultatif)
 Bien qu'Aspose.Tasks pour .NET puisse être utilisé sans licence en mode d'évaluation, l'obtention d'une licence est recommandée pour bénéficier de toutes les fonctionnalités et pour supprimer les limitations d'évaluation. Vous pouvez acquérir une licence auprès du[page d'achat](https://purchase.aspose.com/buy) ou optez pour un[permis temporaire](https://purchase.aspose.com/temporary-license/) à des fins de tests.
### 3. Connaissance de base du développement C# et .NET
Une compréhension fondamentale du langage de programmation C# et du framework .NET est nécessaire pour suivre les exemples et intégrer efficacement les fonctionnalités Aspose.Tasks dans vos applications.
## Importer des espaces de noms
Avant de commencer à enregistrer les options de MS Project sous forme d'images à l'aide d'Aspose.Tasks pour .NET, assurons-nous d'importer les espaces de noms nécessaires dans notre projet C# :
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Étape 1 : Configurer le chemin du répertoire de documents
Assurez-vous d'avoir un répertoire désigné pour vos documents et définissez le chemin en conséquence :
```csharp
String DataDir = "Your Document Directory";
```
## Étape 2 : Chargez le fichier MS Project
 Initialiser un nouveau`Project` objet en chargeant le fichier MS Project :
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Étape 3 : Définir les options d'enregistrement de l'image
 Créer une instance de`ImageSaveOptions`et précisez les paramètres souhaités :
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## Étape 4 : Spécifiez les pages à enregistrer
Si nécessaire, précisez les pages à enregistrer. Dans cet exemple, nous ajoutons la page 2 :
```csharp
options.Pages.Add(2);
```
## Étape 5 : Enregistrez l'image
Enfin, enregistrez les pages sélectionnées sous forme d'image avec les options spécifiées :
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## Conclusion
Aspose.Tasks for .NET simplifie le processus de travail avec les fichiers MS Project, permettant aux développeurs de manipuler sans effort les tâches du projet. En suivant les étapes décrites dans ce didacticiel, vous pouvez enregistrer efficacement les options de MS Project sous forme d'images dans vos applications .NET.
## FAQ
### Q1 : Puis-je utiliser Aspose.Tasks pour .NET sans licence ?
R : Oui, vous pouvez utiliser Aspose.Tasks pour .NET sans licence en mode évaluation. Cependant, il est recommandé d'obtenir une licence pour bénéficier de toutes les fonctionnalités et de supprimer les limitations d'évaluation.
### Q2 : Comment puis-je obtenir une licence temporaire pour tester ?
 R : Vous pouvez obtenir une licence temporaire à des fins de test auprès du[page de licence temporaire](https://purchase.aspose.com/temporary-license/).
### Q3 : Aspose.Tasks pour .NET est-il compatible avec d'autres frameworks .NET ?
: Oui, Aspose.Tasks pour .NET est compatible avec divers frameworks .NET, notamment .NET Core et .NET Standard.
### Q4 : Puis-je personnaliser davantage les options d’enregistrement des images ?
R : Oui, vous pouvez personnaliser les options d'enregistrement des images en fonction de vos besoins spécifiques, telles que l'ajustement de la taille de la page, de la résolution ou du format de sortie.
### Q5 : Où puis-je trouver de l'assistance pour Aspose.Tasks pour .NET ?
 R : Vous pouvez trouver du support et de l'assistance pour Aspose.Tasks for .NET sur le[forum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
