---
title: Rendre les données MS Project au format 24bppRgb dans Aspose.Tasks
linktitle: Rendre les données au format 24bppRgb dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment restituer des données MS Project sous forme d'images en Java à l'aide d'Aspose.Tasks. Suivez notre tutoriel étape par étape pour une intégration transparente.
weight: 11
url: /fr/java/project-file-operations/render-data-format-24bppRgb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rendre les données MS Project au format 24bppRgb dans Aspose.Tasks

## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus de rendu des données au format MS Project 24bppRgb à l'aide d'Aspose.Tasks pour Java. Le rendu des données d'un projet au format image peut être utile à diverses fins, telles que le partage visuel de l'avancement du projet ou la création de rapports.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Aspose.Tasks pour Java : téléchargez et installez Aspose.Tasks pour Java à partir de[ici](https://releases.aspose.com/tasks/java/).
3. Connaissance de base de la programmation Java : une connaissance du langage de programmation Java sera utile pour comprendre et mettre en œuvre les exemples de code.

## Importer des packages
Tout d'abord, vous devez importer les packages nécessaires dans votre projet Java :
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Décomposons l'exemple fourni en plusieurs étapes :
## Étape 1 : Définir le répertoire de données
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Data Directory";
```
Dans cette étape, vous définissez le répertoire où se trouvent les données de votre projet. Remplacer`"Your Data Directory"` avec le chemin réel vers votre répertoire de données.
## Étape 2 : Charger le fichier de projet
```java
Project project = new Project(dataDir + "project.mpp");
```
Ici, nous chargeons le fichier MS Project (`project.mpp` ) en utilisant Aspose.Tasks et stockez-le dans le`project` objet.
## Étape 3 : configurer les options d'enregistrement de l'image
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
Cette étape consiste à configurer les options d'enregistrement des données du projet sous forme d'image. Nous spécifions le format d'image (TIFF), les résolutions horizontale et verticale et le format de pixel (24bppRgb).
## Étape 4 : Enregistrer les données du projet sous forme d'image
```java
project.save(dataDir + "resFile.tif", options);
```
Enfin, nous enregistrons les données du projet sous forme de fichier image (`resFile.tif`) avec les options spécifiées.

## Conclusion
Dans ce didacticiel, nous avons appris à restituer les données d'un projet au format MS Project 24bppRgb à l'aide d'Aspose.Tasks pour Java. En suivant les étapes fournies, vous pouvez facilement convertir les données de votre projet en un format d'image à diverses fins.
## FAQ
### Q : Puis-je restituer les données du projet dans d'autres formats d'image ?
R : Oui, Aspose.Tasks prend en charge le rendu des données du projet dans divers formats d'image tels que PNG, JPEG, BMP, etc.
### Q : Aspose.Tasks est-il compatible avec différentes versions de MS Project ?
R : Oui, Aspose.Tasks prend en charge plusieurs versions de MS Project, notamment 2003, 2007, 2010, 2013 et 2016.
### Q : Puis-je personnaliser la résolution et le format de pixels de l'image rendue ?
R : Oui, vous pouvez personnaliser la résolution et le format de pixels en fonction de vos besoins à l'aide d'Aspose.Tasks.
### Q : Aspose.Tasks nécessite-t-il une licence pour une utilisation commerciale ?
 R : Oui, vous devez acheter une licence pour une utilisation commerciale d’Aspose.Tasks. Vous pouvez obtenir une licence temporaire à des fins de test auprès de[ici](https://purchase.aspose.com/temporary-license/).
### Q : Où puis-je obtenir de l'aide pour Aspose.Tasks ?
 R : Vous pouvez obtenir de l'aide pour Aspose.Tasks auprès du[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
