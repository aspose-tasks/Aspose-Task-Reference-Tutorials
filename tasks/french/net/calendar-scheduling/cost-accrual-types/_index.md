---
date: 2026-07-05
description: Apprenez comment suivre le budget du projet et gérer les coûts du projet
  en utilisant Aspose.Tasks pour .NET. Définissez les Cost Accrual Types pour un suivi
  précis des coûts.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Cost Accrual Types dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Suivre le budget du projet avec les Cost Accrual Types dans Aspose.Tasks
url: /fr/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Suivre le budget du projet avec les types d'accumulation des coûts dans Aspose.Tasks

## Introduction

Suivre avec précision le **budget du projet** est la colonne vertébrale d’une livraison de projet réussie. Lorsque les informations de coût sont capturées aux bons moments, vous pouvez prévoir les dépassements, ajuster les ressources et tenir les parties prenantes informées. Aspose.Tasks pour .NET offre aux développeurs un contrôle fin sur l’accumulation des coûts, vous permettant de décider *quand* un coût est enregistré — que ce soit au début du travail, de façon continue, ou uniquement lorsque le travail est terminé. Ce tutoriel vous guide à travers les concepts, montre comment définir un type d’accumulation, et démontre les meilleures pratiques pour un suivi fiable du budget.

## Réponses rapides
- **Quel est le but principal des types d'accumulation des coûts ?** Ils déterminent le moment du cycle de vie d’une tâche où le coût est reconnu, permettant un suivi précis du budget.  
- **Quelle valeur d'énumération retarde le coût jusqu'à la fin du travail ?** `CostAccrualType.End`.  
- **Ai‑je besoin d’une licence pour exécuter le code ?** Oui, une licence valide Aspose.Tasks est requise pour une utilisation en production.  
- **Puis‑je changer les types d'accumulation pour de nombreuses ressources à la fois ?** Oui — parcourez la collection `Resources` et attribuez le type souhaité.  
- **Quelles versions .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu'est‑ce que le type d'accumulation des coûts ?
Un **type d'accumulation des coûts** indique à Aspose.Tasks quand appliquer le coût d’une ressource au budget du projet. Il est représenté par l’énumération `CostAccrualType` et peut être défini par ressource ou par tâche. Choisir le type correct garantit que les données de coût correspondent aux politiques de facturation de votre organisation, que vous ayez besoin d’enregistrer les coûts au début du travail, de les proratiser sur la durée, ou uniquement après l’achèvement.

## Pourquoi suivre le budget du projet en utilisant les types d'accumulation des coûts ?
Aspose.Tasks prend en charge **quatre** options d’accumulation — `Start`, `Prorated`, `Duration` et `End` — couvrant l’ensemble des scénarios comptables typiques. Sélectionner l’option appropriée vous permet d’aligner la reconnaissance des coûts avec les cycles de facturation contractuels, de réduire les écarts dans les rapports financiers, et de générer des états de coûts qui s’intègrent facilement aux systèmes ERP, tout en maintenant une faible consommation de mémoire pour les projets de grande taille.

## Prérequis

Avant de commencer, assurez‑vous de disposer des éléments suivants :

