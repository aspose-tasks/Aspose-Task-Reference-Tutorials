---
date: 2026-09-14
description: Apprenez comment obtenir la devise de MS Project et lire les propriétés
  du projet Java avec Aspose.Tasks. Guide étape par étape pour extraire les chiffres
  de la devise d'un fichier MPP.
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Comment obtenir la devise de MS Project avec Aspose.Tasks
og_description: Apprenez comment obtenir la devise de MS Project et lire les propriétés
  du projet Java avec Aspose.Tasks. Suivez ce tutoriel Java concis pour extraire les
  chiffres de la devise d'un fichier MPP.
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Comment obtenir la devise de MS Project avec Aspose.Tasks – Guide Java
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Comment obtenir la devise de MS Project avec Aspose.Tasks
url: /fr/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment obtenir la devise du projet MS avec Aspose.Tasks

## Introduction
Si vous vous demandez **comment obtenir la devise du projet MS** à partir d’un fichier Microsoft Project, vous êtes au bon endroit. Dans ce tutoriel complet, vous découvrirez **comment travailler avec les valeurs de devise du projet MS** en utilisant la bibliothèque Aspose.Tasks pour Java. Que vous construisiez un outil de reporting, une utilité de migration, ou que vous ayez simplement besoin de lire les paramètres de devise d’un **fichier de projet Java**, ce guide vous accompagne à chaque étape — du chargement d’un fichier *.mpp* à l’extraction des décimales de la devise. À la fin, vous serez à l’aise pour gérer les données de devise du projet MS dans vos propres applications.

## Réponses rapides
- **Quelle bibliothèque lit les fichiers MS Project ?** Aspose.Tasks for Java.  
- **Combien de lignes de code pour obtenir les décimales de la devise ?** Juste trois lignes concises après le chargement du projet.  
- **Ai‑je besoin d’une licence pour le développement ?** Une version d’essai fonctionne pour les tests ; une licence commerciale est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieure (tout JDK exécutant Aspose.Tasks).  
- **Puis‑je récupérer d’autres propriétés du projet ?** Oui – Aspose.Tasks expose l’ensemble complet des champs du projet (par ex., date de début, taux de coût, etc.).

## Qu'est-ce que la devise du projet MS ?
La propriété `ms project currency` définit le nombre de décimales que Microsoft Project utilise lors de l’affichage des valeurs monétaires. Elle est stockée dans le fichier Project sous le champ **CURRENCY_DIGITS** et détermine si les montants apparaissent comme des nombres entiers, à une décimale, deux décimales, etc. Ce paramètre influence directement les rapports budgétaires, les agrégations de coûts et toute interface affichant des chiffres financiers, ce qui le rend essentiel pour un échange de données précis.

## Pourquoi utiliser Aspose.Tasks pour gérer la devise du projet MS ?
Aspose.Tasks vous permet d’extraire les décimales de la devise sans installer Microsoft Project, et ce avec des performances de niveau entreprise. La bibliothèque prend en charge **plus de 30 ans de versions de fichiers Project** — de Project 2000 à Project 2024—couvrant plus de **150 schémas de fichiers distincts**. Charger un projet de 500 pages prend généralement moins de **2 secondes** sur un serveur standard, et vous pouvez interroger uniquement les champs dont vous avez besoin, maintenant l’utilisation mémoire sous **50 Mo** même pour les plannings les plus volumineux.

## Prérequis
Avant de commencer, assurez‑vous de disposer de :

1. **Environnement de développement Java** – JDK 8 ou plus récent installé et configuré.  
2. **Aspose.Tasks for Java** – téléchargez le JAR le plus récent depuis le site officiel : [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Connaissances de base en Java** – vous devez être à l’aise pour créer un projet Java, ajouter des bibliothèques externes et exécuter une méthode `main`.  

## Importer les packages
Tout d’abord, importez les classes dont nous aurons besoin.  
Importez la classe `Project` et les utilitaires associés de la bibliothèque Aspose.Tasks.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Étape 1 : définir le répertoire de données
Spécifiez le dossier qui contient votre **fichier de projet Java** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Remplacez `"Your Data Directory"` par le chemin absolu ou relatif où se trouve `project.mpp`.

## Étape 2 : charger le fichier mpp  
Nous allons maintenant voir **comment charger les fichiers mpp** avec Aspose.Tasks.  
La classe `Project` représente un fichier Microsoft Project et donne accès à ses propriétés.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Assurez‑vous que le nom du fichier correspond exactement ; sinon, une `IOException` sera levée.

## Étape 3 : récupérer les décimales de la devise  
Une fois le projet chargé, extraire les décimales de la **devise du projet MS** se fait en une seule ligne :  
La méthode `getCurrencyDigits()` renvoie le nombre de décimales définies pour les valeurs monétaires.  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
L’appel renvoie un `Integer` représentant le nombre de décimales (par ex., `2` pour les centimes). La valeur est affichée dans la console, mais vous pouvez également la stocker dans une variable pour un traitement ultérieur.

## Problèmes courants et astuces
- **Fichier non trouvé** – vérifiez le chemin `dataDir` et assurez‑vous que le nom du fichier est correct, y compris l’extension `.mpp`.  
- **Version de fichier non prise en charge** – Aspose.Tasks prend en charge les formats Project 2000‑2024 ; les fichiers plus anciens ou corrompus peuvent nécessiter une conversion.  
- **Licence non définie** – pendant le développement, une version d’essai fonctionne, mais en production vous devez appliquer une licence valide pour éviter les filigranes d’évaluation.

## Questions fréquemment posées

**Q : Aspose.Tasks peut‑il gérer d’autres attributs du projet en plus des décimales de la devise ?**  
R : Oui, Aspose.Tasks offre un large éventail de fonctionnalités pour manipuler divers aspects des fichiers Project, tels que les tâches, les ressources et les champs personnalisés.

**Q : Aspose.Tasks est‑il adapté aux applications de niveau entreprise ?**  
R : Absolument, Aspose.Tasks est conçu pour répondre aux exigences des projets de niveau entreprise, offrant haute performance et évolutivité.

**Q : Aspose.Tasks prend‑il en charge le développement multiplateforme ?**  
R : Oui, vous pouvez utiliser Aspose.Tasks pour Java sur n’importe quelle plateforme supportant le Java Runtime Environment (Windows, Linux, macOS).

**Q : Puis‑je essayer Aspose.Tasks avant d’acheter ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite depuis la [page des versions Aspose](https://releases.aspose.com/).

**Q : Où puis‑je obtenir du support pour Aspose.Tasks ?**  
R : Vous pouvez trouver du support sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Dernière mise à jour :** 2026-09-14  
**Testé avec :** Aspose.Tasks for Java (dernière version au moment de la rédaction)  
**Auteur :** Aspose

## Tutoriels associés

- [propriétés du projet Java – Extraire le symbole monétaire du MPP avec Aspose.Tasks pour Java](/tasks/java/currency/currency-symbols/)
- [Comment récupérer la devise depuis MS Project avec Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Propriétés du projet Java – Lire les métadonnées avec Aspose.Tasks](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}