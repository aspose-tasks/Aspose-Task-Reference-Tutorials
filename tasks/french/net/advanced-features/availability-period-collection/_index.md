---
date: 2026-03-21
description: Apprenez à gérer les périodes de disponibilité des ressources et à assurer
  une disponibilité efficace des ressources de projet avec Aspose.Tasks pour .NET.
  Ce guide étape par étape montre comment ajouter, mettre à jour et supprimer les
  périodes de disponibilité.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Disponibilité des ressources du projet – Gestion des périodes de disponibilité
  dans Aspose.Tasks
url: /fr/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Disponibilité des ressources du projet : Collection de périodes de disponibilité dans Aspose.Tasks

La gestion **de la disponibilité des ressources du projet** est une partie essentielle d’une planification de projet réussie. Dans ce tutoriel, vous apprendrez **comment gérer la disponibilité** des ressources en utilisant l’API Aspose.Tasks pour .NET, étape par étape, du chargement d’un projet à la copie des périodes entre ressources.

## Réponses rapides
- **Quelle est la classe principale pour les périodes de disponibilité ?** `AvailabilityPeriod` dans l’espace de noms `Aspose.Tasks`.  
- **Puis-je effacer les périodes existantes ?** Oui, appelez `resource.AvailabilityPeriods.Clear()`.  
- **Comment ajouter une nouvelle période ?** Créez un objet `AvailabilityPeriod` et utilisez `Add` ou `Insert`.  
- **Est-il possible de copier des périodes vers une autre ressource ?** Absolument – utilisez `CopyTo` puis ajoutez chaque élément à la ressource cible.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Oui, une licence commerciale Aspose.Tasks est requise pour les déploiements non‑essai.

## Qu’est‑ce que la disponibilité des ressources du projet ?
La disponibilité des ressources du projet définit les dates et les unités (pourcentage de capacité) pendant lesquelles une ressource peut être affectée à des tâches. En contrôlant ces périodes, vous évitez la surallocation et améliorez la précision du planning.

## Pourquoi utiliser Aspose.Tasks pour gérer les périodes de disponibilité ?
- **Intégration .NET complète** – pas d’interop COM, code purement géré.  
- **Contrôle granulaire** – définissez des dates de début/fin précises et des unités fractionnaires.  
- **Copie facile** – déplacez les données de disponibilité entre ressources sans analyse manuelle.  
- **Optimisé pour la performance** – fonctionne efficacement avec de gros fichiers MPP.

## Prérequis
1. **Visual Studio** – toute version récente (2019, 2022 ou ultérieure).  
2. **Aspose.Tasks pour .NET** – téléchargez depuis [here](https://releases.aspose.com/tasks/net/).  
3. **Connaissances de base en C#** – vous devez être à l’aise avec les classes, les collections et LINQ.

## Importer les espaces de noms

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

Nous importons l’espace de noms principal Aspose.Tasks ainsi que les collections .NET standard dont nous aurons besoin plus tard.

## Étape 1 : Initialiser le projet et la ressource

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Ici, nous chargeons un fichier MPP existant et récupérons la ressource dont nous souhaitons modifier la disponibilité (ID = 1).

## Étape 2 : Effacer les périodes de disponibilité existantes

```csharp
resource.AvailabilityPeriods.Clear();
```

L’effacement supprime toutes les périodes précédemment définies, nous offrant une base propre.

## Étape 3 : Ajouter des périodes de disponibilité

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Nous récupérons une collection d’objets `AvailabilityPeriod` (la fonction d’assistance `GetPeriods` est supposée être définie ailleurs) et ajoutons chacun d’eux, en vérifiant que la collection est modifiable.

## Étape 4 : Insérer une nouvelle période de disponibilité

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Cela crée une période personnalisée pour l’année 2013 et l’insère à la position 1 (deuxième emplacement) si elle n’est pas déjà présente.

## Étape 5 : Afficher les périodes de disponibilité

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Un affichage rapide dans la console montre le nombre total et les détails de chaque période – pratique pour le débogage ou la vérification.

## Étape 6 : Copier les périodes de disponibilité vers une autre ressource

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Nous copions l’ensemble de la collection dans un tableau, effaçons les périodes de la ressource cible, puis les remplissons à nouveau. Cela montre comment dupliquer les données de disponibilité entre ressources.

## Étape 7 : Mettre à jour et supprimer les périodes de disponibilité

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Ici, nous ajustons le `AvailableUnits` de l’avant‑dernière période puis supprimons la période 2013 que nous avions ajoutée précédemment.

## Problèmes courants et solutions
- **Erreur de collection en lecture‑seule** – Assurez‑vous que le projet n’est pas ouvert en mode lecture‑seule ou que vous avez appelé `resource.AvailabilityPeriods.Clear()` avant d’ajouter de nouveaux éléments.  
- **Périodes qui se chevauchent** – Aspose.Tasks ne fusionne pas automatiquement les chevauchements ; vous devrez peut‑être écrire une logique personnalisée pour les détecter et les résoudre.  
- **Format de date incorrect** – Utilisez toujours des objets `DateTime` ; l’analyse de chaînes peut entraîner des bugs spécifiques à la locale.

## Questions fréquemment posées

**Q : Puis‑je ajouter des champs personnalisés aux périodes de disponibilité ?**  
R : Non, les périodes de disponibilité dans Aspose.Tasks pour .NET ne prennent pas en charge les champs personnalisés.

**Q : Les périodes de disponibilité sont‑elles liées à des tâches spécifiques ?**  
R : Non, elles sont associées aux ressources et définissent quand la ressource est généralement disponible pour les tâches.

**Q : Puis‑je importer des périodes de disponibilité depuis des sources externes ?**  
R : Oui, vous pouvez importer des périodes depuis CSV, XML ou une base de données en créant des objets `AvailabilityPeriod` et en les ajoutant à la collection.

**Q : Comment gérer les périodes de disponibilité qui se chevauchent ?**  
R : Les chevauchements ne sont pas résolus automatiquement ; vous devez implémenter une validation personnalisée pour fusionner ou rejeter les périodes conflictuelles.

**Q : Existe‑t‑il une limite au nombre de périodes de disponibilité qu’une ressource peut avoir ?**  
R : Il n’y a pas de limite codée en dur, mais des collections très volumineuses peuvent affecter les performances ; envisagez de consolider les périodes lorsque cela est possible.

## Conclusion

Dans ce guide, nous avons couvert tout ce que vous devez savoir pour gérer **la disponibilité des ressources du projet** avec Aspose.Tasks pour .NET — de l’initialisation d’un projet et de la suppression des anciennes données, à l’ajout, l’insertion, la copie, la mise à jour et la suppression des périodes de disponibilité. Maîtriser ces étapes vous aide à maintenir des calendriers de ressources précis et des plannings de projet réalistes.

---

**Dernière mise à jour :** 2026-03-21  
**Testé avec :** Aspose.Tasks pour .NET (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}