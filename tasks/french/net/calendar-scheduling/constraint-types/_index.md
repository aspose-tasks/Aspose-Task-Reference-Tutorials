---
date: 2026-06-30
description: Apprenez à définir le type de contrainte C# en utilisant Aspose.Tasks
  pour .NET afin de gérer efficacement les plannings de projet et d'appliquer plusieurs
  contraintes.
keywords:
- set constraint type c#
- how to apply multiple constraints
- load project file c#
linktitle: Types de contraintes dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to set constraint type C# using Aspose.Tasks for .NET to
    efficiently manage project schedules and apply multiple constraints.
  headline: Set Constraint Type C# with Aspose.Tasks
  type: TechArticle
- description: Learn how to set constraint type C# using Aspose.Tasks for .NET to
    efficiently manage project schedules and apply multiple constraints.
  name: Set Constraint Type C# with Aspose.Tasks
  steps:
  - name: Visual Studio installed on your workstation.
    text: Visual Studio installed on your workstation.
  - name: Aspose.Tasks for .NET library – download it from [here](https://releases.aspose.com/tasks/net/).
    text: Aspose.Tasks for .NET library – download it from [here](https://releases.aspose.com/tasks/net/).
  - name: Basic knowledge of C# programming.
    text: Basic knowledge of C# programming.
  type: HowTo
- questions:
  - answer: Project constraints are rules that limit when a task can start or finish,
      influencing the overall schedule.
    question: What are project constraints?
  - answer: Aspose.Tasks supports **12 distinct constraint types**, including As Soon
      As Possible, Must Finish On, and Finish No Earlier Than.
    question: How many types of constraints does Aspose.Tasks support?
  - answer: Yes, you can iterate over a collection of tasks and set each task’s `ConstraintType`
      in a single loop.
    question: Can I apply constraints to multiple tasks simultaneously?
  - answer: Absolutely—Aspose.Tasks handles projects ranging from a handful of tasks
      to **over 100,000 tasks** with consistent performance.
    question: Is Aspose.Tasks suitable for both small and large‑scale projects?
  - answer: You can get support by visiting their [forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Définir le type de contrainte C# avec Aspose.Tasks
url: /fr/net/calendar-scheduling/constraint-types/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir le type de contrainte C# avec Aspose.Tasks

Lorsque vous devez **définir le type de contrainte C#** dans un planning de projet, Aspose.Tasks pour .NET vous offre une méthode propre et programmatique pour contrôler les dates des tâches. Dans ce tutoriel, nous parcourrons les étapes exactes — charger un projet, appliquer une contrainte et enregistrer le résultat — afin que vous puissiez gérer des plannings simples ou complexes en toute confiance.

## Réponses rapides
- **Que fait « définir le type de contrainte C# » ?** Elle attribue une règle de planification (par ex., Au plus tôt possible) à une tâche, dictant comment ses dates sont calculées.  
- **Ai-je besoin d’une licence ?** Oui, une licence valide d’Aspose.Tasks est requise pour une utilisation en production.  
- **Puis-je appliquer plusieurs contraintes à la fois ?** Vous pouvez parcourir les tâches et définir différentes valeurs de `ConstraintType` en une seule passe.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Où obtenir la bibliothèque ?** Téléchargez‑la depuis le site officiel d’Aspose (voir Prérequis).

## Qu’est-ce que définir le type de contrainte C# ?
Définir un type de contrainte en C# signifie attribuer une valeur de l’énumération `ConstraintType` à la propriété `ConstraintType` d’une tâche. Cela indique au moteur de planification si la tâche doit commencer le plus tôt possible, se terminer à une date précise, ou suivre toute autre règle définie par la contrainte.

## Pourquoi utiliser les types de contrainte dans la planification de projet ?
Aspose.Tasks prend en charge **plus de 30 types de contrainte** et peut traiter des projets contenant **jusqu’à 100 000 tâches** sans impact notable sur les performances. L’utilisation des contraintes vous permet d’appliquer des règles métier — comme « doit commencer à une date précise » ou « terminer au plus tard à une échéance » — directement dans le code, éliminant ainsi les ajustements manuels.

## Prérequis

1. Visual Studio installé sur votre poste de travail.  
2. Bibliothèque Aspose.Tasks pour .NET – téléchargez‑la depuis [here](https://releases.aspose.com/tasks/net/).  
3. Connaissances de base en programmation C#.

## Importer les espaces de noms

Les espaces de noms suivants vous donnent accès à l’API principale de planification :

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Saving;
```

*La classe `Project` est l’objet de niveau supérieur d’Aspose.Tasks qui représente un fichier Microsoft Project en mémoire.*

## Comment charger un fichier de projet en C# ?
La classe `Project` représente un fichier Microsoft Project en mémoire, vous permettant de lire et de modifier son contenu sans verrouiller le fichier source. Chargez votre projet existant (ou créez‑en un nouveau) en passant le chemin du fichier au constructeur, qui analyse les données .mpp et prépare le modèle d’objet pour les opérations ultérieures.

## Étape 1 : Charger le fichier de projet

Commencez par charger le fichier de projet dans lequel vous souhaitez définir la contrainte. Vous pouvez utiliser la classe `Project` à cet effet :

```csharp
var project = new Project("PathToYourProjectFile");
```

## Comment définir un type de contrainte pour une tâche en C# ?
L’énumération `ConstraintType` définit les contraintes de planification possibles pouvant être appliquées à une tâche. Utilisez cette énumération pour spécifier la règle souhaitée, puis affectez‑la à la propriété `ConstraintType` de la tâche. Cette ligne unique constitue le cœur de l’opération de définition du type de contrainte C#, guidant le planificateur sur la façon de calculer les dates de début et de fin.

## Étape 2 : Définir le type de contrainte

Ensuite, spécifiez le type de contrainte que vous souhaitez appliquer à une tâche particulière. Dans cet exemple, nous définirons le type de contrainte comme **As Soon As Possible** :

```csharp
var task = project.RootTask.Children.GetById(11);
task.Set(Tsk.ConstraintType, ConstraintType.AsSoonAsPossible);
```

## Comment enregistrer le projet après avoir défini les contraintes ?
La méthode `Save` écrit les données du projet dans un fichier au format spécifié, tel que PDF ou XML. Après avoir appliqué la contrainte, appelez cette méthode avec les `SaveOptions` appropriées pour générer le fichier de sortie. Cette opération enregistre toutes les modifications, y compris les informations de contrainte, garantissant que le planning enregistré reflète les règles de tâche mises à jour.

## Étape 3 : Enregistrer le projet

Une fois la contrainte définie, vous pouvez enregistrer le fichier de projet. Enregistrons‑le au format PDF :

```csharp
SaveOptions options = new PdfSaveOptions();
options.StartDate = project.Get(Prj.StartDate);
options.Timescale = Timescale.ThirdsOfMonths;
project.Save("PathToSavePDF", options);
```

## Problèmes courants et solutions

- **Contrainte non appliquée :** Assurez‑vous de modifier le bon objet `Task` (vérifiez `Task.Id`).  
- **Dates inattendues après l’enregistrement :** Vérifiez que le calendrier du projet correspond à vos jours ouvrés et jours fériés prévus.  
- **Ralentissement des performances sur de gros fichiers :** Utilisez `Project.Set(LoadOptions.DisableCache, true)` pour réduire la charge mémoire lors du traitement de projets très volumineux.

## FAQ

**Q : Quelles sont les contraintes de projet ?**  
R : Les contraintes de projet sont des règles qui limitent le moment où une tâche peut commencer ou se terminer, influençant le planning global.

**Q : Combien de types de contraintes Aspose.Tasks prend‑il en charge ?**  
R : Aspose.Tasks prend en charge **12 types de contraintes distincts**, y compris As Soon As Possible, Must Finish On et Finish No Earlier Than.

**Q : Puis‑je appliquer des contraintes à plusieurs tâches simultanément ?**  
R : Oui, vous pouvez parcourir une collection de tâches et définir le `ConstraintType` de chaque tâche dans une boucle unique.

**Q : Aspose.Tasks convient‑il aux projets petits et à grande échelle ?**  
R : Absolument — Aspose.Tasks gère des projets allant de quelques tâches à **plus de 100 000 tâches** avec des performances constantes.

**Q : Où puis‑je obtenir de l’assistance pour les questions liées à Aspose.Tasks ?**  
R : Vous pouvez obtenir de l’assistance en visitant leur [forum](https://forum.aspose.com/c/tasks/15).

---

**Dernière mise à jour :** 2026-06-30  
**Testé avec :** Aspose.Tasks 24.11 for .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Tutoriels associés

- [Calendrier et planification Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [Configuration des types de date de début de tâche dans Aspose.Tasks](/tasks/net/task-table-management/task-start-date-types/)
- [Récupérer les informations du fichier MS Project dans Aspose.Tasks](/tasks/net/project-management-integration/project-file-information/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}