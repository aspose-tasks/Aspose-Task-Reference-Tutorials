---
date: 2026-03-14
description: Apprenez comment spécifier le schéma de base de données d’une base de
  données Microsoft Project à l’aide d’Aspose.Tasks, et comment importer les données
  de projet dans des applications .NET.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Spécifier le schéma de la base de données du projet avec Aspose.Tasks
url: /fr/net/advanced-concepts/msp-database-settings/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Paramètres pour la base de données Microsoft Project dans Aspose.Tasks

## Introduction

Si vous travaillez avec des bases de données Microsoft Project dans vos applications .NET en utilisant Aspose.Tasks, vous devrez **spécifier le schéma de la base de données** et configurer les paramètres nécessaires pour **importer les données du projet** de manière fluide. Ce tutoriel vous guidera à travers le processus étape par étape, en vous montrant **comment configurer les détails de connexion**, **créer une chaîne de connexion .NET**, et enfin **enregistrer le projet au format MPP**.

## Quick Answers
- **Quel est l'objectif principal ?** Spécifier le schéma de la base de données et importer une base de données Project dans une application .NET.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks pour .NET.  
- **Comment se connecter à Project Server ?** En construisant une chaîne de connexion SQL appropriée et en utilisant `MspDbSettings`.  
- **Quel format de fichier est produit ?** Un fichier MPP enregistré avec `SaveFileFormat.Mpp`.  
- **Puis-je changer le nom du schéma ?** Oui, définissez la propriété `Schema` sur `MspDbSettings`.

## How to specify database schema for Project DB

Comprendre pourquoi vous pourriez avoir besoin de **spécifier le schéma de la base de données** est essentiel. Dans de nombreux environnements d'entreprise, la base de données Project Server réside sous un schéma personnalisé (par ex., `dbo`, `psdata`). En définissant explicitement le schéma, vous assurez qu'Aspose.Tasks interroge les bonnes tables, évitant ainsi les erreurs d'exécution et garantissant une importation précise des données.

## Prerequisites

Avant de commencer, assurez-vous de disposer de ce qui suit :

1. Aspose.Tasks pour .NET : téléchargez et installez la bibliothèque Aspose.Tasks depuis [here](https://releases.aspose.com/tasks/net/).  
2. Accès à une base de données Microsoft Project : vous devez disposer d'un accès à une base de données Microsoft Project pour en importer les données.  

## Import Namespaces

Tout d'abord, assurez-vous d'importer les espaces de noms nécessaires dans votre projet :

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Step 1: Create Connection String

### Étape 1 : Créer la chaîne de connexion

Construisez la chaîne de connexion à votre base de données Microsoft Project. C'est ici que vous **créez une chaîne de connexion .NET** et définissez également comment **se connecter à Project Server**.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **Astuce :** Vérifiez à nouveau les valeurs `DataSource` et `InitialCatalog` ; elles doivent correspondre à l'adresse de votre serveur et au nom de la base de données publiée.

## Step 2: Configure MspDbSettings

### Étape 2 : Configurer MspDbSettings

Créez une instance de `MspDbSettings`, transmettez la chaîne de connexion, et **spécifiez le schéma de la base de données** en définissant la propriété `Schema`. Cela indique à Aspose.Tasks quel schéma interroger.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Ici, nous fournissons également le GUID du projet qui identifie le projet spécifique que vous souhaitez charger.

## Step 3: Load Project Data

### Étape 3 : Charger les données du projet

Instanciez un objet `Project` en utilisant les paramètres configurés. Cette étape importe effectivement **les données du projet** depuis la base de données vers un objet .NET.

```csharp
var project = new Project(settings);
```

## Step 4: Save Project Data

### Étape 4 : Enregistrer les données du projet

Enfin, persistez le projet chargé dans un fichier MPP sur le disque. Cela démontre **l'enregistrement du projet au format MPP** à l'aide de l'API Aspose.Tasks.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Après l'exécution du code, vous trouverez le fichier `ImportProjectDataFromDatabase_out.mpp` dans le répertoire de sortie, prêt à être ouvert dans Microsoft Project.

## Conclusion

Dans ce tutoriel, vous avez appris comment **spécifier le schéma de la base de données** pour une base de données Microsoft Project, **configurer la connexion**, **importer les données du projet**, et **enregistrer le projet au format MPP** en utilisant Aspose.Tasks pour .NET. Ces étapes permettent une intégration fluide des données de Project Server dans vos applications personnalisées, vous aidant à créer des solutions de gestion de projet robustes.

## Frequently Asked Questions

### Q1 : Puis‑je utiliser Aspose.Tasks avec différentes versions de bases de données Microsoft Project ?
**R1 :** Oui, Aspose.Tasks prend en charge diverses versions de bases de données Microsoft Project, offrant une flexibilité d'intégration.

### Q2 : Comment dépanner les problèmes de connexion à la base de données ?
**R2 :** Assurez‑vous que votre chaîne de connexion est correctement configurée avec les informations d'identification et les détails de la base de données appropriés. Vous pouvez également consulter la documentation ou demander de l'aide sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q3 : Existe‑t‑il une version d'essai disponible pour Aspose.Tasks ?
**R3 :** Oui, vous pouvez accéder à une version d'essai gratuite depuis [here](https://releases.aspose.com/).

### Q4 : Puis‑je personnaliser le schéma pour l'interaction avec la base de données ?
**R4 :** Oui, vous pouvez spécifier le schéma pour l'objet `MspDbSettings` en fonction de la structure de votre base de données.

### Q5 : Où puis‑je trouver une documentation plus détaillée sur l'utilisation d'Aspose.Tasks ?
**R5 :** Vous pouvez explorer la documentation complète [here](https://reference.aspose.com/tasks/net/) pour des informations détaillées sur les fonctionnalités d'Aspose.Tasks.

**Q : Cette approche fonctionne‑t‑elle avec les bases de données Azure SQL ?**  
**R :** Absolument. Il suffit d’ajuster le `DataSource` à votre nom de serveur Azure et de vous assurer que les paramètres TLS/SSL sont activés.

**Q : Comment gérer de grandes bases de données Project sans dépasser le délai d’attente ?**  
**R :** Augmentez la valeur `ConnectTimeout` dans la chaîne de connexion et envisagez de charger les projets par lots si nécessaire.

---

**Dernière mise à jour :** 2026-03-14  
**Testé avec :** Aspose.Tasks 24.12 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}