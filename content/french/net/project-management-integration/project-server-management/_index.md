---
title: Gestion de MS Project Server avec Aspose.Tasks
linktitle: Gestion de Project Server avec Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Débloquez une gestion transparente de MS Project Server avec Aspose.Tasks pour .NET. Automatisez les tâches du projet sans effort.
type: docs
weight: 23
url: /fr/net/project-management-integration/project-server-management/
---
## Introduction
Dans ce didacticiel, nous aborderons la gestion de MS Project Server à l'aide d'Aspose.Tasks pour .NET. Aspose.Tasks est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers Microsoft Project par programme, permettant une intégration et une manipulation transparentes des données du projet.
## Conditions préalables
Avant de nous lancer dans la gestion de MS Project Server avec Aspose.Tasks, assurez-vous d'avoir configuré les conditions préalables suivantes :
1. Microsoft Project Server : vous devez accéder à une instance de Microsoft Project Server sur laquelle vous disposez de privilèges administratifs ou au moins d'autorisations pour créer et gérer des projets.
2.  Bibliothèque Aspose.Tasks pour .NET : assurez-vous d'avoir téléchargé et installé la bibliothèque Aspose.Tasks pour .NET. Vous pouvez le télécharger depuis le[site web](https://releases.aspose.com/tasks/net/).
3. Informations d'identification : obtenez les informations d'identification nécessaires pour vous authentifier auprès de votre instance MS Project Server. Cela inclut généralement un nom d'utilisateur et un mot de passe.
## Importer des espaces de noms
Avant de commencer, assurez-vous d'avoir importé les espaces de noms requis dans votre code C# :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## Étape 1 : Configurer les informations d'authentification
Tout d'abord, vous devez configurer les informations d'authentification pour vous connecter à votre instance MS Project Server. Cela inclut l'adresse du domaine, le nom d'utilisateur et le mot de passe.
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa" ;
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## Étape 2 : Charger le projet
Ensuite, chargez le fichier MS Project que vous souhaitez gérer à l'aide d'Aspose.Tasks.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## Étape 3 : Créer un gestionnaire de serveur de projet
 Instancier un`ProjectServerManager` objet en utilisant les informations d’identification définies précédemment.
```csharp
var manager = new ProjectServerManager(credentials);
```
## Étape 4 : Définir les options d'enregistrement
Définissez les options de sauvegarde spécifiques à votre projet. Par exemple, vous pouvez définir un délai d'attente pour l'opération.
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## Étape 5 : Créer ou mettre à jour un projet
Enfin, créez ou mettez à jour le projet sur MS Project Server.
```csharp
manager.CreateNewProject(project, options);
```
Toutes nos félicitations! Vous avez géré avec succès MS Project Server à l'aide d'Aspose.Tasks pour .NET.

## Conclusion
Dans ce didacticiel, nous avons exploré comment gérer MS Project Server par programme à l'aide d'Aspose.Tasks pour .NET. Avec les étapes fournies, vous pouvez intégrer de manière transparente Aspose.Tasks dans vos applications .NET pour automatiser les tâches de gestion de projet sur MS Project Server.
## FAQ
### Q : Aspose.Tasks est-il compatible avec toutes les versions de Microsoft Project Server ?
R : Aspose.Tasks prend en charge l'intégration avec différentes versions de Microsoft Project Server, garantissant ainsi la compatibilité entre différents environnements.
### Q : Puis-je effectuer des opérations groupées sur des projets à l’aide d’Aspose.Tasks ?
R : Oui, Aspose.Tasks vous permet d'effectuer des opérations groupées telles que la création, la mise à jour et la suppression de projets sur MS Project Server.
### Q : Aspose.Tasks fournit-il une prise en charge pour la planification de projets et la gestion des ressources ?
R : Absolument, Aspose.Tasks offre une prise en charge complète des fonctionnalités de planification de projet, d'allocation de ressources et de gestion des tâches.
### Q : Est-il possible d'automatiser les tâches de reporting avec Aspose.Tasks ?
: Oui, Aspose.Tasks vous permet d'automatiser la génération de rapports personnalisés basés sur les données du projet, facilitant ainsi un suivi et une analyse efficaces du projet.
### Q : Puis-je essayer Aspose.Tasks avant de l'acheter ?
 R : Oui, vous pouvez explorer les capacités d'Aspose.Tasks en accédant à un essai gratuit depuis le[site web](https://purchase.aspose.com/temporary-license/).