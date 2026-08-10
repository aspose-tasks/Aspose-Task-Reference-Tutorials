---
date: 2026-04-06
description: Apprenez à ajouter une ressource à un projet et à définir les périodes
  de disponibilité des ressources en utilisant Aspose.Tasks pour .NET. Guide étape
  par étape pour gérer les calendriers des ressources.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Travailler avec les périodes de disponibilité dans Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ajouter une ressource au projet et définir la disponibilité dans Aspose.Tasks
url: /fr/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une ressource au projet et définir la disponibilité dans Aspose.Tasks

## Introduction

Dans ce tutoriel, vous apprendrez **comment ajouter une ressource à un projet** puis définir ses périodes de disponibilité en utilisant la bibliothèque Aspose.Tasks .NET. La gestion des calendriers de ressources est essentielle pour des plannings de projet réalistes, et les étapes ci‑dessous vous guident à travers l’ensemble du processus — depuis la création d’une instance de projet jusqu’à l’affichage des détails de chaque période.

## Réponses rapides
- **Quel est l'objectif principal ?** Ajouter une ressource à un projet et configurer ses périodes de disponibilité.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks pour .NET.  
- **Ai-je besoin d'une licence pour la production ?** Oui, une licence commerciale est requise.  
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Temps d'implémentation ?** Typiquement moins de 15 minutes pour les scénarios de base.

## Qu’est‑ce que « ajouter une ressource à un projet » ?

Ajouter une ressource à un projet crée un espace réservé pour une personne, un équipement ou un matériau qui peut être affecté aux tâches. Une fois la ressource créée, vous pouvez **définir la disponibilité de la ressource**, définir son calendrier de travail, et laisser le planificateur respecter ces contraintes.

## Pourquoi configurer le planning de travail et les périodes de disponibilité ?

- **Planification précise :** Les tâches sont planifiées uniquement lorsque la ressource est réellement disponible.  
- **Contrôle des coûts :** Les unités de disponibilité reflètent un effort à temps partiel, vous aidant à calculer correctement les coûts de main‑d’œuvre.  
- **Nivellement des ressources :** Le moteur peut automatiquement niveler les sur‑allocations lorsqu’il connaît le calendrier de chaque ressource.

## Prérequis

1. Visual Studio (ou tout IDE compatible .NET).  
2. Aspose.Tasks pour .NET – téléchargez depuis [here](https://releases.aspose.com/tasks/net/).  
3. Connaissances de base en C#.

## Importer les espaces de noms

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Comment ajouter une ressource à un projet ?

### Étape 1 : Créer une nouvelle instance `Project`

```csharp
var project = new Project();
```

Cet objet représente l’ensemble du fichier de projet en mémoire.

### Étape 2 : Ajouter une ressource au projet

```csharp
var resource = project.Resources.Add("Work Resource");
```

L’appel crée une **ressource** nommée *Work Resource* que vous pourrez ensuite associer aux tâches.

### Étape 3 : Définir les périodes de disponibilité

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` est une méthode d’aide (implémentation non affichée) qui renvoie une collection d’objets `AvailabilityPeriod`. Chaque période spécifie une date de début, une date de fin, et les unités (pourcentage d’effort à temps plein) pendant lesquelles la ressource est disponible.

### Étape 4 : Ajouter les périodes à la ressource

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Ici nous **définissons la disponibilité de la ressource** en parcourant la collection et en ajoutant chaque période au calendrier de la ressource.

### Étape 5 : Afficher les détails de la disponibilité

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

La sortie console vous permet de vérifier que les périodes ont été correctement enregistrées.

## Pièges courants et conseils

- **Précision des dates :** `AvailableFrom` et `AvailableTo` sont des valeurs `DateTime` ; assurez‑vous qu’elles sont réglées à minuit si vous souhaitez des périodes d’une journée entière.  
- **Plage des unités :** Les valeurs valides sont 0‑100  %; les valeurs en dehors de cette plage déclencheront une exception.  
- **Périodes qui se chevauchent :** Les périodes qui se chevauchent sont fusionnées automatiquement, mais il est plus clair de les garder distinctes.

## Questions fréquemment posées

### Q1 : Puis‑je utiliser Aspose.Tasks pour .NET dans des projets commerciaux ?

A1 : Oui, Aspose.Tasks pour .NET peut être utilisé dans des projets commerciaux. Vous pouvez acheter une licence [here](https://purchase.aspose.com/buy).

### Q2 : Existe‑t‑il un essai gratuit disponible pour Aspose.Tasks pour .NET ?

A2 : Oui, vous pouvez obtenir un essai gratuit d’Aspose.Tasks pour .NET [here](https://releases.aspose.com/).

### Q3 : Où puis‑je trouver la documentation d’Aspose.Tasks pour .NET ?

A3 : Vous pouvez trouver la documentation [here](https://reference.aspose.com/tasks/net/).

### Q4 : Comment obtenir du support pour Aspose.Tasks pour .NET ?

A4 : Vous pouvez obtenir du support via le forum communautaire [here](https://forum.aspose.com/c/tasks/15).

### Q5 : Proposez‑vous des licences temporaires pour Aspose.Tasks pour .NET ?

A5 : Oui, des licences temporaires sont disponibles [here](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2026-04-06  
**Testé avec :** Aspose.Tasks pour .NET (dernière version stable)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}