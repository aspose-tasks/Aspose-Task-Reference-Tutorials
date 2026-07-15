---
date: 2026-02-10
description: Apprenez à extraire et à mettre à jour les propriétés d’un projet Java,
  telles que le symbole monétaire, à l’aide d’Aspose.Tasks pour Java. Modifiez la
  devise du projet et récupérez facilement le symbole monétaire.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Propriétés du projet Java – Extraire le symbole monétaire du MPP à l'aide d'Aspose.Tasks
  pour Java
url: /fr/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraire le symbole monétaire mpp avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous apprendrez à travailler avec **java project properties** — plus précisément comment extraire le symbole monétaire d’un fichier Microsoft Project (MPP) et comment **change currency symbol java** ou **retrieve currency symbol java** en utilisant la bibliothèque Aspose.Tasks. Que vous construisiez un outil de reporting, intégriez des données Project dans un système financier, ou ayez simplement besoin d’afficher le bon symbole monétaire dans votre interface, maîtriser cette tâche petite mais essentielle rendra vos applications Java plus robustes et conviviales.

## Réponses rapides
- **Que signifie « extract currency symbol mpp » ?** Cela signifie lire le symbole monétaire stocké dans un fichier MPP (Microsoft Project).  
- **Quelle bibliothèque gère cela ?** Aspose.Tasks for Java fournit une API simple pour la tâche.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Combien de temps cela prend‑il ?** Avec le code ci‑dessous, vous pouvez obtenir le symbole en moins d’une minute.  
- **Puis‑je également changer le symbole ?** Oui – vous pouvez définir une nouvelle valeur en utilisant la même propriété `Prj.CURRENCY_SYMBOL`.

## Qu’est‑ce que « extract currency symbol mpp » ?
Microsoft Project stocke le symbole monétaire (par ex., $, €, £) dans l’en‑tête du fichier projet. L’opération **extract currency symbol mpp** lit cette valeur afin que vous puissiez l’afficher ou la manipuler programmatiquement.

## Pourquoi mettre à jour le symbole monétaire dans les propriétés de projet Java ?
Les projets couvrent souvent plusieurs régions. Pouvoir **change project currency** ou **update currency symbol** à l’exécution vous permet d’adapter rapports, factures ou tableaux de bord au marché local sans recréer le fichier projet complet. Cette flexibilité est une partie essentielle de la gestion efficace des **java project properties**.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – version 8 ou supérieure.  
2. **Aspose.Tasks for Java** – téléchargez le dernier JAR depuis la [page de téléchargement Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Un fichier **project.mpp** valide placé dans un dossier que vous pouvez référencer depuis votre code.

## Importer les packages
Tout d’abord, importez les classes dont nous aurons besoin pour travailler avec les fichiers Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Étape 1 : Définir le répertoire de données
Indiquez à l’application où se trouve votre fichier *.mpp*.

```java
String dataDir = "Your Data Directory";
```

> **Conseil :** Utilisez `System.getProperty("user.dir")` pour construire un chemin absolu qui fonctionne sur n’importe quelle machine.

## Étape 2 : Charger le fichier MS Project
Créez un objet `Project` qui représente le fichier MPP en mémoire.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Étape 3 : Récupérer (et éventuellement modifier) le symbole monétaire
Nous **retrieve currency symbol java** en lisant la propriété `Prj.CURRENCY_SYMBOL`. Vous pouvez également **change currency symbol java** (ou **change project currency**) en assignant une nouvelle chaîne à la même propriété.

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
| Symbole inattendu (ex., `?`) | Projet créé avec une locale non standard | Assurez‑vous que le fichier MPP source définit réellement un symbole monétaire ; vous pouvez en définir un programmatiquement comme indiqué ci‑dessus |
| Erreur de licence | Utilisation de la version d'essai sans fichier de licence valide | Chargez votre licence avec `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` avant de créer l’objet `Project` |

## Questions fréquentes

**Q : Puis‑je manipuler d’autres attributs du projet en plus des symboles monétaires avec Aspose.Tasks ?**  
R : Oui, Aspose.Tasks vous permet de modifier les tâches, les ressources, les affectations, les calendriers et de nombreuses autres propriétés du projet.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de fichiers MS Project ?**  
R : Absolument. Il prend en charge les formats MPP, MPT et XML de Project 98 jusqu’aux dernières versions.

**Q : Aspose.Tasks propose‑t‑il de la documentation et du support pour les développeurs ?**  
R : Des documents d’API complets, des exemples de code et un forum de support dédié sont disponibles sur le site web d’Aspose.Tasks.

**Q : Puis‑je essayer Aspose.Tasks avant de l’acheter ?**  
R : Oui – un essai gratuit complet peut être téléchargé depuis le [site Aspose](https://purchase.aspose.com/buy).

**Q : Comment obtenir une licence temporaire pour Aspose.Tasks ?**  
R : Des licences temporaires sont disponibles sur la [page de licence temporaire d’Aspose](https://purchase.aspose.com/temporary-license/) à des fins d’évaluation.

---

**Dernière mise à jour :** 2026-02-10  
**Testé avec :** Aspose.Tasks for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}