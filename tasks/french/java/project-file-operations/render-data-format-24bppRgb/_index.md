---
date: 2025-12-17
description: Apprenez à enregistrer un projet en tant qu'image et à modifier la résolution
  de l'image en Java à l'aide d'Aspose.Tasks for Java. Ce guide étape par étape montre
  le rendu des données MS Project au format 24bppRgb.
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: Enregistrer le projet en tant qu’image – format 24bppRgb avec Aspose.Tasks
url: /fr/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer le projet en image – Format 24bppRgb avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez comment **enregistrer un projet en image** en utilisant le format de pixel 24bppRgb avec Aspose.Tasks pour Java. Rendre les données MS Project sous forme d'image est pratique lorsque vous devez partager un aperçu visuel d'un planning, intégrer une chronologie dans un rapport ou générer des vignettes pour un portail de projet. Nous vous montrerons également comment **modifier la résolution de l'image java** pour répondre à vos exigences de qualité.

## Réponses rapides
- **Puis-je rendre un projet sous forme d'image ?** Oui, Aspose.Tasks vous permet d'enregistrer un projet au format TIFF, PNG, JPEG, etc.  
- **Quel format de pixel offre la meilleure profondeur de couleur ?** `Format24bppRgb` fournit des images en couleur vraie (24 bits).  
- **Comment ajuster la résolution de l'image ?** Utilisez `setHorizontalResolution` et `setVerticalResolution` sur `ImageSaveOptions`.  
- **Ai‑je besoin d'une licence pour la production ?** Une licence commerciale est requise pour un usage autre que l'évaluation.  
- **Est‑ce compatible avec toutes les versions de Java ?** Fonctionne avec Java 8 et versions ultérieures.

## Qu’est‑ce que « enregistrer le projet en image » ?
Enregistrer un projet sous forme d'image convertit la représentation visuelle d’un fichier Microsoft Project (`.mpp`) en un format raster (par ex., TIFF). Le fichier résultant peut être affiché dans les navigateurs, inséré dans des documents ou imprimé sans nécessiter l’application Project d’origine.

## Pourquoi utiliser le format 24bppRgb ?
Le format de pixel 24bppRgb stocke chaque pixel avec 8 bits pour le rouge, le vert et le bleu, offrant une qualité couleur vraie sans canal alpha. C’est idéal pour des rapports à haute clarté où la fidélité des couleurs compte, tout en maintenant des tailles de fichier raisonnables comparées aux formats 32 bits.

## Prérequis
Avant de commencer, assurez‑vous de disposer de :

1. **Java Development Kit (JDK)** – JDK 8 ou version supérieure installé sur votre machine.  
2. **Aspose.Tasks for Java** – Téléchargez et installez depuis [here](https://releases.aspose.com/tasks/java/).  
3. **Connaissances de base en Java** – Une familiarité avec la syntaxe Java et la configuration d’un projet vous aidera à suivre les extraits de code.

## Importer les packages
Tout d’abord, importez les classes Aspose.Tasks requises dans votre projet Java :

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Guide étape par étape

### Étape 1 : Définir le répertoire de données
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Remplacez `"Your Data Directory"` par le chemin absolu où se trouve votre fichier `.mpp`.

### Étape 2 : Charger le fichier de projet
```java
Project project = new Project(dataDir + "project.mpp");
```
Cette ligne lit le fichier Microsoft Project (`project.mpp`) et crée un objet `Project` qu’Aspose.Tasks peut manipuler.

### Étape 3 : Configurer les options d’enregistrement d’image
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
Ici nous définissons le format de sortie en TIFF, spécifions une résolution de **72 dpi** (vous pouvez modifier ces valeurs selon vos besoins – c’est ici que vous **changez la résolution de l'image java**), et sélectionnons le format de pixel 24bppRgb pour une sortie en couleur vraie.

### Étape 4 : Enregistrer les données du projet en image
```java
project.save(dataDir + "resFile.tif", options);
```
La méthode `save` écrit l’image rendue dans `resFile.tif` en utilisant les options définies ci‑dessus.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Image blanche en sortie** | La vue du projet peut être vide. | Appelez `project.setDefaultView(ViewType.Gantt);` avant l’enregistrement. |
| **Image de mauvaise qualité** | Résolution réglée trop basse. | Augmentez `setHorizontalResolution` et `setVerticalResolution` (par ex., 150 dpi). |
| **Format de pixel non pris en charge** | Utilisation d’une version ancienne d’Aspose.Tasks. | Mettez à jour vers la dernière version d’Aspose.Tasks for Java.## Conclusion
Vous savez maintenant comment **enregistrer un projet en image** avec le format 24bppRgb et ajuster la résolution à l’aide d’Aspose.Tasks pour Java. Cette approche vous permet de générer des représentations visuelles claires et fidèles en couleur de vos plannings de projet pour le partage, le reporting ou l’archivage.

## FAQ
### Q : Puis‑je rendre les données du projet dans d’autres formats d’image ?
R : Oui, Aspose.Tasks prend en charge le rendu des données du projet dans divers formats d’image tels que PNG, JPEG, BMP, etc.  
### Q : Aspose.Tasks est‑il compatible avec différentes versions de MS Project ?
R : Oui, Aspose.Tasks supporte plusieurs versions de MS Project, y compris 2003, 2007, 2010, 2013 et 2016.  
### Q : Puis‑je personnaliser la résolution et le format de pixel de l’image rendue ?
R : Oui, vous pouvez personnaliser la résolution et le format de pixel selon vos besoins en utilisant Aspose.Tasks.  
### Q : Aspose.Tasks nécessite‑t‑il une licence pour un usage commercial ?
R : Oui, vous devez acquérir une licence pour l’usage commercial d’Aspose.Tasks. Vous pouvez obtenir une licence temporaire pour les tests depuis [here](https://purchase.aspose.com/temporary-license/).  
### Q : Où puis‑je obtenir du support pour Aspose.Tasks ?
R : Vous pouvez obtenir du support pour Aspose.Tasks sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Dernière mise à jour :** 2025-12-17  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}