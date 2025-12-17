---
date: 2025-12-17
description: Apprenez à exporter le projet au format PDF, à réduire l'écart du pied
  de page et à enregistrer le projet en tant qu'image en utilisant Aspose.Tasks pour
  Java. Optimisez la mise en page de votre MS Project sans effort.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
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
Dans ce tutoriel, vous découvrirez **comment exporter un projet en PDF** tout en réduisant l'espace indésirable entre la liste des tâches et le pied de page dans les fichiers Microsoft Project. À la fin du guide, vous serez capable de générer des PDF propres, des images PNG et des pages HTML avec une mise en page compacte en utilisant Aspose.Tasks pour Java. Parcourons le processus étape par étape.

## Réponses rapides  
- **Que signifie « exporter un projet en PDF » ?** Cela convertit un fichier MPP en document PDF en conservant les tâches, les chronologies et le formatage.  
- **Pourquoi réduire l'écart du pied de page ?** Un écart plus petit crée des rapports plus compacts et plus professionnels, notamment pour les documents imprimés ou affichés sur le web.  
- **Puis-je également enregistrer le projet sous forme d'image ?** Oui – Aspose.Tasks prend en charge PNG, JPEG et d'autres formats d'image.  
- **Ai‑je besoin d'une licence spéciale ?** Un essai gratuit est disponible ; une licence commerciale est requise pour une utilisation en production.  
- **Quelle version de Java est requise ?** Java 8 ou supérieur fonctionne avec la bibliothèque actuelle d'Aspose.Tasks.

## Qu’est‑ce que « exporter un projet en PDF » ?  
Exporter un projet en PDF transforme la structure interne MPP en un document portable qui peut être ouvert sur n'importe quel appareil sans nécessiter Microsoft Project. C’est idéal pour partager des rapports d’état, des mises à jour aux parties prenantes ou archiver des plans de projet.

## Pourquoi réduire l’écart du pied de page ?  
L'écart par défaut du pied de page peut ajouter un espace blanc inutile, entraînant des problèmes de pagination et un aspect déséquilibré. Réduire cet écart garantit que votre contenu utilise la page de manière efficace, rendant le PDF ou l'image final(e) plus lisible.

## Comment réduire l’écart entre la liste des tâches et le pied de page ?  
Aspose.Tasks propose une option `setReduceFooterGap(true)` pour les opérations d’enregistrement en image, PDF et HTML. Activer ce drapeau indique au moteur de compresser l'espace entre la dernière ligne de tâche et le pied de page.

## Enregistrer le projet en image avec Aspose.Tasks  
Si vous avez besoin d’une capture visuelle de votre planning, vous pouvez **enregistrer le projet en image** (PNG) tout en appliquant les mêmes paramètres de réduction d’écart.

## Exportation Java du projet en PDF  
Les sections suivantes parcourent un flux de travail complet d’**exportation de projet Java**, depuis le chargement du fichier MPP jusqu’à son enregistrement dans trois formats différents.

