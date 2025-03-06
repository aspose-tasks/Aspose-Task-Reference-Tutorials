---
title: Options d'enregistrement du serveur MS Project pour Aspose.Tasks
linktitle: Options d'enregistrement de Project Server pour Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment enregistrer les options Microsoft Project pour Aspose.Tasks à l’aide de l’intégration de Project Server. Améliorez vos flux de travail de gestion de projet.
weight: 16
url: /fr/net/saving-options/project-server-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Options d'enregistrement du serveur MS Project pour Aspose.Tasks

## Introduction
Dans ce didacticiel, nous aborderons l'enregistrement des options de Microsoft Project pour Aspose.Tasks à l'aide de Project Server. Aspose.Tasks est une puissante API .NET qui permet aux développeurs de travailler avec des fichiers Microsoft Project par programme. En tirant parti des capacités de Project Server, nous pouvons intégrer de manière transparente Aspose.Tasks dans nos flux de travail de gestion de projet. Ce tutoriel vous guidera étape par étape tout au long du processus.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1.  Aspose.Tasks pour .NET : installez Aspose.Tasks pour .NET à partir du[lien de téléchargement](https://releases.aspose.com/tasks/net/).
   
2. Accès à Project Server : vous aurez besoin des informations d'identification d'accès et de l'URL de votre instance de Project Server. Si vous n'en avez pas, vous pouvez obtenir un essai gratuit auprès de[ici](https://releases.aspose.com/).
3. Fichier Microsoft Project : préparez le fichier Microsoft Project (.mpp) que vous souhaitez enregistrer à l'aide d'Aspose.Tasks.

## Importer des espaces de noms
Tout d'abord, vous devez importer les espaces de noms nécessaires dans votre projet :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Étape 1 : initialiser le projet et les informations d'identification
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Assurez-vous de remplacer`"Your Document Directory"`, `URL`, `Domain`, `UserName` , et`Password` avec vos valeurs réelles.
## Étape 2 : Créer un gestionnaire de serveur de projet
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Étape 3 : Définir les options d'enregistrement
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Ajuste le`ProjectGuid`, `ProjectName`, `Timeout` , et`PollingInterval` selon vos exigences.
## Étape 4 : Enregistrer le projet sur le serveur
```csharp
manager.CreateNewProject(project, options);
```
Cela enregistrera le projet sur Project Server avec les options spécifiées.

## Conclusion
Dans ce didacticiel, nous avons appris à enregistrer les options de Microsoft Project pour Aspose.Tasks à l'aide de l'intégration de Project Server. En suivant ces étapes, vous pouvez intégrer de manière transparente Aspose.Tasks dans vos flux de travail de gestion de projet, améliorant ainsi l'efficacité et la productivité.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks avec différentes versions de Microsoft Project ?
: Oui, Aspose.Tasks prend en charge différentes versions de Microsoft Project, garantissant ainsi la compatibilité entre différents environnements.
### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks ?
 R : Oui, vous pouvez obtenir une version d'essai gratuite d'Aspose.Tasks à partir de[ici](https://releases.aspose.com/).
### Q : Aspose.Tasks prend-il en charge le multithreading ?
R : Oui, Aspose.Tasks est conçu pour être thread-safe, permettant un accès simultané aux données du projet.
### Q : Puis-je personnaliser les options d'enregistrement lors de l'utilisation de l'intégration de Project Server ?
R : Oui, vous pouvez personnaliser les options de sauvegarde telles que le nom du projet, le délai d'expiration et l'intervalle d'interrogation en fonction de vos besoins.
### Q : Où puis-je trouver de l'aide pour Aspose.Tasks ?
 R : Vous pouvez trouver du soutien et de l'assistance sur le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
