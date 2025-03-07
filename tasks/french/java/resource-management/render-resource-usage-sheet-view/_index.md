---
title: Rendre l'utilisation des ressources et la vue de la feuille dans Aspose.Tasks
linktitle: Rendre l'utilisation des ressources et la vue de la feuille dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment afficher les vues Utilisation des ressources et Feuille de MS Project dans Aspose.Tasks pour Java. Suivez notre guide étape par étape pour générer des rapports PDF détaillés sans effort.
weight: 16
url: /fr/java/resource-management/render-resource-usage-sheet-view/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rendre l'utilisation des ressources et la vue de la feuille dans Aspose.Tasks

## Introduction
Dans ce didacticiel, nous allons apprendre à utiliser Aspose.Tasks pour Java pour afficher les vues d'utilisation des ressources et de feuille de MS Project. Aspose.Tasks est une puissante bibliothèque Java qui permet aux développeurs de travailler avec des fichiers Microsoft Project sans avoir besoin d'installer Microsoft Project.
## Conditions préalables
Avant de commencer, assurez-vous que les prérequis suivants sont installés et configurés :
1. Kit de développement Java (JDK) : assurez-vous que le kit de développement Java est installé sur votre système. Vous pouvez télécharger et installer la dernière version de JDK à partir du site Web d'Oracle.
2.  Aspose.Tasks for Java : téléchargez et installez la bibliothèque Aspose.Tasks for Java à partir du[page de téléchargement](https://releases.aspose.com/tasks/java/).

## Importer des packages
Tout d'abord, vous devez importer les packages nécessaires dans votre projet Java :
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Étape 1 : Lire le projet source
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Data Directory";
// Lire le projet source
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
Dans cette étape, nous spécifions le chemin d'accès au fichier projet source (`ResourceUsageView.mpp` ) et utilisez le`Project` classe pour le lire.
## Étape 2 : Définir les options de sauvegarde avec les paramètres d'échelle de temps requis
```java
// Définissez les SaveOptions avec les paramètres TimeScale requis en jours
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Ici, nous définissons le`SaveOptions` avec le nécessaire`TimeScale` paramètres. Dans cet exemple, nous définissons le`TimeScale` à jours.
## Étape 3 : définissez le format de présentation sur ResourceUsage
```java
// Définissez le format de présentation sur ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 Nous définissons le format de présentation sur`ResourceUsage`, indiquant que nous souhaitons afficher la vue Utilisation des ressources.
## Étape 4 : Enregistrez le projet
```java
// Enregistrez le projet
project.save(dataDir + days, options);
```
Enfin, nous sauvegardons le projet avec les options spécifiées. Dans cet exemple, le fichier de sortie sera enregistré sous`result_days.pdf`.
## Étape 5 : Rendre les vues pour d'autres paramètres d'échelle de temps
Répétez les étapes 2 à 4 pour le rendu des vues avec différents paramètres TimeScale (ThirdsOfMonths et Months).
```java
// Définissez les paramètres de l'échelle de temps sur ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Enregistrez le projet
project.save(thirds, options);
// Définissez les paramètres de l'échelle de temps sur Mois
options.setTimescale(Timescale.Months);
// Enregistrez le projet
project.save(dataDir + months, options);
```
 Assurez-vous de changer le`Timescale` paramètres en conséquence pour chaque vue.

## Conclusion
Dans ce didacticiel, nous avons expliqué comment utiliser Aspose.Tasks pour Java pour afficher les vues d'utilisation des ressources et de feuille de MS Project. En suivant les étapes décrites ci-dessus, vous pouvez générer efficacement ces vues au format PDF, facilitant ainsi une meilleure visualisation et analyse des données de votre projet.
## FAQ
### Aspose.Tasks peut-il afficher d'autres vues que l'utilisation des ressources et la feuille ?
Aspose.Tasks prend en charge le rendu de diverses vues telles que les vues Diagramme de Gantt, Utilisation des tâches et Calendrier, entre autres.
### Aspose.Tasks est-il compatible avec différentes versions des fichiers Microsoft Project ?
Oui, Aspose.Tasks prend en charge un large éventail de formats de fichiers Microsoft Project, notamment les formats MPP, MPT et XML.
### Puis-je personnaliser l’apparence des vues rendues à l’aide d’Aspose.Tasks ?
Absolument! Aspose.Tasks fournit de nombreuses options pour personnaliser l'apparence et la disposition des vues rendues en fonction de vos besoins spécifiques.
### Aspose.Tasks nécessite-t-il que Microsoft Project soit installé sur le système ?
Non, Aspose.Tasks est une bibliothèque autonome et ne nécessite pas l'installation de Microsoft Project pour son fonctionnement.
### Le support technique est-il disponible pour les utilisateurs d'Aspose.Tasks ?
 Oui, les utilisateurs d'Aspose.Tasks peuvent bénéficier d'une assistance technique via le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
