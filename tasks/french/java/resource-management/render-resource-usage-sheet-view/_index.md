---
date: 2026-01-15
description: Apprenez à enregistrer un projet au format PDF et à rendre les vues Utilisation
  des ressources et Feuille de MS Project à l’aide d’Aspose.Tasks pour Java. Suivez
  notre guide étape par étape pour exporter le projet en PDF sans effort.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Enregistrer le projet au format PDF – Rendu de l’utilisation des ressources
  et de la vue Feuille dans Aspose.Tasks
url: /fr/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer le projet au format PDF – Rendu de la vue Utilisation des ressources et Feuille dans Aspose.Tasks

## Introduction
Dans ce tutoriel, vous découvrirez comment **enregistrer le projet au format PDF** tout en rendant les vues Resource Usage et Sheet d'un fichier Microsoft Project. Que vous ayez besoin de générer un rapport imprimable pour les parties prenantes ou de convertir des fichiers MPP en un format universellement consultable, Aspose.Tasks for Java rend le processus simple—sans nécessiter d'installation de Microsoft Project.

## Quick Answers
- **Que fait “enregistrer le projet au format PDF” ?** Il convertit un fichier Project (MPP) en un document PDF en préservant la vue sélectionnée.  
- **Quelle vue peut être exportée ?** Resource Usage, Sheet, Gantt, Task Usage, et plus.  
- **Puis-je modifier l'échelle de temps dans le PDF ?** Oui—les options incluent Days, ThirdsOfMonths et Months.  
- **Ai-je besoin d'installer Microsoft Project ?** Non, Aspose.Tasks fonctionne de manière indépendante.  
- **Une licence est‑elle requise pour la production ?** Oui, une licence commerciale est nécessaire pour une utilisation hors période d'essai.

## Qu'est‑ce que “enregistrer le projet au format PDF” ?
Enregistrer un projet au format PDF crée une représentation statique et haute résolution d'une vue Project choisie. Cela est idéal pour le partage avec les clients, l'archivage ou l'impression sans exposer le fichier projet sous‑jacent.

## Pourquoi utiliser Aspose.Tasks pour exporter un projet en PDF ?
- **Aucune dépendance externe** – fonctionne sur toute plateforme supportant Java.  
- **Contrôle fin** – vous pouvez sélectionner la vue, l'échelle de temps et la mise en page.  
- **Haute fidélité** – le PDF reflète l'apparence de la vue Project originale.  
- **Prêt pour l'automatisation** – intégrez-le aux pipelines CI, aux services de reporting ou aux convertisseurs batch.

## Prérequis
Avant de commencer, assurez‑vous d'avoir :

1. **Java Development Kit (JDK)** – dernière version recommandée.  
2. **Aspose.Tasks for Java** – téléchargez depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/).

## Importer les packages
Tout d'abord, importez les classes nécessaires dans votre projet Java :

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Guide étape par étape

### Étape 1 : Lire le projet source
Chargez le fichier MPP que vous souhaitez convertir.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Étape 2 : Définir SaveOptions avec l'échelle de temps requise (Exporter le projet en PDF)
Configurez les options d'exportation PDF et définissez l'échelle de temps souhaitée.  
*Ici nous utilisons **Days** comme exemple.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Étape 3 : Définir le format de présentation sur ResourceUsage
Choisissez la vue que vous souhaitez rendre. Dans ce cas, la vue **Resource Usage**.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Étape 4 : Enregistrer le projet (Convertir le MPP en PDF)
Exécutez la conversion et générez le fichier PDF.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Étape 5 : Rendre les vues pour d'autres réglages d'échelle de temps (Modifier l'échelle de temps du PDF)
Répétez les étapes précédentes pour produire des PDF avec différentes échelles de temps telles que **ThirdsOfMonths** et **Months**.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Problèmes courants et solutions
- **Erreurs de fichier introuvable** – Vérifiez que `dataDir` pointe vers le bon dossier et que le nom du fichier MPP correspond exactement.  
- **Sortie PDF vide** – Assurez‑vous que le `PresentationFormat` correspond à une vue contenant des données (par ex., ResourceUsage).  
- **Échelle de temps incorrecte** – Vérifiez que `options.setTimescale()` est appelé avant chaque `project.save()`.

## Questions fréquemment posées

### Aspose.Tasks peut‑il rendre d'autres vues en plus de Resource Usage et Sheet ?
Aspose.Tasks prend en charge le rendu de diverses vues telles que Gantt Chart, Task Usage et les vues Calendar, entre autres.

### Aspose.Tasks est‑il compatible avec différentes versions de fichiers Microsoft Project ?
Oui, Aspose.Tasks prend en charge un large éventail de formats de fichiers Microsoft Project, y compris les formats MPP, MPT et XML.

### Puis‑je personnaliser l'apparence des vues rendues avec Aspose.Tasks ?
Absolument ! Aspose.Tasks offre de nombreuses options pour personnaliser l'apparence et la mise en page des vues rendues afin de répondre à vos exigences spécifiques.

### Aspose.Tasks nécessite‑t‑il l'installation de Microsoft Project sur le système ?
Non, Aspose.Tasks est une bibliothèque autonome et ne nécessite pas l'installation de Microsoft Project pour fonctionner.

### Un support technique est‑il disponible pour les utilisateurs d'Aspose.Tasks ?
Oui, les utilisateurs d'Aspose.Tasks peuvent bénéficier du support technique via le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-01-15  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose