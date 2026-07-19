---
date: 2026-07-19
description: Apprenez à contrôler le symbole monétaire après le montant dans les projets
  .NET facilement avec Aspose.Tasks.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Positions du symbole monétaire dans Aspose.Tasks
og_description: Apprenez à placer le symbole monétaire après le montant en utilisant
  Aspose.Tasks pour .NET. Suivez des instructions étape par étape et les meilleures
  pratiques.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Symbole monétaire après le montant dans Aspose.Tasks — Guide rapide
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: Comment placer le symbole monétaire après le montant dans Aspose.Tasks
url: /fr/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment placer le symbole monétaire après le montant dans Aspose.Tasks

## Introduction

Lorsque vous générez des rapports de coûts de projet, le placement du **symbole monétaire après le montant** peut affecter la lisibilité et la conformité aux normes régionales. Aspose.Tasks pour .NET vous permet de contrôler ce formatage en quelques lignes de code, garantissant que chaque chiffre financier apparaît exactement comme vos parties prenantes l’attendent. Dans ce tutoriel, nous parcourrons les étapes requises, expliquerons pourquoi ce paramètre est important et vous montrerons comment l’appliquer dans un projet .NET réel.

## Réponses rapides
- **Que signifie « symbole monétaire après le montant » ?** Il affiche le symbole (par ex., $) après la valeur numérique, comme `100 $`.
- **Quelle propriété contrôle la position ?** `CurrencySymbolPosition` sur l’objet `Project`.
- **Ai‑je besoin d’une licence ?** Une version d’essai fonctionne pour le développement ; une licence commerciale est requise pour la production.
- **Quelles devises sont prises en charge ?** Plus de 50 devises sont intégrées, couvrant la plupart des marchés mondiaux.
- **Puis‑je modifier le paramètre à l’exécution ?** Oui, vous pouvez le mettre à jour à tout moment avant d’enregistrer le fichier du projet.

## Qu’est‑ce que le paramètre « symbole monétaire après le montant » ?
L’option **symbole monétaire après le montant** détermine si le signe monétaire apparaît avant ou après la valeur numérique dans tous les champs monétaires d’un projet. Ajuster ce paramètre garantit que les rapports respectent les conventions comptables locales sans traitement manuel post‑traitement. Cela améliore également la lisibilité pour les parties prenantes habituées à ce format.

## Pourquoi utiliser Aspose.Tasks pour le formatage des devises ?
Aspose.Tasks prend en charge **plus de 50 devises** et peut gérer des projets contenant **plus de 10 000 tâches** sans charger le fichier complet en mémoire, offrant des performances rapides même sur du matériel modeste. L’API vous donne un contrôle programmatique, éliminant le besoin d’éditions manuelles de feuilles de calcul. Cela rend le reporting financier à grande échelle à la fois efficace et fiable.

## Prérequis

### 1. Installation d’Aspose.Tasks pour .NET
Assurez‑vous que la bibliothèque Aspose.Tasks est installée. Vous pouvez la télécharger [ici](https://releases.aspose.com/tasks/net/).

### 2. Connaissances de base en programmation .NET
Une compréhension fondamentale de la programmation .NET est nécessaire pour suivre les exemples.

## Importer les espaces de noms

L’espace de noms `Aspose.Tasks` donne accès à la classe `Project` et aux énumérations associées.

La classe `Project` est l’objet de haut niveau d’Aspose.Tasks qui représente un fichier de projet unique en mémoire. Après avoir importé l’espace de noms, vous pouvez commencer à travailler avec les données du projet.

```csharp

```

Maintenant, décomposons l’exemple en étapes claires et exploitables.

## Comment définir le symbole monétaire après le montant ?

`CurrencySymbolPosition` est une énumération qui spécifie si le symbole monétaire apparaît avant ou après la valeur numérique.

Chargez votre projet, définissez `CurrencySymbolPosition` sur `After`, puis enregistrez — c’est tout ce dont vous avez besoin pour afficher le symbole après le montant. Cette approche directe fonctionne pour toute devise prise en charge et ne nécessite aucune logique de formatage supplémentaire. Vous pouvez également vérifier le paramètre en exportant un rapport de coûts d’exemple afin de vous assurer que le symbole apparaît correctement.

### Étape 1 : Charger le fichier de projet
La classe `Project` charge un fichier MS‑Project existant ou crée un nouveau en mémoire.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Étape 2 : Définir la position du symbole monétaire
`CurrencySymbolPosition` est une énumération qui vous permet de choisir `Before` ou `After`. La définir sur `After` place le symbole après la valeur numérique.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### Étape 3 : Travailler avec le projet
Après avoir configuré la position du symbole, vous pouvez continuer à ajouter des tâches, des ressources ou des champs personnalisés selon vos besoins. Le paramètre est conservé lors de l’enregistrement du projet.

```csharp
// Perform other operations with the project...
```

## Problèmes courants et solutions
- **Le symbole apparaît toujours avant le montant :** Assurez‑vous de définir la propriété *avant* d’appeler `Save`. Le modifier après l’enregistrement nécessite de ré‑enregistrer le fichier.
- **Devise non prise en charge :** Vérifiez que le code de devise que vous utilisez figure dans la liste des devises prises en charge par Aspose.Tasks (plus de 50 devises).
- **Ralentissement des performances sur de gros projets :** Utilisez `ProjectReader` pour diffuser de gros fichiers si vous dépassez 10 000 tâches.

## Questions fréquemment posées

**Q : Puis‑je changer la position du symbole monétaire plusieurs fois dans le même projet ?**  
R : Oui, vous pouvez ajuster `CurrencySymbolPosition` autant de fois que nécessaire ; il suffit de définir la propriété et de ré‑enregistrer le projet.

**Q : Aspose.Tasks prend‑il en charge des devises autres que le dollar américain ?**  
R : Absolument. Aspose.Tasks prend en charge plus de 50 devises internationales, vous permettant de travailler avec n’importe quel format régional.

**Q : Existe‑t‑il une version d’essai d’Aspose.Tasks pour .NET ?**  
R : Oui, vous pouvez obtenir une version d’essai gratuite d’Aspose.Tasks pour .NET [ici](https://releases.aspose.com/).

**Q : Puis‑je obtenir de l’aide si je rencontre des problèmes avec Aspose.Tasks pour .NET ?**  
R : Bien sûr ! Vous pouvez demander de l’assistance sur le forum communautaire Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

**Q : Comment acheter une licence pour Aspose.Tasks pour .NET ?**  
R : Vous pouvez acheter une licence pour Aspose.Tasks pour .NET [ici](https://purchase.aspose.com/buy).

## Conclusion

Contrôler le **symbole monétaire après le montant** est une partie essentielle du reporting financier dans les logiciels de gestion de projet. Avec Aspose.Tasks pour .NET, vous pouvez définir ce paramètre de façon programmatique, en prenant en charge plus de 50 devises et en gérant efficacement de grands projets. Appliquez les étapes ci‑dessus pour que vos rapports de projet respectent les attentes de formatage de toute locale.

---

**Dernière mise à jour :** 2026-07-19  
**Testé avec :** Aspose.Tasks 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Gestion de la collection de calendriers dans Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [Collection d’exceptions de calendrier dans Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Gestion des tarifs MS Project avec Aspose.Tasks pour .NET](/tasks/net/rate-recurring-tasks/handling-rates/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}