## Prérequis
1. Java Development Kit (JDK) – version 8 ou supérieure.  
2. Bibliothèque Aspose.Tasks pour Java – téléchargez‑la depuis [ici](https://releases.aspose.com/tasks/java/).

## Importer les packages
Avant de plonger dans la partie codage, importons les packages nécessaires :
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

## Étape 1 : Fournir le chemin vers votre répertoire de données
```java
String dataDir = "Your Data Directory";
```
Assurez‑vous de remplacer `"Your Data Directory"` par le chemin vers votre répertoire de données réel où se trouve votre fichier Microsoft Project (`HomeMovePlan.mpp` dans cet exemple).

## Étape 2 : Lire le fichier MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Cette ligne de code lit le fichier Microsoft Project nommé `HomeMovePlan.mpp`.

## Étape 3 : Définir ImageSaveOptions (Enregistrer le projet en image)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Configurez les options d’enregistrement d’image, en définissant `ReduceFooterGap` à `true` pour réduire l’écart entre la liste des tâches et le pied de page.

## Étape 4 : Enregistrer en image
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Enregistrez le projet en image avec les options configurées.

## Étape 5 : Définir PdfSaveOptions (Exporter le projet en PDF)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
Définissez les options d’enregistrement PDF, en veillant à définir `ReduceFooterGap` à `true`.

## Étape 6 : Enregistrer en PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Enregistrez le projet en PDF avec les options configurées.

## Étape 7 : Définir HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
Spécifiez les options d’enregistrement HTML, en définissant `ReduceFooterGap` à `true`.

## Étape 8 : Enregistrer en HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Enregistrez le projet en fichier HTML avec les options configurées.

## Conclusion  
En conclusion, réduire l’écart entre la liste des tâches et le pied de page dans les fichiers Microsoft Project est un processus simple avec Aspose.Tasks pour Java. En suivant les étapes décrites dans ce tutoriel, vous pouvez efficacement **exporter le projet en PDF**, l’enregistrer en image ou générer du HTML tout en conservant une mise en page compacte et professionnelle.

## FAQ

### Q : Aspose.Tasks est‑il compatible avec toutes les versions de Microsoft Project ?
A : Aspose.Tasks prend en charge les formats Microsoft Project 2003‑2019, garantissant la compatibilité avec diverses versions.

### Q : Puis‑je personnaliser l’apparence du pied de page dans mes documents de projet ?
A : Oui, Aspose.Tasks offre de nombreuses options pour personnaliser l’apparence des pieds de page, y compris la réduction des écarts et le réglage du placement du contenu.

### Q : Aspose.Tasks prend‑il en charge l’enregistrement de projets dans des formats autres que PNG, PDF et HTML ?
A : Oui, Aspose.Tasks prend en charge un large éventail de formats, notamment XLSX, XML et MPP, entre autres.

### Q : Existe‑t‑il une version d’essai disponible pour Aspose.Tasks ?
A : Oui, vous pouvez télécharger une version d’essai gratuite d’Aspose.Tasks depuis [ici](https://releases.aspose.com/).

### Q : Où puis‑je obtenir de l’aide si je rencontre des problèmes en utilisant Aspose.Tasks ?
A : Vous pouvez obtenir de l’assistance sur le forum communautaire Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

## Questions fréquemment posées (Supplémentaires)

**Q : Comment la réduction de l’écart du pied de page affecte‑t‑elle la pagination ?**  
A : Elle minimise l’espace blanc en bas de chaque page, permettant d’y placer plus de tâches sur une même page et réduisant le nombre total de pages.

**Q : Puis‑je appliquer le même réglage de réduction d’écart à une seule page uniquement ?**  
A : Oui, en définissant `setRenderToSinglePage(true)` dans `ImageSaveOptions`, vous pouvez contrôler la pagination tout en réduisant l’écart.

**Q : L’option `setReduceFooterGap` est‑elle disponible pour d’autres formats de sortie ?**  
A : Actuellement, elle est prise en charge pour les exportations PNG, PDF et HTML. Pour d’autres formats, il peut être nécessaire d’ajuster manuellement la mise en page.

**Q : Que se passe‑t‑il si mon projet contient des champs personnalisés — sont‑ils conservés ?**  
A : Tous les champs personnalisés sont conservés lors de l’exportation ; les ajustements de mise en page n’affectent que l’espacement, pas les données.

**Q : La bibliothèque gère‑t‑elle efficacement les grands projets ?**  
A : Aspose.Tasks diffuse les données et peut traiter de gros fichiers MPP ; toutefois, assurez‑vous de disposer de suffisamment de mémoire lors de l’exportation vers des images haute résolution.

---

**Dernière mise à jour :** 2025-12-17  
**Testé avec :** Aspose.Tasks 24.11 for Java  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}