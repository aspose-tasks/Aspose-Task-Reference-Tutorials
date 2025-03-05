---
title: Réduire l'écart entre la liste des tâches et le pied de page dans Aspose.Tasks
linktitle: Réduire l'écart entre la liste des tâches et le pied de page dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment réduire l'écart entre les listes de tâches et les pieds de page de MS Project à l'aide d'Aspose.Tasks pour Java. Optimisez la mise en page des documents de projet sans effort.
type: docs
weight: 10
url: /fr/java/project-file-operations/reduce-gap-tasks-list-footer/
---
## Introduction
Dans ce didacticiel, nous allons nous pencher sur la réduction de l'écart entre la liste des tâches et le pied de page dans les fichiers Microsoft Project à l'aide d'Aspose.Tasks pour Java. En suivant ces étapes, vous pourrez optimiser la mise en page de vos documents de projet sans effort.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Bibliothèque Aspose.Tasks pour Java : téléchargez et incluez la bibliothèque Aspose.Tasks pour Java dans votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/java/).

## Importer des packages
Avant de plonger dans la partie codage, importons les packages nécessaires :
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
## Étape 1 : Fournissez le chemin d'accès à votre répertoire de données
```java
String dataDir = "Your Data Directory";
```
 Assurez-vous de remplacer`"Your Data Directory"` avec le chemin d'accès à votre répertoire de données réel où se trouve votre fichier Microsoft Project (`HomeMovePlan.mpp` dans cet exemple) est localisé.
## Étape 2 : Lire le fichier MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Cette ligne de code lit le fichier Microsoft Project nommé`HomeMovePlan.mpp`.
## Étape 3 : définir ImageSaveOptions
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Configurez les options d'enregistrement des images, en définissant`ReduceFooterGap` à`true` pour réduire l'écart entre la liste des tâches et le pied de page.
## Étape 4 : Enregistrer sous forme d'image
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Enregistrez le projet sous forme d'image avec les options configurées.
## Étape 5 : Définir les options PdfSave
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 Définir les options d'enregistrement PDF, en veillant à définir`ReduceFooterGap` à`true`.
## Étape 6 : Enregistrer au format PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Enregistrez le projet au format PDF avec les options configurées.
## Étape 7 : définir HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // défini sur vrai
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 Spécifier les options d'enregistrement HTML, paramètre`ReduceFooterGap` à`true`.
## Étape 8 : Enregistrer au format HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Enregistrez le projet sous forme de fichier HTML avec les options configurées.

## Conclusion
En conclusion, réduire l'écart entre la liste des tâches et le pied de page dans les fichiers Microsoft Project est un processus simple avec Aspose.Tasks pour Java. En suivant les étapes décrites dans ce didacticiel, vous pouvez optimiser efficacement la mise en page de vos documents de projet.

## FAQ

### Q : Aspose.Tasks est-il compatible avec toutes les versions de Microsoft Project ?

R : Aspose.Tasks prend en charge les formats Microsoft Project 2003-2019, garantissant la compatibilité entre les différentes versions.

### Q : Puis-je personnaliser l’apparence du pied de page dans les documents de mon projet ?

R : Oui, Aspose.Tasks propose de nombreuses options pour personnaliser l'apparence des pieds de page, notamment en réduisant les espaces et en ajustant le placement du contenu.

### Q : Aspose.Tasks prend-il en charge l'enregistrement de projets dans des formats autres que PNG, PDF et HTML ?

R : Oui, Aspose.Tasks prend en charge un large éventail de formats, notamment XLSX, XML et MPP.

### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks ?

 R : Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Tasks à partir de[ici](https://releases.aspose.com/).

### Q : Où puis-je obtenir de l'aide si je rencontre des problèmes lors de l'utilisation d'Aspose.Tasks ?

 R : Vous pouvez obtenir de l'aide sur le forum de la communauté Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).