---
title: Gestion des informations d'identification MS Project Server dans Aspose.Tasks
linktitle: Gestion des informations d'identification de Project Server dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer les informations d'identification MS Project Server de manière transparente avec Aspose.Tasks pour .NET. Améliorer l’efficacité de la gestion de projet.
weight: 22
url: /fr/net/project-management-integration/project-server-credentials/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestion des informations d'identification MS Project Server dans Aspose.Tasks

## Introduction
Dans le domaine de la gestion de projet, une coordination efficace et une communication transparente sont essentielles à la réussite de l’exécution du projet. Aspose.Tasks for .NET fournit une solution complète pour gérer les informations d'identification de Microsoft Project Server, permettant aux utilisateurs d'accéder et de manipuler en toute sécurité les données du projet. Ce didacticiel explore le processus de gestion des informations d'identification MS Project Server à l'aide d'Aspose.Tasks pour .NET, guidant les utilisateurs à chaque étape pour garantir une expérience fluide.
## Conditions préalables
Avant de vous lancer dans la gestion des informations d'identification MS Project Server avec Aspose.Tasks pour .NET, assurez-vous que les conditions préalables suivantes sont remplies :
### 1. Installation d'Aspose.Tasks pour .NET
 Pour commencer, téléchargez et installez Aspose.Tasks for .NET à partir du[lien de téléchargement](https://releases.aspose.com/tasks/net/). Suivez les instructions d'installation pour intégrer la bibliothèque dans votre environnement .NET de manière transparente.
### 2. Accéder aux informations d'identification
Rassemblez les informations d'identification nécessaires pour accéder au serveur MS Project. Cela inclut l'adresse de domaine SharePoint, le nom d'utilisateur et le mot de passe associés au serveur Project.

## Importer des espaces de noms
Dans votre projet .NET, importez les espaces de noms requis pour utiliser efficacement les fonctionnalités fournies par Aspose.Tasks pour .NET.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## Étape 1 : Définir le chemin du répertoire de documents
```csharp
String DataDir = "Your Document Directory";
```
## Étape 2 : Définir l'adresse de domaine SharePoint, le nom d'utilisateur et le mot de passe
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa" ;
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## Étape 3 : Créer les informations d'identification de Project Server
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Étape 4 : Charger le fichier de projet
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Étape 5 : initialiser le gestionnaire de Project Server
```csharp
var manager = new ProjectServerManager(credentials);
```
## Étape 6 : Créer un nouveau projet
```csharp
manager.CreateNewProject(newProject);
```
## Étape 7 : Récupérer la liste des projets
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Étape 8 : Parcourir la liste des projets
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Conclusion
La gestion efficace des informations d'identification MS Project Server est primordiale pour une gestion de projet rationalisée. Aspose.Tasks for .NET simplifie ce processus en fournissant un ensemble robuste de fonctionnalités. En suivant le guide étape par étape décrit dans ce didacticiel, les utilisateurs peuvent intégrer de manière transparente Aspose.Tasks for .NET dans leurs projets, garantissant ainsi un accès et une manipulation sécurisés des données du projet.
## FAQ
### Q : Aspose.Tasks pour .NET est-il compatible avec toutes les versions de Microsoft Project Server ?
R : Aspose.Tasks for .NET est conçu pour être compatible avec différentes versions de Microsoft Project Server, garantissant ainsi polyvalence et flexibilité aux utilisateurs.
### Q : Puis-je intégrer Aspose.Tasks pour .NET dans mon projet .NET existant ?
R : Oui, Aspose.Tasks pour .NET peut être intégré de manière transparente aux projets .NET existants, facilitant ainsi des capacités de gestion de projet efficaces.
### Q : Aspose.Tasks pour .NET fournit-il une prise en charge pour accéder aux ressources du projet ?
: Absolument, Aspose.Tasks pour .NET offre une prise en charge complète pour l'accès et la manipulation des ressources du projet, améliorant ainsi l'efficacité de la gestion de projet.
### Q : Existe-t-il des options de licence disponibles pour Aspose.Tasks pour .NET ?
R : Oui, Aspose.Tasks pour .NET propose des options de licence flexibles, notamment des licences temporaires à des fins d'essai et des licences complètes pour un usage commercial.
### Q : Où puis-je demander de l'aide ou du support pour Aspose.Tasks pour .NET ?
 R : Pour toute demande de renseignements ou d'assistance concernant Aspose.Tasks pour .NET, vous pouvez visiter le forum d'assistance à l'adresse[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Code source complet
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
