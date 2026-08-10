---
date: 2026-05-20
description: Apprenez comment exporter le projet en PDF, réduire l'écart du pied de
  page et enregistrer le projet en image en utilisant Aspose.Tasks pour Java. Optimisez
  la mise en page de votre MS Project sans effort.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Exporter le projet en PDF et réduire l'écart entre la liste des tâches
  et le pied de page dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Exporter le projet en PDF et réduire l'écart entre la liste des tâches et le
  pied de page dans Aspose.Tasks
url: /fr/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exporter le projet en PDF et réduire l'écart entre la liste des tâches et le pied de page dans Aspose.Tasks

## Introduction
Dans ce tutoriel, vous découvrirez **comment exporter un projet en PDF** tout en réduisant l'espace indésirable entre la liste des tâches et le pied de page dans les fichiers Microsoft Project. À la fin du guide, vous serez capable de générer des PDF propres, des images PNG et des pages HTML avec une mise en page compacte en utilisant Aspose.Tasks pour Java. Parcourons le processus étape par étape, et vous verrez pourquoi cela est important pour les rapports professionnels.

## Réponses rapides
- **Que signifie « exporter un projet en PDF » ?** Il convertit un fichier MPP en document PDF en conservant les tâches, les chronologies et la mise en forme.  
- **Pourquoi réduire l'écart du pied de page ?** Un écart plus petit crée des rapports plus compacts et plus professionnels, surtout pour les documents imprimés ou affichés sur le web.  
- **Puis-je également enregistrer le projet en tant qu'image ?** Oui – Aspose.Tasks prend en charge PNG, JPEG et d'autres formats d'image.  
- **Ai-je besoin d'une licence spéciale ?** Une version d'essai gratuite est disponible ; une licence commerciale est requise pour une utilisation en production.  
- **Quelle version de Java est requise ?** Java 8 ou supérieur fonctionne avec la bibliothèque Aspose.Tasks actuelle.  

## Qu'est-ce que « exporter un projet en PDF » ?
Exporter un projet en PDF transforme la structure interne MPP en un document portable qui peut être ouvert sur n'importe quel appareil sans nécessiter Microsoft Project. C'est idéal pour partager des rapports d'état, des mises à jour des parties prenantes ou archiver des plans de projet. Il conserve la mise en page, les couleurs et la hiérarchie des tâches d'origine, garantissant que le PDF ressemble exactement au fichier source.

## Pourquoi réduire l'écart du pied de page ?
L'écart par défaut du pied de page peut ajouter un espace blanc inutile, entraînant des problèmes de pagination et une apparence déséquilibrée. Réduire cet écart garantit que votre contenu utilise la page de manière efficace, rendant le PDF ou l'image final(e) plus lisible. Une mise en page plus compacte réduit également le nombre total de pages, ce qui peut diminuer les coûts d'impression et améliorer la navigation à l'écran.

## Comment réduire l'écart entre la liste des tâches et le pied de page ?
`setReduceFooterGap` est une propriété booléenne qui contrôle l'espacement du pied de page lors de l'exportation.  
Aspose.Tasks fournit une option `setReduceFooterGap(true)` pour les opérations d'enregistrement d'image, PDF et HTML. Activer ce drapeau indique au moteur de compresser l'espace entre la dernière ligne de tâche et le pied de page. Lorsqu'elle est définie sur true, le rendu supprime automatiquement la marge sans couper aucune donnée de tâche, ce qui donne une mise en page de page plus propre.

## Enregistrer le projet en image avec Aspose.Tasks
`ImageSaveOptions` configure la façon dont un projet est rendu dans un fichier image.  
La classe `ImageSaveOptions` vous permet d'exporter un instantané du planning en PNG, JPEG ou BMP. Lorsque vous activez également `setReduceFooterGap(true)`, l'image générée reflète la mise en page compacte du PDF, vous offrant un visuel propre pour les présentations ou les tableaux de bord.

## Exportation d'un projet Java en PDF
Les sections suivantes parcourent un flux complet d'**java project export**, depuis le chargement du fichier MPP jusqu'à son enregistrement dans trois formats différents.

## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Java Development Kit (JDK) – version 8 ou ultérieure.  
2. Bibliothèque Aspose.Tasks pour Java – téléchargez‑la depuis [ici](https://releases.aspose.com/tasks/java/).  

## Importer les packages
Before diving into the coding part, let's import the necessary packages:

```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Étape 1 : fournir le chemin vers votre répertoire de données
```java
String dataDir = "Your Data Directory";
```  
Assurez‑vous de remplacer "Your Data Directory" par le chemin vers votre répertoire de données réel où se trouve votre fichier Microsoft Project (`HomeMovePlan.mpp` dans cet exemple).

## Étape 2 : lire le fichier MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
Cette ligne de code lit le fichier Microsoft Project nommé `HomeMovePlan.mpp`.

## Étape 3 : définir ImageSaveOptions (enregistrer le projet en image)
`ImageSaveOptions` configure la façon dont un projet est rendu dans un fichier image.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
Configurez les options d'enregistrement d'image, en définissant `ReduceFooterGap` sur `true` pour réduire l'écart entre la liste des tâches et le pied de page.

## Étape 4 : enregistrer en image
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
Enregistrez le projet en image avec les options configurées.

## Étape 5 : définir PdfSaveOptions (exporter le projet en PDF)
`PdfSaveOptions` spécifie les paramètres d'exportation d'un projet au format PDF.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
Définissez les options d'enregistrement PDF, en veillant à définir `ReduceFooterGap` sur `true`.

## Étape 6 : enregistrer en PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
Enregistrez le projet en PDF avec les options configurées.

## Étape 7 : définir HtmlSaveOptions
`HtmlSaveOptions` contrôle la conversion d'un projet en HTML, y compris les options de style et de mise en page.  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
Spécifiez les options d'enregistrement HTML, en définissant `ReduceFooterGap` sur `true`.

## Étape 8 : enregistrer en HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
Enregistrez le projet en fichier HTML avec les options configurées.

## Cas d'utilisation courants et conseils
- **Rapports aux parties prenantes :** Exportez en PDF avec un écart de pied de page réduit pour garder les rapports concis et adaptés à l'impression.  
- **Instantanés de tableau de bord :** Utilisez l'exportation d'image lorsque vous avez besoin d'un visuel rapide pour Power BI ou Confluence.  
- **Publication web :** L'exportation HTML conserve l'interactivité et peut être intégrée directement dans les portails intranet.  
- **Astuce :** Pour les très grands projets, augmentez la `Resolution` dans `ImageSaveOptions` à 300 dpi pour maintenir la clarté tout en bénéficiant de l'écart réduit.

## Questions fréquemment posées (Supplémentaires)

**Q : Comment la réduction de l'écart du pied de page affecte‑t‑elle la pagination ?**  
A: Elle minimise l'espace blanc en bas de chaque page, permettant à davantage de tâches de tenir sur une même page et réduisant le nombre total de pages.

**Q : Puis‑je appliquer le même réglage de réduction d'écart à une seule page uniquement ?**  
A: Oui, en définissant `setRenderToSinglePage(true)` dans `ImageSaveOptions`, vous pouvez contrôler la pagination tout en réduisant l'écart.

**Q : L'option `setReduceFooterGap` est‑elle disponible pour d'autres formats de sortie ?**  
A: Actuellement, elle est prise en charge pour les exportations PNG, PDF et HTML. Pour d'autres formats, vous devrez peut‑être ajuster la mise en page manuellement.

**Q : Que se passe‑t‑il si mon projet contient des champs personnalisés—sont‑ils préservés ?**  
A: Tous les champs personnalisés sont conservés lors de l'exportation ; les ajustements de mise en page n'affectent que l'espacement, pas les données.

**Q : La bibliothèque gère‑t‑elle efficacement les grands projets ?**  
A: Aspose.Tasks diffuse les données et peut traiter des fichiers MPP de plusieurs centaines de pages sans charger le fichier complet en mémoire ; cependant, allouez suffisamment d'espace de tas lors de l'exportation d'images haute résolution.

---

**Dernière mise à jour :** 2026-05-20  
**Testé avec :** Aspose.Tasks 24.11 pour Java  
**Auteur :** Aspose

## Tutoriels associés

- [Enregistrer le projet en image – format 24bppRgb avec Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Enregistrer le projet en tant que modèle, CSV et texte avec Aspose.Tasks pour Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Comment créer un fichier MPP – créer et enregistrer un projet vide au format MPP avec Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}