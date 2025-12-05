---
date: 2025-12-05
description: Apprenez à gérer efficacement les décimales monétaires de MS Project
  à l’aide d’Aspose.Tasks pour Java. Guide étape par étape couvrant la manipulation
  des fichiers de projet Java et la façon de charger les fichiers MPP.
language: fr
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Gérer les décimales de la devise MS Project avec Aspose.Tasks
url: /java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gérer les chiffres de devise MS Project avec Aspose.Tasks

## Introduction
Dans ce tutoriel complet, vous découvrirez **comment travailler avec les valeurs de devise MS Project** à l’aide de la bibliothèque Aspose.Tasks pour Java. Que vous construisiez un outil de reporting, une utilité de migration, ou que vous ayez simplement besoin de lire les paramètres de devise d’un **fichier de projet Java**, ce guide vous accompagne à chaque étape — du chargement d’un fichier *.mpp* à l’extraction des chiffres de devise. À la fin, vous serez à l’aise pour manipuler les données de devise MS Project dans vos propres applications.

## Réponses rapides
- **Quelle bibliothèque lit les fichiers MS Project ?** Aspose.Tasks pour Java.  
- **Combien de lignes de code pour obtenir les chiffres de devise ?** Juste trois lignes concises après le chargement du projet.  
- **Ai‑je besoin d’une licence pour le développement ?** Une version d’essai gratuite suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieur (tout JDK exécutant Aspose.Tasks).  
- **Puis‑je récupérer d’autres propriétés du projet ?** Oui – Aspose.Tasks expose l’ensemble complet des champs du projet (par ex., date de début, taux de coût, etc.).

## Qu’est‑ce que la devise MS Project ?
`ms project currency` désigne la précision numérique (nombre de décimales) que Microsoft Project utilise lors de l’affichage des valeurs monétaires. Elle est stockée dans le fichier de projet sous la propriété **CURRENCY_DIGITS** et détermine si les montants apparaissent en nombres entiers, avec une décimale, deux décimales, etc.

## Pourquoi utiliser Aspose.Tasks pour gérer la devise MS Project ?
- **Aucune installation de Microsoft Project requise** – travaillez directement avec les fichiers *.mpp* sur n’importe quelle plateforme supportant Java.  
- **Sécurité de type forte** – l’API renvoie des valeurs fortement typées, réduisant les erreurs d’analyse.  
- **Optimisé pour les performances** – chargez de gros projets rapidement et extrayez uniquement les champs dont vous avez besoin.  
- **Multiplateforme** – exécutez sous Windows, Linux ou macOS sans modification.

## Prérequis
Avant de commencer, assurez‑vous de disposer de :

1. **Environnement de développement Java** – JDK 8 ou plus récent installé et configuré.  
2. **Aspose.Tasks pour Java** – téléchargez le dernier JAR depuis le site officiel : [Aspose.Tasks pour Java](https://releases.aspose.com/tasks/java/).  
3. **Connaissances de base en Java** – vous devez être à l’aise pour créer un projet Java, ajouter des bibliothèques externes et exécuter une méthode `main`.  

## Importer les packages
Tout d’abord, importez les classes dont nous aurons besoin.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Étape 1 : Définir le répertoire de données
Spécifiez le dossier contenant votre **fichier de projet Java** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Remplacez `"Your Data Directory"` par le chemin absolu ou relatif où se trouve `project.mpp`.

## Étape 2 : Charger le fichier MPP  
Nous allons maintenant voir **comment charger les fichiers mpp** avec Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Assurez‑vous que le nom du fichier correspond exactement ; sinon, une `IOException` sera levée.

## Étape 3 : Récupérer les chiffres de devise  
Une fois le projet chargé, extraire les **chiffres de devise MS Project** ne nécessite qu’une seule ligne :  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
L’appel renvoie un `Integer` représentant le nombre de décimales (par ex., `2` pour les centimes). La valeur est affichée dans la console, mais vous pouvez également la stocker dans une variable pour un traitement ultérieur.

## Problèmes courants & conseils
- **Fichier introuvable** – vérifiez le chemin `dataDir` et assurez‑vous que le nom du fichier est correct, y compris l’extension `.mpp`.  
- **Version de fichier non prise en charge** – Aspose.Tasks supporte les formats Project 2000‑2024 ; les fichiers plus anciens ou corrompus peuvent nécessiter une conversion.  
- **Licence non définie** – pendant le développement, une version d’essai suffit, mais en production vous devez appliquer une licence valide pour éviter les filigranes d’évaluation.

## Questions fréquentes

**Q : Aspose.Tasks peut‑il gérer d’autres attributs du projet en plus des chiffres de devise ?**  
R : Oui, Aspose.Tasks offre une large gamme de fonctionnalités pour manipuler divers aspects des fichiers Project, tels que les tâches, les ressources et les champs personnalisés.

**Q : Aspose.Tasks convient‑il aux applications de niveau entreprise ?**  
R : Absolument, Aspose.Tasks est conçu pour répondre aux exigences des projets d’entreprise, offrant haute performance et évolutivité.

**Q : Aspose.Tasks prend‑il en charge le développement multiplateforme ?**  
R : Oui, vous pouvez utiliser Aspose.Tasks pour Java sur n’importe quelle plateforme supportant le Java Runtime Environment (Windows, Linux, macOS).

**Q : Puis‑je essayer Aspose.Tasks avant d’acheter ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite [ici](https://releases.aspose.com/).

**Q : Où puis‑je obtenir du support pour Aspose.Tasks ?**  
R : Vous trouverez de l’aide sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Dernière mise à jour :** 2025-12-05  
**Testé avec :** Aspose.Tasks pour Java 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}