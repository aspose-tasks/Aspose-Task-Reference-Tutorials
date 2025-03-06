---
title: Paramètres de base de données dans Aspose.Tasks
linktitle: Paramètres de base de données dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment importer des projets à partir d'une base de données Primavera à l'aide d'Aspose.Tasks pour .NET. Obtenez des conseils étape par étape dans ce didacticiel complet.
type: docs
weight: 29
url: /fr/net/calendar-scheduling/database-settings/
---
## Introduction

Aspose.Tasks for .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers Microsoft Project dans leurs applications .NET. Dans ce didacticiel, nous nous concentrerons sur l'importation de projets à partir d'une base de données Primavera à l'aide d'Aspose.Tasks.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Connaissance de base du langage de programmation C#.
- Visual Studio installé sur votre système.
-  Aspose.Tasks pour la bibliothèque .NET installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
- Accès à une base de données Primavera, ainsi que les autorisations nécessaires.

## Importer des espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires dans votre projet C#. Ces espaces de noms donnent accès aux classes et méthodes nécessaires pour travailler avec Aspose.Tasks pour .NET.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Maintenant, décomposons l'exemple de code fourni en plusieurs étapes :

## Étape 1 : Définir la chaîne de connexion

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 Dans cette étape, nous définissons la chaîne de connexion pour se connecter à la base de données Primavera. Assurez-vous de remplacer`DataDir` avec le répertoire où se trouve votre fichier de base de données.

## Étape 2 : Créer les paramètres de la base de données

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 Ici, nous créons une instance de`PrimaveraDbSettings` classe, en passant la chaîne de connexion et l'ID du projet comme paramètres. Ajustez l’ID du projet selon vos besoins.

## Étape 3 : Définir le nom invariant du fournisseur

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Spécifiez le nom invariant du fournisseur. Dans cet exemple, nous utilisons SQLite, mais vous pouvez le modifier en fonction de votre fournisseur de base de données.

## Étape 4 : Charger le projet

```csharp
var project = new Project(settings);
```

 Créer un nouveau`Project` objet, en passant les paramètres de la base de données en tant que paramètre.

## Étape 5 : Enregistrer le projet

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Enfin, enregistrez le projet à l'emplacement souhaité avec le format de fichier spécifié.

## Conclusion

Dans ce didacticiel, nous avons appris à importer des projets à partir d'une base de données Primavera à l'aide d'Aspose.Tasks pour .NET. En suivant les étapes fournies, vous pouvez intégrer de manière transparente la fonctionnalité d'importation de projet dans vos applications .NET.

## FAQ

### Q1 : Puis-je importer des projets de différents fournisseurs de bases de données à l’aide d’Aspose.Tasks pour .NET ?

A1 : Oui, vous pouvez importer des projets de différents fournisseurs de bases de données en ajustant la chaîne de connexion et le nom invariant du fournisseur en conséquence.

### Q2 : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour .NET ?

 A2 : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/).

### Q3 : Où puis-je trouver la documentation pour Aspose.Tasks pour .NET ?

 A3 : Vous pouvez trouver la documentation[ici](https://reference.aspose.com/tasks/net/).

### Q4 : Comment puis-je obtenir de l'assistance pour Aspose.Tasks pour .NET ?

 A4 : Vous pouvez obtenir de l'aide auprès du forum de la communauté Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).

### Q5 : Ai-je besoin d’une licence temporaire pour utiliser Aspose.Tasks pour .NET ?

 A5 : Si vous souhaitez évaluer toutes les fonctionnalités de la bibliothèque, vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/).