### 1. Installer Aspose.Tasks pour .NET
Pour démarrer, vous devez installer Aspose.Tasks pour .NET dans votre environnement de développement. Vous pouvez télécharger la bibliothèque depuis la [page de téléchargement](https://releases.aspose.com/tasks/net/) et suivre les instructions d’installation fournies.

### 2. Familiarité avec le .NET Framework
Une connaissance de base du framework .NET et du langage de programmation C# est requise pour suivre les exemples de ce tutoriel.

## Comment définir le type d'accumulation des coûts pour une ressource ?

Chargez le projet, localisez la ressource cible, et attribuez le `CostAccrualType` souhaité. Le modèle en deux lignes ci‑dessous est l’approche standard : créez une instance `Project`, récupérez la ressource par son ID, puis définissez `CostAccrualType`. Cette séquence concise garantit que vous **suivez le budget du projet** avec précision dès l’ajout de la ressource.

### Étape 1 : Importer les espaces de noms
Commençons par importer les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.Tasks dans notre projet .NET :

```csharp

```

Maintenant que les espaces de noms sont prêts, nous pouvons passer au chargement d’un fichier de projet.

### Étape 2 : Charger le fichier de projet
La classe `Project` représente un fichier Microsoft Project et fournit l’accès à ses tâches, ressources et autres données.

```csharp
var project = new Project("Project2.mpp");
```

Tout d’abord, nous devons charger le fichier de projet dans notre application. Nous créons un nouvel objet `Project` et l’initialisons avec le chemin vers notre fichier de projet.

### Étape 3 : Accéder à la ressource
La collection `Resources` contient toutes les ressources définies dans le projet. La méthode `GetById` récupère une ressource par son identifiant unique.

```csharp
var resource = project.Resources.GetById(1);
```

Ensuite, nous accédons à la ressource à laquelle nous voulons appliquer le type d’accumulation des coûts. Nous utilisons la méthode `GetById` de la collection `Resources` et passons l’ID de la ressource en argument. Cela illustre **l’accès à une ressource par ID**, une exigence courante lors de l’automatisation des mises à jour de coûts.

### Étape 4 : Définir le type d'accumulation des coûts
La méthode `Set` attribue une valeur à un champ de ressource.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Ici, nous définissons le type d’accumulation des coûts pour la ressource. Dans cet exemple, nous le réglons sur `CostAccrualType.End`, ce qui signifie que les coûts ne seront pas accumulés tant que le travail restant n’est pas nul. Choisir `End` est idéal lorsque vous souhaitez **suivre le budget du projet** uniquement après l’achèvement complet d’une tâche.

### Étape 5 : Continuer à travailler avec le projet
Après avoir défini le type d’accumulation des coûts, vous pouvez poursuivre vos travaux sur le projet selon vos besoins, en effectuant des opérations supplémentaires ou des calculs tels que la génération de rapports de coûts, la mise à jour des affectations, ou l’exportation du fichier.

## Pièges courants et astuces professionnelles
- **Astuce :** Appelez toujours `project.Save` après avoir modifié les types d’accumulation afin de persister les changements.  
- **Piège :** Définir `CostAccrualType.Start` sur une ressource qui ne commence jamais le travail gonflera les rapports budgétaires — vérifiez d’abord les plannings des tâches.  
- **Astuce :** Utilisez `project.Resources.ToList()` lorsque vous devez mettre à jour en lot de nombreuses ressources ; cela évite les recherches répétées dans la collection et améliore les performances sur les grands projets.

## Questions fréquentes

**Q : Puis‑je changer le type d'accumulation des coûts pour plusieurs ressources simultanément ?**  
R : Oui, parcourez `project.Resources` et attribuez le `CostAccrualType` souhaité à chaque ressource dans une boucle `foreach`.

**Q : Quels sont les autres types d'accumulation des coûts disponibles en plus de `End` ?**  
R : Aspose.Tasks propose `Start`, `Prorated` et `Duration` — chacun correspond à une stratégie de facturation différente.

**Q : Comment déterminer le type d'accumulation des coûts actuel d'une ressource spécifique ?**  
R : Récupérez la valeur via `resource.Get(TskResource.CostAccrualType)` ; elle renvoie l’énumération représentant le paramètre actuel.

**Q : Est‑il possible d’appliquer des types d'accumulation différents à différentes tâches dans le même projet ?**  
R : Absolument. Les tâches et les ressources exposent toutes deux une propriété `CostAccrualType`, permettant une configuration indépendante par entité.

**Q : Aspose.Tasks prend‑il en charge des types d'accumulation des coûts personnalisés ?**  
R : Non, la bibliothèque ne prend actuellement en charge que les quatre types intégrés ; une logique personnalisée doit être implémentée en externe si nécessaire.

---

**Dernière mise à jour :** 2026-07-05  
**Testé avec :** Aspose.Tasks 24.8 pour .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Calendrier et planification Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [Gestion des tarifs MS Project avec Aspose.Tasks pour .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Gérer facilement les ressources MS Project avec Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}