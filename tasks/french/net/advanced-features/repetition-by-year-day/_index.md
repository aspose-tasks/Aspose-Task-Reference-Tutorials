---
date: 2026-04-03
description: Apprenez la planification des tâches de gestion de projet et comment
  ajouter des tâches récurrentes avec Aspose.Tasks pour .NET, y compris l’enregistrement
  du projet au format MPP.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Répétition par jour de l'année dans Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Planification des tâches de gestion de projet avec répétition annuelle dans
  Aspose.Tasks
url: /fr/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Planification des tâches de gestion de projet avec répétition annuelle par jour dans Aspose.Tasks

## Introduction

Une **planification des tâches de gestion de projet** efficace est la pierre angulaire de tout projet réussi. Lorsque les tâches se répètent chaque année — comme les audits annuels, les fenêtres de maintenance ou les revues saisonnières — gérer ces récurrences manuellement peut entraîner des erreurs et prendre beaucoup de temps. Aspose.Tasks pour .NET simplifie cela en vous permettant de définir programmatiquement des modèles de jour de l'année, afin que vous puissiez vous concentrer sur ce qui compte le plus : fournir de la valeur. Dans ce tutoriel, vous apprendrez **comment ajouter une tâche récurrente** basée sur un jour spécifique de l'année et vous verrez exactement **comment enregistrer le projet au format MPP** pour une intégration fluide avec Microsoft Project.

## Réponses rapides
- **Que signifie « répétition par jour de l'année » ?** Elle planifie une tâche à un jour précis d'un mois donné chaque année.  
- **Quelle classe API crée la récurrence ?** `YearlyRecurrencePattern` combinée avec `ByYearDayRepetition`.  
- **Puis-je définir une date de début et de fin ?** Oui, en utilisant `EndByRecurrenceRange`.  
- **Quel format de fichier est produit ?** Le projet est enregistré au format MPP (`SaveFileFormat.Mpp`).  
- **Ai-je besoin d'une licence pour la production ?** Une licence commerciale est requise pour une utilisation hors évaluation.

## Prérequis

Avant de plonger dans le tutoriel, assurez‑vous que vous disposez des prérequis suivants :

1. Bibliothèque Aspose.Tasks pour .NET : Téléchargez et installez la bibliothèque Aspose.Tasks pour .NET depuis le [site web](https://releases.aspose.com/tasks/net/).  
2. Environnement de développement : Configurez un environnement de développement adapté avec Visual Studio ou tout autre IDE préféré pour le développement .NET.  
3. Connaissances de base en C# : Familiarisez‑vous avec les fondamentaux du langage de programmation C# pour suivre les exemples de code.  
4. Concepts de gestion de projet : La compréhension des concepts de gestion de projet et de la planification des tâches vous aidera à saisir efficacement les notions du tutoriel.

## Importer les espaces de noms

Avant de commencer à coder, importons les espaces de noms nécessaires pour faciliter la manipulation de nos tâches avec Aspose.Tasks pour .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Maintenant, décomposons l'exemple fourni en plusieurs étapes et expliquons chaque étape en détail.

## Comment ajouter une tâche récurrente avec un modèle de jour de l'année

### Étape 1 : Charger le fichier de projet

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Ici, nous initialisons un nouvel objet `Project` et chargeons un fichier de projet existant nommé **Project1.mpp**.

### Étape 2 : Définir les paramètres de la tâche récurrente

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

Dans cette étape, nous définissons les paramètres de notre tâche récurrente. Nous spécifions le nom de la tâche, la durée et le modèle de récurrence. Pour une récurrence annuelle, nous utilisons `YearlyRecurrencePattern` et définissons la répétition pour le **1er jour de juillet** à l'aide de `ByYearDayRepetition`. De plus, nous définissons la plage de récurrence du 1 juillet 2018 au 1 juillet 2019.

### Étape 3 : Ajouter la tâche au projet

```csharp
project.RootTask.Children.Add(parameters);
```

Ici, nous ajoutons les paramètres de la tâche récurrente définis à la tâche racine du projet.

### Étape 4 : Enregistrer le projet au format MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Enfin, nous **enregistrons le projet au format MPP**, le rendant prêt à être ouvert dans Microsoft Project ou tout visualiseur compatible.

## Pourquoi c’est important

- **Automatisation** – Élimine la saisie manuelle des tâches annuelles, réduisant les erreurs humaines.  
- **Cohérence** – Garantit que le même modèle jour‑mois est appliqué sur plusieurs années.  
- **Intégration** – Le fichier MPP résultant peut être partagé avec les parties prenantes qui utilisent Microsoft Project.  

## Pièges courants et conseils

- **Précision du DateTime** – Assurez‑vous que l'heure de début correspond à votre calendrier de projet ; sinon, la tâche peut apparaître décalée.  
- **Fuseaux horaires** – L'API fonctionne avec des objets `DateTime` ; envisagez une conversion en UTC si votre application couvre plusieurs régions.  
- **Application de la licence** – En mode évaluation, le MPP enregistré peut contenir un filigrane ; utilisez une licence valide pour la production.

## Questions fréquemment posées

**Q : Aspose.Tasks peut‑il gérer des modèles de récurrence complexes ?**  
R : Oui, Aspose.Tasks offre une prise en charge complète de divers modèles de récurrence, y compris les répétitions annuelles, mensuelles, hebdomadaires et quotidiennes.

**Q : Aspose.Tasks est‑il compatible avec différents formats de fichiers de projet ?**  
R : Absolument, Aspose.Tasks prend en charge les formats de fichiers de projet populaires tels que MPP, XML et CSV, assurant la compatibilité avec différents outils de gestion de projet.

**Q : Aspose.Tasks propose‑t‑il de la documentation et du support pour les développeurs ?**  
R : Oui, les développeurs peuvent accéder à une documentation exhaustive et demander de l'aide sur les forums communautaires d'Aspose.Tasks pour toute question ou problème.

**Q : Puis‑je personnaliser les propriétés d’une tâche comme la durée et la date de début avec Aspose.Tasks ?**  
R : Bien sûr, Aspose.Tasks fournit des API robustes pour manipuler dynamiquement les propriétés des tâches, permettant aux développeurs de personnaliser les durées, les dates de début, les dépendances, etc.

**Q : Aspose.Tasks convient‑il aux projets de petite comme de grande envergure ?**  
R : En effet, Aspose.Tasks est conçu pour répondre aux besoins des développeurs travaillant sur des projets de toutes tailles, des tâches individuelles aux projets d’entreprise à grande échelle.

---

**Dernière mise à jour :** 2026-04-03  
**Testé avec :** Aspose.Tasks 24.12 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}