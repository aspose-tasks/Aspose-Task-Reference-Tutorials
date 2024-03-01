---
title: Enregistrement de fichiers MS Project dans différents formats dans Aspose.Tasks
linktitle: Enregistrement de fichiers dans différents formats dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment enregistrer des fichiers MS Project dans différents formats à l'aide d'Aspose.Tasks pour .NET. Des étapes simples pour une gestion de projet efficace.
type: docs
weight: 17
url: /fr/net/rate-recurring-tasks/save-file-formats/
---
## Introduction
Dans ce didacticiel, nous verrons comment enregistrer des fichiers Microsoft Project dans différents formats à l'aide d'Aspose.Tasks pour .NET. Aspose.Tasks est une API puissante qui permet aux développeurs de manipuler et de gérer les fichiers de projet par programme.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1.  Aspose.Tasks pour .NET : téléchargez et installez Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
2. Environnement de développement : configurez un environnement de développement .NET, tel que Visual Studio.
3. Compréhension de base de C# : Une connaissance du langage de programmation C# sera bénéfique.

## Importer des espaces de noms
Assurez-vous d'importer les espaces de noms nécessaires au début de votre fichier C# :
```csharp

using Aspose.Tasks.Saving;
```
## Étape 1 : Créer un objet de projet
Tout d’abord, créez un objet Project et chargez votre fichier Microsoft Project.
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Étape 2 : Enregistrer le projet au format CSV
Maintenant, sauvegardons le projet au format CSV. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Étape 3 : Explorez d’autres formats
 Aspose.Tasks prend en charge divers formats d'enregistrement des fichiers de projet, tels que XML, PDF, XLSX, etc. Vous pouvez explorer ces formats en changeant simplement le`SaveFileFormat` paramètre dans le`Save` méthode.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
En suivant ces étapes, vous pouvez facilement enregistrer des fichiers Microsoft Project dans différents formats à l'aide d'Aspose.Tasks pour .NET.

## Conclusion
Dans ce didacticiel, nous avons appris à enregistrer des fichiers MS Project dans différents formats à l'aide d'Aspose.Tasks pour .NET. Aspose.Tasks simplifie le processus de manipulation des fichiers de projet par programmation, offrant flexibilité et efficacité aux développeurs.
## FAQ
### Q : Aspose.Tasks est-il compatible avec toutes les versions de Microsoft Project ?
R : Aspose.Tasks prend en charge les formats Microsoft Project 2003 XML, Microsoft Project 2007 MPP et Microsoft Project 2010 MPP.
### Q : Puis-je essayer Aspose.Tasks avant d'acheter ?
 R : Oui, vous pouvez télécharger un essai gratuit à partir de[ici](https://releases.aspose.com/).
### Q : Comment puis-je obtenir de l'aide pour Aspose.Tasks ?
R : Vous pouvez obtenir de l'aide sur le forum de la communauté Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).
### Q : Des licences temporaires sont-elles disponibles pour Aspose.Tasks ?
 R : Oui, des licences temporaires sont disponibles à des fins d'évaluation. Vous pouvez en obtenir un[ici](https://purchase.aspose.com/temporary-license/).
### Q : Quel est le prix d’Aspose.Tasks ?
 R : Les informations sur les prix peuvent être trouvées sur la page d'achat d'Aspose.Tasks.[ici](https://purchase.aspose.com/buy).