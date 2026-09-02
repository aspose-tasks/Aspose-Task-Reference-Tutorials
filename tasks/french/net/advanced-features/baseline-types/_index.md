---
date: 2026-04-30
description: Apprenez à définir la ligne de base et à manipuler les lignes de base
  du projet efficacement en utilisant Aspose.Tasks pour .NET.
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Différents types de lignes de base dans Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Comment définir une ligne de base dans Aspose.Tasks – Différents types de lignes
  de base
url: /fr/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Différents types de lignes de base dans Aspose.Tasks

## Introduction

En gestion de projet, **comment définir une ligne de base** correctement peut faire la différence entre un projet qui reste sur la bonne voie et un projet qui part en vrille. Aspose.Tasks pour .NET vous fournit une API complète pour créer, mettre à jour et comparer les lignes de base, vous permettant de **suivre la progression du projet** par rapport au plan initial. Dans ce tutoriel, vous apprendrez comment définir une ligne de base, travailler avec plusieurs types de lignes de base, et utiliser les données pour analyser le **comparatif ligne de base vs planning réel** de votre projet.

## Réponses rapides
- **Qu'est-ce qu'une ligne de base ?** Une capture d'écran du planning, des coûts et des données de travail prise à un moment précis d'un projet.  
- **Combien de lignes de base Aspose.Tasks peut‑il stocker ?** Jusqu'à 11 lignes de base distinctes par projet.  
- **Pourquoi définir une ligne de base ?** Pour comparer la performance réelle au plan initial et identifier les écarts.  
- **Ai‑je besoin d'une licence pour essayer cela ?** Une version d'essai gratuite est disponible ; une licence est requise pour une utilisation en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu’est‑ce que « comment définir une ligne de base » dans Aspose.Tasks ?
Définir une ligne de base signifie appeler la méthode `SetBaseline` sur un objet `Project`. L'API vous permet de choisir parmi plusieurs valeurs `BaselineType` (Baseline, Baseline1 … Baseline10) afin de conserver des captures historiques au fur et à mesure que le projet évolue.

## Pourquoi gérer les lignes de base du projet ?
- **Mesurer les écarts :** Voir rapidement si les tâches sont en avance ou en retard par rapport au planning.  
- **Contrôle des coûts :** Comparer le coût de la ligne de base aux dépenses réelles.  
- **Rapports aux parties prenantes :** Exporter les données de la ligne de base en PDF, XLSX ou autres formats pour une communication claire.  
- **Planification de scénarios :** Stocker plusieurs lignes de base pour évaluer des plannings « what‑if ».

## Prerequisites

### 1. Familiarité avec C# et le .NET Framework
Une compréhension de base des classes C#, des méthodes et des concepts orientés objet est requise.

### 2. Installation d’Aspose.Tasks pour .NET
Assurez‑vous que la bibliothèque est ajoutée à votre projet. Vous pouvez la télécharger depuis le [site web d’Aspose.Tasks](https://releases.aspose.com/tasks/net/) ou l’installer via NuGet.

### 3. Environnement de développement intégré (IDE)
Visual Studio (ou tout IDE compatible) est recommandé pour écrire, compiler et déboguer le code C#.

## Importer les espaces de noms

Avant de commencer à travailler avec Aspose.Tasks dans notre projet C#, nous devons importer les espaces de noms nécessaires pour accéder aux classes et méthodes requises. Suivez ces étapes :

```csharp

```

Maintenant que nous avons configuré nos prérequis et importé les espaces de noms nécessaires, plongeons dans la définition de différents types de lignes de base avec Aspose.Tasks pour .NET. Nous décomposerons chaque exemple en plusieurs étapes pour plus de clarté et de facilité de compréhension.

## Comment définir une ligne de base dans Aspose.Tasks

### Étape 1 : Charger le fichier de projet
Tout d’abord, nous devons charger le fichier de projet sur lequel nous souhaitons définir la ligne de base. Cette étape consiste à initialiser un objet `Project` et à charger le fichier de projet. Voici comment procéder :

```csharp
var project = new Project("Project2.mpp");
```

### Étape 2 : Définir la ligne de base
Une fois le projet chargé, nous pouvons procéder à la définition de la ligne de base. Les lignes de base offrent une capture du planning initial du projet, servant de point de référence pour la comparaison au fur et à mesure de l’avancement du projet. Utilisez la méthode `SetBaseline` pour définir la ligne de base. Par exemple, pour définir la ligne de base pour l’ensemble du projet, utilisez l’énumération `BaselineType.Baseline` :

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### Étape 3 : Travailler avec les lignes de base du projet
Après avoir défini la ligne de base, vous pouvez travailler avec différents champs de lignes de base du projet pour analyser et suivre la progression du projet avec précision. Cette étape implique l’accès aux données de ligne de base telles que les dates de début, les dates de fin, les durées et les coûts. C’est ici que vous pouvez exploiter l’ensemble riche de fonctionnalités fourni par Aspose.Tasks pour manipuler les données de ligne de base selon vos besoins.

## Problèmes courants et solutions
- **Ligne de base non appliquée :** Assurez‑vous que le fichier de projet est enregistré après l’appel à `SetBaseline`. Utilisez `project.Save("output.mpp");` si vous devez persister les modifications.  
- **Conflit de multiples lignes de base :** Lors de la définition de plusieurs lignes de base, spécifiez le `BaselineType` correct (par ex., `Baseline1`, `Baseline2`).  
- **Incompatibilité de version :** Vérifiez que la version du DLL Aspose.Tasks correspond à l’environnement d’exécution .NET cible.

## Questions fréquemment posées

**Q : Puis‑je définir plusieurs lignes de base pour un même projet avec Aspose.Tasks pour .NET ?**  
R : Oui, Aspose.Tasks vous permet de définir jusqu’à 11 lignes de base pour un projet, offrant des capacités de suivi complètes.

**Q : Aspose.Tasks est‑il compatible avec différents formats de fichiers de projet ?**  
R : Absolument ! Aspose.Tasks prend en charge divers formats de fichiers de projet tels que MPP, XML et MPX, garantissant la compatibilité sur différentes plateformes.

**Q : Comment puis‑je visualiser les données de ligne de base dans mon projet ?**  
R : Vous pouvez utiliser Aspose.Tasks pour exporter les données du projet vers des formats populaires comme PDF ou XLSX, facilitant la visualisation et le partage des informations de ligne de base.

**Q : Aspose.Tasks offre‑t‑il un support pour l’intégration avec des outils de gestion de projet ?**  
R : Aspose.Tasks propose une documentation exhaustive et des forums de support pour aider les développeurs à intégrer sans heurts ses fonctionnalités avec les outils et plateformes de gestion de projet populaires.

**Q : Puis‑je essayer Aspose.Tasks avant de l’acheter ?**  
R : Oui, vous pouvez explorer Aspose.Tasks via un essai gratuit disponible sur le site web, vous permettant de découvrir ses capacités directement.

---

**Dernière mise à jour :** 2026-04-30  
**Testé avec :** Aspose.Tasks for .NET (latest stable release)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}