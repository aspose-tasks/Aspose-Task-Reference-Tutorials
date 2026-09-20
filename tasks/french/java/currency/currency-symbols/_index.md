---
date: 2026-09-20
description: Apprenez à extraire le symbole monétaire mpp et à mettre à jour les propriétés
  du projet en utilisant Aspose.Tasks for Java. Modifiez et récupérez le symbole en
  quelques lignes de code seulement.
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: Extraire le symbole monétaire mpp avec Aspose.Tasks for Java
og_description: Apprenez à extraire le symbole monétaire mpp et à mettre à jour les
  propriétés du projet avec Aspose.Tasks for Java. Rapide, fiable et prêt pour la
  production.
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: Comment extraire le symbole monétaire mpp avec Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: Comment extraire le symbole monétaire mpp avec Aspose.Tasks Java
url: /fr/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraire le symbole monétaire mpp à l'aide d'Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous apprendrez à travailler avec **java project properties** — plus précisément comment **extract currency symbol mpp** à partir d'un fichier Microsoft Project (MPP) et comment **change currency symbol java** ou **retrieve currency symbol java** en utilisant la bibliothèque Aspose.Tasks. Que vous construisiez un outil de reporting financier, intégriez des données Project dans un système ERP, ou ayez simplement besoin d'afficher le symbole monétaire correct dans votre interface utilisateur, maîtriser cette tâche petite mais essentielle rendra vos applications Java plus robustes et conviviales.

## Réponses rapides
- **What does “extract currency symbol mpp” mean?** Cela signifie lire le symbole monétaire stocké dans un fichier MPP (Microsoft Project).  
- **Which library handles this?** Aspose.Tasks for Java fournit une API simple pour cette tâche.  
- **Do I need a license?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **How long does it take?** Avec le code ci‑dessous, vous pouvez obtenir le symbole en moins d’une minute.  
- **Can I also change the symbol?** Oui – vous pouvez définir une nouvelle valeur en utilisant la même propriété `Prj.CURRENCY_SYMBOL`.

## Qu'est-ce que “extract currency symbol mpp” ?
Extraire le symbole monétaire d'un fichier MPP consiste à lire la chaîne d'un caractère que Microsoft Project stocke dans l'en‑tête du fichier pour représenter l'unité monétaire du projet. Cette opération vous permet d'afficher le symbole correct (tel que $, €, £) dans vos propres applications sans coder en dur une valeur.

## Pourquoi mettre à jour le symbole monétaire dans les propriétés du projet java ?
Mettre à jour le symbole monétaire vous permet de localiser les rapports, factures et tableaux de bord à la volée. Les entreprises qui gèrent des projets dans plusieurs régions peuvent changer le symbole en une seule étape, évitant ainsi de dupliquer l’ensemble du fichier projet. Aspose.Tasks peut modifier la propriété en mémoire et enregistrer le fichier, prenant en charge des projets contenant jusqu’à 2 000 tâches sans impact notable sur les performances.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – version 8 ou supérieure.  
2. **Aspose.Tasks for Java** – téléchargez le dernier JAR depuis la [page de téléchargement Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Un fichier **project.mpp** valide placé dans un dossier que vous pouvez référencer depuis votre code.

## Importer les packages
Tout d'abord, importez les classes dont nous aurons besoin pour travailler avec les fichiers Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Étape 1 : définir le répertoire de données
Indiquez à l'application où se trouve votre fichier *.mpp*.

```java
String dataDir = "Your Data Directory";
```

> **Astuce :** Utilisez `System.getProperty("user.dir")` pour construire un chemin absolu qui fonctionne sur n'importe quelle machine.

## Étape 2 : charger le fichier MS Project
`Project` est l'objet de haut niveau d'Aspose.Tasks qui représente un fichier Microsoft Project unique en mémoire. La création de cet objet charge la structure du fichier sans nécessiter l'installation de Microsoft Project.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Étape 3 : récupérer (et éventuellement modifier) le symbole monétaire
`Prj.CURRENCY_SYMBOL` est la clé de propriété qui stocke le symbole monétaire. Le lire renvoie le symbole actuel ; lui assigner une nouvelle chaîne met à jour la définition monétaire du projet.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

L’appel `System.out.println` affiche le symbole (par ex., `$`) dans la console, confirmant que l’extraction a réussi.

## Problèmes courants et comment les résoudre
| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| `NullPointerException` sur `project.get(...)` | Chemin de fichier incorrect ou fichier introuvable | Vérifiez `dataDir` et le nom du fichier ; utilisez `new File(dataDir).exists()` pour déboguer |
| Symbole inattendu (ex. `?`) | Projet créé avec une locale non standard | Assurez‑vous que le fichier MPP source définit réellement un symbole monétaire ; vous pouvez en définir un programmatiquement comme montré ci‑dessus |
| Erreur de licence | Utilisation de l’essai sans fichier de licence valide | Chargez votre licence avec `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` avant de créer l’objet `Project` |

## Questions fréquemment posées

**Q : Puis‑je manipuler d’autres attributs du projet en plus des symboles monétaires avec Aspose.Tasks ?**  
R : Oui, Aspose.Tasks vous permet de modifier les tâches, ressources, affectations, calendriers et bien d’autres propriétés du projet.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de fichiers MS Project ?**  
R : Absolument. Il prend en charge les formats MPP, MPT et XML de Project 98 jusqu’aux dernières versions.

**Q : Aspose.Tasks propose‑t‑il de la documentation et du support pour les développeurs ?**  
R : Une documentation API complète, des exemples de code et un forum de support dédié sont disponibles sur le site d’Aspose.Tasks.

**Q : Puis‑je essayer Aspose.Tasks avant de l’acheter ?**  
R : Oui – un essai gratuit entièrement fonctionnel peut être téléchargé depuis le [site Aspose](https://purchase.aspose.com/buy).

**Q : Comment obtenir une licence temporaire pour Aspose.Tasks ?**  
R : Les licences temporaires sont fournies sur la [page de licence temporaire Aspose](https://purchase.aspose.com/temporary-license/) à des fins d’évaluation.

---

**Dernière mise à jour :** 2026-09-20  
**Testé avec :** Aspose.Tasks for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose

## Tutoriels associés

- [Propriétés du projet Java – Lire les métadonnées avec Aspose.Tasks](/tasks/java/project-properties/)
- [Comment récupérer la devise depuis MS Project avec Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Définir la date de début du projet dans MS Project à l'aide d'Aspose.Tasks pour Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}