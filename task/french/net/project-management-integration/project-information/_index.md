---
title: Extraire les informations de MS Project dans Aspose.Tasks
linktitle: Extraction des informations sur le projet dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment extraire facilement des informations MS Project à l'aide d'Aspose.Tasks pour .NET. Plongez dans notre tutoriel complet.
type: docs
weight: 20
url: /fr/net/project-management-integration/project-information/
---
## Introduction
Cherchez-vous à extraire efficacement des informations des fichiers Microsoft Project à l’aide d’Aspose.Tasks pour .NET ? Dans ce didacticiel, nous vous guiderons étape par étape tout au long du processus. Mais avant d’entrer dans les détails de la mise en œuvre, assurons-nous d’abord que vous disposez de tout ce dont vous avez besoin.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
### 1. Aspose.Tasks pour .NET
 Assurez-vous d'avoir installé la bibliothèque Aspose.Tasks pour .NET. Si vous ne l'avez pas déjà fait, vous pouvez le télécharger depuis le[Aspose.Tasks pour le site Web .NET](https://releases.aspose.com/tasks/net/).
### 2. Informations d'identification pour SharePoint
Vous aurez besoin des informations d'identification pour accéder au SharePoint où sont stockés vos fichiers MS Project. Assurez-vous d'avoir les informations suivantes :
- Adresse de domaine SharePoint
- Nom d'utilisateur
- Mot de passe
## Importation d'espaces de noms
Une fois que vous avez réglé vos prérequis, il est temps d'importer les espaces de noms nécessaires dans votre projet.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Décomposons maintenant le processus d'extraction des informations MS Project en plusieurs étapes.
## Étape 1 : Fournissez les informations d'identification
Tout d’abord, vous devez fournir vos informations d’identification SharePoint pour accéder au Project Server.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa" ;
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Étape 2 : initialiser le gestionnaire de Project Server
 Ensuite, initialisez un`ProjectServerManager` instance avec les informations d’identification fournies.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Étape 3 : Récupérer la liste des projets
Vous pouvez désormais récupérer la liste des projets depuis Project Server.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Étape 4 : Imprimer les informations sur le projet
Enfin, parcourez la liste des projets et imprimez leurs informations.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment extraire des informations MS Project à l'aide d'Aspose.Tasks pour .NET. Grâce à ces connaissances, vous pouvez désormais intégrer cette fonctionnalité dans vos applications .NET de manière transparente.
## FAQ
### Q1 : Puis-je utiliser Aspose.Tasks pour .NET avec n’importe quelle version de Microsoft Project ?
R : Oui, Aspose.Tasks pour .NET prend en charge différentes versions de Microsoft Project, notamment 2003, 2007, 2010, 2013, 2016 et 2019.
### Q2 : Aspose.Tasks pour .NET est-il compatible avec les plates-formes Windows et Linux ?
R : Oui, Aspose.Tasks for .NET est compatible avec les plates-formes Windows et Linux, ce qui le rend polyvalent pour différents environnements de développement.
### Q3 : Puis-je extraire les dépendances de tâches à l’aide d’Aspose.Tasks pour .NET ?
R : Absolument ! Aspose.Tasks for .NET fournit des fonctionnalités robustes pour extraire non seulement les informations de base du projet, mais également les dépendances des tâches et d'autres détails complexes.
### Q4 : Aspose.Tasks pour .NET offre-t-il une assistance technique ?
 R : Oui, vous pouvez obtenir une assistance technique pour Aspose.Tasks for .NET via le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), où vous pouvez poser des questions et demander l'aide d'experts.
### Q5 : Puis-je essayer Aspose.Tasks pour .NET avant de l'acheter ?
 R : Certainement ! Vous pouvez bénéficier d'un essai gratuit d'Aspose.Tasks pour .NET à partir du[page des versions](https://releases.aspose.com/), vous permettant d'explorer ses fonctionnalités avant de prendre une décision d'achat.